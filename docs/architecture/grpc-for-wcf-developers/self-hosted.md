---
title: 자체 호스팅 gRPC 응용 프로그램 - WCF 개발자를 위한 gRPC
description: ASP.NET 코어 gRPC 애플리케이션을 자체 호스팅 서비스로 배포합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147804"
---
# <a name="self-hosted-grpc-applications"></a>자체 호스팅 gRPC 응용 프로그램

ASP.NET Core 3.0 응용 프로그램은 Windows Server의 IIS에서 호스팅할 수 있지만 현재 는 일부 HTTP/2 기능이 지원되지 않으므로 IIS에서 gRPC 응용 프로그램을 호스팅할 수 없습니다. 이 기능은 Windows Server에 대한 향후 업데이트의 목표입니다.

응용 프로그램을 Windows 서비스로 실행할 수 있습니다. 또는 .NET Core 3.0 호스팅 확장의 새로운 기능으로 인해 [systemd에](https://en.wikipedia.org/wiki/Systemd)의해 제어되는 Linux 서비스로 실행할 수 있습니다.

## <a name="run-your-app-as-a-windows-service"></a>Windows 서비스로 앱 실행

ASP.NET 핵심 응용 프로그램을 Windows 서비스로 실행하도록 구성하려면 NuGet에서 [Microsoft.Extensions.Hosting.WindowsServices 패키지를 설치합니다.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) 그런 다음 에서 `UseWindowsService` 메서드에 대한 호출을 `CreateHostBuilder` 추가합니다. `Program.cs`

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
> 응용 프로그램이 Windows 서비스로 실행되지 않는 `UseWindowsService` 경우 메서드는 아무 것도 수행하지 않습니다.

이제 다음 방법 중 하나를 사용하여 응용 프로그램을 게시합니다.

* 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **게시를** 선택하여 Visual Studio에서.
* .NET 코어 CLI에서.

.NET Core 응용 프로그램을 게시할 때 *프레임워크 종속* 배포 또는 *독립형* 배포를 만들도록 선택할 수 있습니다. 프레임워크 종속 배포에서는 .NET Core 공유 런타임을 실행되는 호스트에 설치해야 합니다. 독립형 배포는 .NET Core 런타임 및 프레임워크의 전체 복사본과 함께 게시되며 모든 호스트에서 실행할 수 있습니다. 각 접근 방식의 장점과 단점을 포함하여 자세한 내용은 [.NET Core 응용 프로그램 배포](../../core/deploying/index.md) 설명서를 참조하십시오.

.NET Core 3.0 런타임을 호스트에 설치할 필요가 없는 독립형 응용 프로그램 빌드를 게시하려면 응용 프로그램에 포함할 런타임을 지정합니다. (또는) `-r` `--runtime`플래그를 사용합니다.

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

프레임워크 종속 빌드를 게시하려면 플래그를 생략합니다. `-r`

```dotnetcli
dotnet publish -c Release -o ./publish
```

`publish` 디렉터리 전체 내용을 설치 폴더에 복사합니다. 그런 다음 [sc 도구를](/windows/desktop/services/controlling-a-service-using-sc) 사용하여 실행 파일에 대한 Windows 서비스를 만듭니다.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Windows 이벤트 로그에 로그

메서드는 `UseWindowsService` Windows 이벤트 로그에 로그 메시지를 쓰는 [로깅](/aspnet/core/fundamentals/logging/) 공급자를 자동으로 추가합니다. 이 공급자의 섹션 `EventLog` `Logging` `appsettings.json` 또는 다른 구성 원본에 항목을 추가하여 이 공급자에 대한 로깅을 구성할 수 있습니다.

이러한 설정에서 속성을 설정하여 이벤트 로그에 `SourceName` 사용된 소스 이름을 재정의할 수 있습니다. 이름을 지정하지 않으면 기본 응용 프로그램 이름(일반적으로 실행 가능한 어셈블리 이름)이 사용됩니다.

로깅에 대한 자세한 내용은 이 장의 끝에 있습니다.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>systemd를 통해 Linux 서비스로 앱을 실행

리눅스 서비스 (또는 리눅스 용어의 *데몬)로* 실행하도록 ASP.NET 코어 응용 프로그램을 구성하려면 NuGet에서 [Microsoft.Extensions.Hostings.Systemd 패키지를 설치합니다.](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) 그런 다음 에서 `UseSystemd` 메서드에 대한 호출을 `CreateHostBuilder` 추가합니다. `Program.cs`

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
> 응용 프로그램이 Linux 서비스로 실행되지 않는 `UseSystemd` 경우 메서드는 아무 것도 수행하지 않습니다.

이제 응용 프로그램을 게시합니다. 응용 프로그램은 관련 Linux 런타임(예: `linux-x64`)에 대해 프레임워크에 종속되거나 자체 포함될 수 있습니다. 다음 방법 중 하나를 사용하여 게시할 수 있습니다.

* 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **게시를** 선택하여 Visual Studio에서.
* .NET 코어 CLI에서 다음 명령을 사용하여 다음 명령을 수행합니다.

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
`publish` 디렉터리 전체 내용을 Linux 호스트의 설치 폴더에 복사합니다. 서비스를 등록하려면 디렉터리에 단위 파일이라는 특수 *파일이* `/etc/systemd/system` 필요합니다. 이 폴더에서 파일을 만들려면 루트 권한이 필요합니다. 사용할 식별자와 `systemd` 확장자를 사용하여 파일의 `.service` 이름을 지정합니다. 예를 들면 `/etc/systemd/system/myapp.service`를 사용합니다.

서비스 파일은 이 예제와 같이 INI 형식을 사용합니다.

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

속성은 `Type=notify` `systemd` 응용 프로그램이 시작 및 종료시 이를 알립니다. 이 `WantedBy=multi-user.target` 설정은 Linux 시스템이 "런레벨 2"에 도달하면 서비스가 시작되며, 이는 그래픽이 아닌 다중 사용자 셸이 활성화되어 있다는 것을 의미합니다.

서비스를 `systemd` 인식하기 전에 구성을 다시 로드해야 합니다. 명령을 `systemd` 사용하여 제어합니다. `systemctl` 다시 로드한 후 `status` 하위 명령을 사용하여 응용 프로그램이 성공적으로 등록되었는지 확인합니다.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

서비스를 올바르게 구성한 경우 다음과 같은 출력을 얻을 수 있습니다.

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

`start` 명령을 사용하여 서비스를 시작합니다.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> `.service` 을 사용할 `systemctl start`때 확장은 선택 사항입니다.

시스템 `systemd` 시작 시 서비스를 자동으로 시작하도록 지시하려면 `enable` 명령을 사용합니다.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>저널로 로그

Windows 이벤트 로그에 해당하는 `journald`Linux는 `systemd`의 일부인 구조화 된 로깅 시스템 서비스입니다. Linux 데몬의 표준 출력에 기록된 로그 `journald`메시지는 에 자동으로 기록됩니다. 로깅 수준을 구성하려면 `Console` 로깅 구성의 섹션을 사용합니다. 호스트 `UseSystemd` 빌더 메서드는 저널에 맞게 콘솔 출력 형식을 자동으로 구성합니다.

리눅스 로그의 표준이기 때문에 `journald` 다양한 도구가 통합됩니다. 로그를 외부 로깅 `journald` 시스템으로 쉽게 라우팅할 수 있습니다. 호스트에서 로컬로 작업하면 `journalctl` 명령을 사용하여 명령줄에서 로그를 볼 수 있습니다.

```console
sudo journalctl -u myapp
```

> [!TIP]
> 호스트에서 사용할 수 있는 GUI 환경이 있는 경우 *QJournalctl* 및 *그놈 로그와*같은 몇 가지 그래픽 로그 뷰어를 Linux에서 사용할 수 있습니다.

명령줄에서 `systemd` 저널을 쿼리하는 `journalctl`방법에 대해 자세히 알아보려면 man [페이지를](https://manpages.debian.org/buster/systemd/journalctl.1)참조하십시오.

## <a name="https-certificates-for-self-hosted-applications"></a>자체 호스팅 응용 프로그램에 대한 HTTPS 인증서

프로덕션 환경에서 gRPC 응용 프로그램을 실행하는 경우 신뢰할 수 있는 인증 기관(CA)의 TLS 인증서를 사용해야 합니다. 이 CA는 공용 CA이거나 조직의 내부 CA일 수 있습니다.

Windows 호스트에서 클래스를 사용하여 보안 [인증서 저장소에서](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) <xref:System.Security.Cryptography.X509Certificates.X509Store> 인증서를 로드할 수 있습니다. 일부 Linux 호스트에서 `X509Store` OpenSSL 키 저장소에서 클래스를 사용할 수도 있습니다.

다음 중 하나에서 [X509Certificate2 생성자](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)중 하나를 사용하여 인증서를 만들 수도 있습니다.

* 강력한 암호로 보호되는 `.pfx` 파일과 같은 파일
* [Azure 키 볼트와](https://azure.microsoft.com/services/key-vault/) 같은 보안 저장소 서비스에서 검색된 이진 데이터

Kestrel은 구성 또는 코드의 두 가지 방법으로 인증서를 사용하도록 구성할 수 있습니다.

### <a name="set-https-certificates-by-using-configuration"></a>구성을 사용하여 HTTPS 인증서 설정

구성 접근 방식을 사용하려면 Kestrel 구성 섹션의 인증서 `.pfx` 파일 및 암호에 대한 경로를 설정해야 합니다. 에서 `appsettings.json`다음과 같이 보입니다.

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

Azure 키 볼트 또는 Hashicorp 볼트와 같은 보안 구성 원본을 사용하여 암호를 제공합니다.

> [!IMPORTANT]
> 암호화되지 않은 암호를 구성 파일에 저장하지 마십시오.

### <a name="set-https-certificates-in-code"></a>코드에서 HTTPS 인증서 설정

코드에서 Kestrel에서 HTTPS를 구성하려면 `ConfigureKestrel` `IWebHostBuilder` `Program` 클래스에서 메서드를 사용합니다.

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

다시 `.pfx` 말하지만, 파일에 대한 암호를 저장하고 보안 구성 소스에서 검색해야합니다.

>[!div class="step-by-step"]
>[이전](grpc-in-production.md)
>[다음](docker.md)
