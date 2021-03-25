---
title: Snap을 사용하여 Linux에 .NET 설치 - .NET
description: Snap을 사용하여 Linux에 .NET SDK 또는 .NET 런타임을 설치하는 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 0d91f5049c92df240e2c3e26bc67952abe17fedc
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190101"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a>Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치

Snap 패키지를 사용하여 .NET SDK 또는 .NET 런타임을 설치합니다. Snap은 Linux 배포에 기본 제공되는 패키지 관리자의 좋은 대안입니다. 이 문서에서는 [Snap](https://snapcraft.io/dotnet-sdk)을 통해 .NET을 설치하는 방법을 설명합니다.

Snap은 다양한 Linux 배포판에서 수정하지 않고도 작동하는 앱의 번들이자 종속성입니다. Snap은 Snap 스토어에서 검색해서 설치할 수 있습니다. Snap에 대한 자세한 내용은 [Snap 시작하기](https://snapcraft.io/docs/getting-started)를 참조하세요.

> [!CAUTION]
> Snap 패키지는 Windows 10의 WSL2에서 지원되지 않습니다. 이에 대한 대안으로, 특정 WSL2 배포를 위해 [`dotnet-install` 스크립트](linux-scripted-manual.md#scripted-install) 또는 패키지 관리자를 사용할 수 있습니다. 권장되지는 않지만 [snapcraft 포럼에서 지원되지 않는 해결 방법](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033)을 사용하여 Snap을 사용하도록 설정해 볼 수 있습니다.

## <a name="net-releases"></a>.NET 릴리스

✔️ 지원되는 버전의 .NET SDK만 Snap을 통해 사용할 수 있습니다. 버전 2.1부터 Snap을 통해 모든 버전의 .NET 런타임을 사용할 수 있습니다. 다음 표에는 .NET 및 .NET Core 릴리스가 나열되어 있습니다.

| ✔️ 지원됨 | ❌ 지원 안 됨 |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1(LTS)   | 2.2           |
| 2.1(LTS)   | 2.0           |
|             | 1.1           |
|             | 1.0           |

.NET 릴리스의 수명 주기에 대한 자세한 내용은 [.NET Core 및 .NET 5 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.

## <a name="sdk-or-runtime"></a>SDK 또는 런타임

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a>SDK 설치

.NET SDK용 Snap 패키지는 모두 동일한 식별자 `dotnet-sdk`로 게시됩니다. 특정 버전의 SDK는 채널을 지정하여 설치할 수 있습니다. SDK에는 해당 런타임이 포함됩니다. 다음 표에서는 채널 목록을 보여 줍니다.

| .NET 버전 | Snap 패키지 또는 채널  |
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

이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다. 원하는 `{alias}` 이름을 선택할 수 있습니다. 예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-sdk.dotnet dotnet50`). `dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다. 그러나 다른 별칭을 선택할 경우 `dotnet` 명령이 사용될 것으로 예상하는 대부분의 자습서 및 예제와 호환되지 않습니다.

## <a name="install-the-runtime"></a>런타임 설치

.NET 런타임용 Snap 패키지는 각각 자체 패키지 식별자로 게시됩니다. 다음 표에는 패키지 식별자가 나열되어 있습니다.

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

이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다. 원하는 `{alias}` 이름을 선택할 수 있습니다. 예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`). `dotnet50` 명령을 사용할 경우 특정 버전의 .NET이 호출됩니다. 그러나 다른 별칭을 선택할 경우 `dotnet` 명령이 사용 가능할 것으로 예상하는 대부분의 자습서 및 예제와 호환되지 않습니다.

## <a name="export-the-install-location"></a>설치 위치 내보내기

`DOTNET_ROOT` 환경 변수는 도구에서 .NET이 설치된 위치를 확인하는 데 자주 사용됩니다. .NET이 Snap을 통해 설치되면 이 환경 변수는 구성되지 않습니다. 프로필에서 *DOTNET_ROOT* 환경 변수를 구성해야 합니다. 스냅 경로는 `/snap/{package}/current` 형식을 사용합니다. 예를 들어 `dotnet-sdk` 스냅을 설치한 경우 다음 명령을 사용하여 환경 변수를 .NET이 있는 위치로 설정합니다.

```bash
export DOTNET_ROOT=/snap/dotnet-sdk/current
```

> [!TIP]
> 앞의 `export` 명령은 실행된 터미널 세션에 대한 환경 변수만 설정합니다.
>
> 셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다. 몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다. 예를 들어:
>
> - **Bash 셸**: *~/.bash_profile*, *~/.bashrc*
> - **Korn 셸**: *~/.kshrc* 또는 *.profile*
> - **Z 셸**: *~/.zshrc* 또는 *.zprofile*
>
> 셸에 적절한 원본 파일을 편집하고 `export DOTNET_ROOT=/snap/dotnet-sdk/current`를 추가합니다.

## <a name="tlsssl-certificate-errors"></a>TLS/SSL 인증서 오류

Snap을 통해 .NET이 설치될 경우, 일부 배포판에서는 .NET TLS/SSL 인증서가 발견되지 않을 수 있으며 `restore` 도중에 오류가 발생할 수 있습니다.

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

| 배포 | 위치                                            |
|--------------|-----------------------------------------------------|
| **Fedora**   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| **OpenSUSE** | `/etc/ssl/ca-bundle.pem`                            |
| **Solus**    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a>다음 단계

- [.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법](../tools/enable-tab-autocomplete.md)
- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
