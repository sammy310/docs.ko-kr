---
title: 자체 호스팅 gRPC 응용 프로그램-WCF 개발자를 위한 gRPC
description: ASP.NET Core gRPC 응용 프로그램을 자체 호스팅 서비스로 배포 합니다.
ms.date: 12/15/2020
ms.openlocfilehash: a5e2316b8d76593f4eb53760d2609b5bbbc9d2c5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938535"
---
# <a name="self-hosted-grpc-applications"></a>자체 호스팅 gRPC 응용 프로그램

ASP.NET Core 5.0 응용 프로그램은 Windows Server의 IIS에서 호스팅될 수 있지만 현재는 HTTP/2 기능이 지원 되지 않기 때문에 IIS에서 gRPC 응용 프로그램을 호스트할 수 없습니다. 이 기능은 향후 Windows Server 업데이트에 대 한 목표입니다.

Windows 서비스로 응용 프로그램을 실행할 수 있습니다. 또는 .NET 5.0 호스팅 확장의 새로운 기능으로 인해 [systemd](https://en.wikipedia.org/wiki/Systemd)로 제어 되는 Linux 서비스로 실행할 수 있습니다.

## <a name="run-your-app-as-a-windows-service"></a>Windows 서비스로 앱 실행

ASP.NET Core 응용 프로그램을 Windows 서비스로 실행 하도록 구성 하려면 NuGet에서 [Microsoft.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) i n s o r e r. r e r. r e r. r e r. r e s 그런 다음에 대 한 호출을 `UseWindowsService` `CreateHostBuilder` 의 메서드에 추가 `Program.cs` 합니다.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> 응용 프로그램이 Windows 서비스로 실행 되지 않는 경우 `UseWindowsService` 메서드는 아무것도 수행 하지 않습니다.

이제 다음 방법 중 하나를 사용 하 여 응용 프로그램을 게시 합니다.

* Visual Studio에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **게시** 를 선택 합니다.
* .NET CLI에서.

.NET 응용 프로그램을 게시할 때 *프레임 워크 종속* 배포 또는 *자체 포함* 배포를 만들도록 선택할 수 있습니다. 프레임 워크 종속 배포에는 .NET 공유 런타임이 실행 되는 호스트에 설치 되어 있어야 합니다. 자체 포함 배포는 전체 .NET 런타임 및 프레임 워크 복사본으로 게시 되며 모든 호스트에서 실행할 수 있습니다. 각 방법의 장점과 단점을 비롯 한 자세한 내용은 [.net 응용 프로그램 배포](../../core/deploying/index.md) 설명서를 참조 하세요.

호스트에 .NET 5.0 런타임을 설치 하지 않아도 되는 자체 포함 된 응용 프로그램 빌드를 게시 하려면 응용 프로그램에 포함 될 런타임을 지정 합니다. `-r`(또는 `--runtime` ) 플래그를 사용 합니다.

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

프레임 워크 종속 빌드를 게시 하려면 플래그를 생략 `-r` 합니다.

```dotnetcli
dotnet publish -c Release -o ./publish
```

`publish`설치 폴더에 디렉터리의 전체 내용을 복사 합니다. 그런 다음 [sc 도구](/windows/desktop/services/controlling-a-service-using-sc) 를 사용 하 여 실행 파일에 대 한 Windows 서비스를 만듭니다.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Windows 이벤트 로그에 기록 합니다.

`UseWindowsService`메서드는 로그 메시지를 Windows 이벤트 로그에 기록 하는 [로깅](/aspnet/core/fundamentals/logging/) 공급자를 자동으로 추가 합니다. `EventLog` `Logging` 또는 다른 구성 소스 섹션에 항목을 추가 하 여이 공급자에 대 한 로깅을 구성할 수 있습니다 `appsettings.json` .

이러한 설정에서 속성을 설정 하 여 이벤트 로그에 사용 되는 소스 이름을 재정의할 수 있습니다 `SourceName` . 이름을 지정 하지 않으면 기본 응용 프로그램 이름 (일반적으로 실행 가능한 어셈블리 이름)이 사용 됩니다.

로깅에 대 한 자세한 내용은이 챕터의 끝에 있습니다.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Systemd를 사용 하 여 앱을 Linux 서비스로 실행

ASP.NET Core 응용 프로그램이 Linux 서비스 (또는 Linux 용어의 *디먼* )로 실행 되도록 구성 하려면 NuGet에서 [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) 패키지를 설치 합니다. 그런 다음에 대 한 호출을 `UseSystemd` `CreateHostBuilder` 의 메서드에 추가 `Program.cs` 합니다.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> 응용 프로그램이 Linux 서비스로 실행 되지 않는 경우 `UseSystemd` 메서드는 아무것도 수행 하지 않습니다.

이제 응용 프로그램을 게시 합니다. 응용 프로그램은 프레임 워크에 종속 되어 있거나 관련 Linux 런타임에 자체 포함 될 수 있습니다 (예: `linux-x64` ). 다음 방법 중 하나를 사용 하 여 게시할 수 있습니다.

* Visual Studio에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **게시** 를 선택 합니다.
* .NET CLI에서 다음 명령을 사용 합니다.

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
디렉터리의 전체 내용을 `publish` Linux 호스트의 설치 폴더에 복사 합니다. 서비스를 등록 하려면 디렉터리에 추가할 *단위 파일* 이라는 특수 파일이 필요 합니다 `/etc/systemd/system` . 이 폴더에 파일을 만들려면 루트 권한이 필요 합니다. 사용할 식별자와 확장명을 사용 하 여 파일의 이름을로 바꿉니다 `systemd` `.service` . 예를 들면 `/etc/systemd/system/myapp.service`를 사용합니다.

이 예에 표시 된 것 처럼 서비스 파일에는 INI 형식이 사용 됩니다.

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

`Type=notify`속성은 `systemd` 응용 프로그램에서 시작 및 종료 시 알리도록 지시 합니다. 이 `WantedBy=multi-user.target` 설정은 Linux 시스템이 "실행 수준 2"에 도달 하면 서비스가 시작 되도록 합니다. 즉, 그래픽이 아닌 다중 사용자 셸이 활성화 됩니다.

에서 `systemd` 서비스를 인식 하기 전에 구성을 다시 로드 해야 합니다. `systemd`명령을 사용 하 여를 제어 `systemctl` 합니다. 다시 로드 한 후에는 `status` 하위 명령을 사용 하 여 응용 프로그램이 성공적으로 등록 되었는지 확인 합니다.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

서비스를 올바르게 구성한 경우 다음과 같은 출력을 얻게 됩니다.

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

명령을 사용 `start` 하 여 서비스를 시작 합니다.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> 을 `.service` 사용 하는 경우 확장은 선택 사항입니다 `systemctl start` .

`systemd`시스템 시작 시 자동으로 서비스를 시작 하도록 지시 하려면 명령을 사용 `enable` 합니다.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Journald에 로그

Windows 이벤트 로그에 해당 하는 Linux는 `journald` 의 일부인 구조적 로깅 시스템 서비스입니다 `systemd` . Linux 데몬에 의해 표준 출력에 기록 된 로그 메시지는 자동으로에 기록 됩니다 `journald` . 로깅 수준을 구성 하려면 `Console` 로깅 구성의 섹션을 사용 합니다. `UseSystemd`호스트 빌더 메서드는 저널에 맞게 콘솔 출력 형식을 자동으로 구성 합니다.

`journald`는 Linux 로그의 표준 이기 때문에 다양 한 도구를 통합 합니다. 에서 `journald` 외부 로깅 시스템으로 로그를 쉽게 라우팅할 수 있습니다. 호스트에서 로컬로 작업 하는 경우 명령을 사용 하 여 명령줄 `journalctl` 에서 로그를 볼 수 있습니다.

```console
sudo journalctl -u myapp
```

> [!TIP]
> 호스트에서 사용할 수 있는 GUI 환경이 있는 경우 *QJournalctl* 및 *gnome* 와 같은 몇 가지 그래픽 로그 뷰어를 Linux에서 사용할 수 있습니다.

를 사용 하 여 명령줄에서 저널을 쿼리 하는 방법에 대 한 자세한 내용은 `systemd` `journalctl` 참조 [페이지](https://manpages.debian.org/buster/systemd/journalctl.1)를 참조 하세요.

## <a name="https-certificates-for-self-hosted-applications"></a>자체 호스팅 응용 프로그램에 대 한 HTTPS 인증서

프로덕션 환경에서 gRPC 응용 프로그램을 실행 하는 경우 신뢰할 수 있는 CA (인증 기관)의 TLS 인증서를 사용 해야 합니다. 이 CA는 공용 CA 또는 조직에 대 한 내부 ca 일 수 있습니다.

Windows 호스트에서는 클래스를 사용 하 여 보안 [인증서 저장소](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) 에서 인증서를 로드할 수 있습니다 <xref:System.Security.Cryptography.X509Certificates.X509Store> . 또한 `X509Store` 일부 Linux 호스트에서 OpenSSL 키 저장소와 함께 클래스를 사용할 수 있습니다.

[X509Certificate2 생성자](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)중 하나를 사용 하 여 다음과 같은 방법으로 인증서를 만들 수도 있습니다.

* 파일 (예: `.pfx` 강력한 암호로 보호 되는 파일)
* [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) 와 같은 보안 저장소 서비스에서 검색 된 이진 데이터

구성 또는 코드에서와 같은 두 가지 방법으로 인증서를 사용 하도록 Kestrel을 구성할 수 있습니다.

### <a name="set-https-certificates-by-using-configuration"></a>구성을 사용 하 여 HTTPS 인증서 설정

구성 방법에서는 `.pfx` Kestrel 구성 섹션에서 인증서 파일의 경로와 암호를 설정 해야 합니다. 에서 `appsettings.json` 다음과 같이 표시 됩니다.

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

Azure Key Vault 또는 Hashicorp Vault와 같은 보안 구성 원본을 사용 하 여 암호를 제공 합니다.

> [!IMPORTANT]
> 암호화 되지 않은 암호를 구성 파일에 저장 하지 않습니다.

### <a name="set-https-certificates-in-code"></a>코드에서 HTTPS 인증서 설정

코드에서 Kestrel에 HTTPS를 구성 하려면 `ConfigureKestrel` 클래스의에서 메서드를 사용 `IWebHostBuilder` `Program` 합니다.

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

다시, 보안 구성 원본에서 파일의 암호를 저장 하 `.pfx` 고 검색 해야 합니다.

>[!div class="step-by-step"]
>[이전](grpc-in-production.md)
>[다음](docker.md)
