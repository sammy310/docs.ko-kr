---
title: macOS에 .NET Core 설치
description: .NET Core를 설치할 수 있는 macOS 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: bb1a0fa24e2f6e8850cbe59378793ff846f04ba9
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804454"
---
# <a name="install-net-core-on-macos"></a>macOS에 .NET Core 설치

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

이 문서에서는 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core는 런타임과 SDK로 구성됩니다. 런타임은 .NET Core 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다. SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다. .NET Core 런타임은 항상 SDK와 함께 설치됩니다.

최신 버전의 .NET Core는 3.1입니다.

[.NET Core를 다운로드합니다.](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>지원되는 릴리스

다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 macOS 버전의 목록입니다. 이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)할 때까지 계속 지원됩니다.

- ✔️는 .NET Core 버전이 계속 지원됨을 나타냅니다.
- ❌️는 .NET Core 버전이 지원되지 않음을 나타냅니다.

| 운영 체제          | .NET Core 2.1 | .NET Core 3.1 | .NET 5 미리 보기 |
|---------------------------|---------------|---------------|----------------|
| macOS 10.15 “Catalina”    | ✔️ 2.1([릴리스 정보][release-notes-21]) | ✔️ 3.1([릴리스 정보][release-notes-31]) | ✔️ 5.0 미리 보기([릴리스 정보][release-notes-50]) |
| macOS 10.14 “Mojave”      | ✔️ 2.1([릴리스 정보][release-notes-21]) | ✔️ 3.1([릴리스 정보][release-notes-31]) | ✔️ 5.0 미리 보기([릴리스 정보][release-notes-50]) |
| macOS 10.13 “High Sierra” | ✔️ 2.1([릴리스 정보][release-notes-21]) | ✔️ 3.1([릴리스 정보][release-notes-31]) | ✔️ 5.0 미리 보기([릴리스 정보][release-notes-50]) |
| macOS 10.12 "Sierra"      | ✔️ 2.1([릴리스 정보][release-notes-21]) | ❌ 3.1([릴리스 정보][release-notes-31]) | ❌ 5.0 미리 보기([릴리스 정보][release-notes-50]) |

## <a name="unsupported-releases"></a>지원되지 않는 릴리스

다음 .NET Core 버전은 ❌ 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0([릴리스 정보][release-notes-30])
- 2.2([릴리스 정보][release-notes-22])
- 2.0([릴리스 정보][release-notes-20])

## <a name="runtime-information"></a>런타임 정보

런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다. 앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다. 앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.

macOS에 설치할 수 있는 세 가지 런타임이 있습니다.

‘ASP.NET Core 런타임’\
ASP.NET Core 앱을 실행합니다. .NET Core 런타임을 포함합니다.

‘.NET Core 런타임’\
이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다. .NET Core 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’을 설치하는 것이 좋습니다.

[.NET Core 런타임 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>SDK 정보

SDK는 .NET Core 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다. SDK를 설치하면 ASP.NET Core 및 .NET Core의 두 가지 [런타임](#runtime-information)이 모두 포함됩니다.

[.NET Core SDK 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>종속성

.NET Core는 다음과 같은 macOS 릴리스에서 지원됩니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| .NET Core 버전 | macOS                 | 아키텍처 |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra(10.13+)  | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra(10.13+)  | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra(10.12+)       | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra(10.12+)       | X64 | [추가 정보](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다. 이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다.

.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다. 그 전에 릴리스된 버전은 공증되지 않았습니다. 공증되지 않은 앱을 실행하면 다음 이미지와 비슷한 오류가 표시됩니다.

![macOS Catalina 공증 경고](media/dependencies/macos-notarized-pkg-warning.png)

공증 요구 사항이 적용됨에 따라 .NET Core(및 .NET Core 앱)에 미치는 영향에 대해 자세히 알아보려면 [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)을 참조하세요.

## <a name="libgdiplus"></a>libgdiplus

*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 애플리케이션을 설치하려면 libgdiplus가 필요합니다.

libgdiplus를 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다. *brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 libgdiplus를 설치합니다.

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a>설치 프로그램을 사용하여 설치

macOS에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.

- [x64(64비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

.NET Core용 macOS 설치 프로그램의 대안으로, SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다. 수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다. 개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.

.NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. 먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.

- ✔️ [.NET 5.0 미리보기 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [모든 .NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET Core에서 사용된 변수를 설정하고 .NET Core가 경로에 있는지 확인합니다.

런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 다운로드합니다. 그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다. 보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.

**다음 명령을 사용하여 런타임을 추출합니다.**

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**다음 명령을 사용하여 SDK를 추출합니다.**

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> 이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET Core CLI 명령을 사용할 수 있도록 만듭니다.
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

## <a name="install-with-visual-studio-for-mac"></a>Mac용 Visual Studio를 사용하여 설치

Mac용 Visual Studio는 **.NET Core** 워크로드가 선택된 경우 .NET Core SDK를 설치합니다. macOS에서 .NET Core 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요. 최신 릴리스인 .NET Core 3.1의 경우 Mac용 Visual Studio 8.4 미리 보기를 사용해야 합니다.

[![macOS Mac용 Visual Studio 2019 및 .NET Core 워크로드의 특징](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Visual Studio Code와 함께 설치

Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다. Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.

Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.

01. [Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).
01. [.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).
01. [Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="install-with-bash-automation"></a>배시 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. `current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다. 런타임을 설치하려면 `runtime` 스위치를 포함합니다. 포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> 위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다. ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.

## <a name="docker"></a>Docker

컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다. 동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.

.NET Core는 Docker 컨테이너에서 실행할 수 있습니다. 공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다. 각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.

Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다. 예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.

Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.

## <a name="next-steps"></a>다음 단계

- [.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-macos)
- [macOS Catalina 공증 관련 사항](macos-notarization-issues.md)
- [자습서: macOS에서 시작](../tutorials/using-on-mac-vs.md)
- [자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)
- [자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
