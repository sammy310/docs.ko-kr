---
ms.openlocfilehash: 83808f2f3a05333ed5d9e3809cbc2fd6e230d02c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031783"
---

[.NET Core는 Snap 스토어에서 제공됩니다.](https://snapcraft.io/dotnet-sdk)

Snap은 다양한 Linux 배포판에서 수정하지 않고도 작동하는 앱의 번들이자 종속성입니다. Snap은 Snap 스토어에서 검색해서 설치할 수 있습니다. Snap에 대한 자세한 내용은 [Snap 시작하기](https://snapcraft.io/docs/getting-started)를 참조하세요.

지원되는 버전의 .NET Core만 Snap을 통해 사용할 수 있습니다.

### <a name="install-the-sdk"></a>SDK 설치

.NET SDK용 스냅 패키지는 모두 동일한 식별자 `dotnet-sdk`로 게시됩니다. 특정 버전의 SDK는 채널을 지정하여 설치할 수 있습니다. SDK에는 해당 런타임이 포함됩니다. 다음 표에서는 채널 목록을 보여 줍니다.

| .NET 버전 | 맞춤 패키지             |
|--------------|--------------------------|
| 5.0          | `5.0` 또는 `latest/stable` |
| 3.1(LTS)    | `3.1` 또는 `lts/stable`    |
| 2.1(LTS)    | `2.1`                    |

`snap install` 명령을 사용하여 .NET SDK 스냅 패키지를 설치합니다. `--channel` 매개 변수를 사용하여 설치할 버전을 지정합니다. 이 매개 변수를 생략하면 `latest/stable`이 사용됩니다. 이 예에서는 `5.0`이 지정되었습니다.

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다. 원하는 `{alias}` 이름을 선택할 수 있습니다. 예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-sdk.dotnet dotnet50`). `dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다. 그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.

### <a name="install-the-runtime"></a>런타임 설치

.NET Core 런타임에 대한 맞춤 패키지는 각각 자체 패키지 식별자에 따라 게시됩니다. 다음 표에는 패키지 식별자가 나열되어 있습니다.

| .NET 버전      | 맞춤 패키지        |
|-------------------|---------------------|
| 5.0               | `dotnet-runtime-50` |
| 3.1(LTS)         | `dotnet-runtime-31` |
| 3.0               | `dotnet-runtime-30` |
| 2.2               | `dotnet-runtime-22` |
| 2.1(LTS)         | `dotnet-runtime-21` |

`snap install` 명령을 사용하여 .NET 런타임 스냅 패키지를 설치합니다. 이 예제에서는 .NET 5.0이 설치됩니다.

```bash
sudo snap install dotnet-runtime-50 --classic
```

다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다. 원하는 `{alias}` 이름을 선택할 수 있습니다. 예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`). `dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다. 그러나, 이는 `dotnet` 명령에서 기대하는 바와 같이 대부분의 자습서와 예시에서는 호환되지 않습니다.

### <a name="ssl-certificate-errors"></a>SSL 인증서 오류

Snap을 통해 .NET가 설치될 경우, 일부 배포판에서는 .NET SSL 인증서를 찾을 수 없고 `restore` 도중에 다음과 유사한 오류를 받게 될 수 있습니다.

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

이 문제를 해결하려면 다음과 같은 몇 가지 환경 변수를 설정합니다.

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

인증서 위치는 배포판에 따라 달라집니다. 문제가 발생한 배포판의 위치는 다음과 같습니다.

* Fedora - `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
* OpenSUSE - `/etc/ssl/ca-bundle.pem`
* Solus - `/etc/ssl/certs/ca-certificates.crt`
