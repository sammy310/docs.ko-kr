---
title: Linux에서 .NET 수동 설치 - .NET
description: Linux에서 패키지 관리자 없이 .NET SDK 및 .NET 런타임을 설치하는 방법을 보여 줍니다. 설치 스크립트를 사용하거나 이진 파일을 수동으로 추출합니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 5879d4d66aba8bfa00caadbe3c33d6df0d7da59a
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970930"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a>수동으로 .NET SDK 또는 .NET 런타임 설치

.NET은 Linux에서 지원되며 이 문서에서는 설치 스크립트를 사용하거나 이진 파일을 추출하여 Linux에 .NET을 설치하는 방법을 설명합니다. 기본 제공 패키지 관리자를 지원하는 배포 목록은 [Linux에서 .NET 설치](linux.md)를 참조하세요.

Snap을 사용하여 .NET을 설치할 수도 있습니다. 자세한 내용은 [Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치](linux-snap.md)를 참조하세요.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a>.NET 릴리스

다음 표에는 .NET 및 .NET Core 릴리스가 나열되어 있습니다.

| ✔️ 지원됨 | ❌ 지원 안 됨 |
|-------------|---------------|
| 5.0         | 3.0           |
| 3.1(LTS)   | 2.2           |
| 2.1(LTS)   | 2.0           |
|             | 1.1           |
|             | 1.0           |

.NET 릴리스의 수명 주기에 대한 자세한 내용은 [.NET Core 및 .NET 5 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.

## <a name="dependencies"></a>종속성

.NET을 설치할 때 특정 종속성이 설치되지 않을 수 있습니다(예: [수동으로 설치](#manual-install)하는 경우). 다음 목록에서는 Microsoft에서 지원하며, 설치해야 할 수 있는 종속성이 있는 Linux 배포판에 대해 자세히 설명합니다. 자세한 내용은 배포 페이지를 확인하세요.

- [Alpine](linux-alpine.md#dependencies)
- [Debian](linux-debian.md#dependencies)
- [CentOS](linux-centos.md#dependencies)
- [Fedora](linux-fedora.md#dependencies)
- [RHEL](linux-rhel.md#dependencies)
- [SLES](linux-sles.md#dependencies)
- [Ubuntu](linux-ubuntu.md#dependencies)

종속성에 대한 일반적인 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.

### <a name="rpm-dependencies"></a>RPM 종속성

자신의 배포판이 위에 나열되지 않았으며 RPM 기반인 경우 다음 종속성이 필요할 수 있습니다.

- krb5-libs
- libicu
- openssl-libs

대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.

### <a name="deb-dependencies"></a>DEB 종속성

자신의 배포판이 위에 나열되지 않았으며 Debian 기반인 경우 다음 종속성이 필요할 수 있습니다.

- libc6
- libgcc1
- libgssapi-krb5-2
- libicu67
- libssl1.1
- libstdc++6
- zlib1g

### <a name="common-dependencies"></a>일반 종속성

*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.

- [libgdiplus(버전 6.0.1 이상)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > 시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다. 자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.

## <a name="scripted-install"></a>스크립팅된 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화와 **SDK** 및 **런타임** 의 관리자 설치가 아닌 일반 설치를 수행하는 데 사용됩니다. <https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 SDK [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. (LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current
```

SDK 대신 .NET 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다. 다음 명령은 .NET SDK 5.0을 설치합니다.

```bash
./dotnet-install.sh -c 5.0
```

자세한 내용은 [dotnet-install 스크립트 참조](../tools/dotnet-install-script.md)를 참조하세요.

## <a name="manual-install"></a>수동 설치

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

패키지 관리자의 대안으로, SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다. 수동 설치는 일반적으로 연속 통합 테스트의 일부로서 사용되거나 지원되지 않는 Linux 배포판에서 사용됩니다. 개발자 또는 사용자의 경우 패키지 관리자를 사용하는 것이 좋습니다.

.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. 먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.

- ✔️ [.NET 5.0 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [모든 .NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET에서 사용된 변수를 설정하고 .NET이 PATH에 있는지 확인합니다.

런타임을 추출하고 터미널에서 .NET CLI 명령을 사용할 수 있도록 하려면 먼저 .NET 이진 릴리스를 다운로드합니다. 그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다. 보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.

**다음 명령을 사용하여 런타임을 추출합니다.**

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**다음 명령을 사용하여 SDK를 추출합니다.**

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> 이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET CLI 명령을 사용할 수 있도록 만듭니다.
>
> 셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다. 몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다. 예를 들어:
>
> - **Bash 셸**: *~/.bash_profile*, *~/.bashrc*
> - **Korn 셸**: *~/.kshrc* 또는 *.profile*
> - **Z 셸**: *~/.zshrc* 또는 *.zprofile*
>
> 셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다. 포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.
>
> 또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.

이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법](../tools/enable-tab-autocomplete.md)
- [자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기](../tutorials/with-visual-studio-code.md)
