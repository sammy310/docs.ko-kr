---
title: Windows, Linux 및 macOS에 .NET Core SDK 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 개발하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4a6c8b27812e9f60e52132169dda0464c24abcc2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740571"
---
# <a name="install-the-net-core-sdk"></a>.NET Core SDK 설치

이 문서에서는 .NET Core SDK를 설치하는 방법을 알아봅니다. .NET Core SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다. .NET Core 런타임은 항상 SDK와 함께 설치됩니다.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>설치 프로그램을 사용하여 설치

Windows에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.

- [x64(64비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86(32비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>설치 프로그램을 사용하여 설치

macOS에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.

- [x64(64비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>패키지 관리자를 사용하여 설치

널리 사용되는 여러 Linux 패키지 관리자를 사용하여 .NET Core SDK를 설치할 수 있습니다. 자세한 내용은 [Linux 패키지 관리자 - .NET Core 설치](linux-package-managers.md)를 참조하세요.

패키지 관리자를 사용한 설치는 x64 아키텍처에서만 지원됩니다. ARM과 같은 다른 아키텍처를 사용하여 .NET Core SDK를 설치하는 경우 아래 지침을 [다운로드하고 수동으로 설치](#download-and-manually-install)합니다. 지원되는 아키텍처에 대한 자세한 내용은 [.NET Core 종속성 및 요구 사항](dependencies.md)을 참조하세요.

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

SDK를 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다. 그런 다음 터미널을 열고 다음 명령을 실행합니다.

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> 이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET Core CLI 명령을 사용할 수 있도록 만듭니다.
>
> 셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다. 몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다. 예:
>
> - **Bash 셸**: *~/.bash_profile*, *~/.bashrc*
> - **Korn 셸**: *~/.kshrc* 또는 *.profile*
> - **Z 셸**: *~/.zshrc* 또는 *.zprofile*
>
> 셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다. 포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.
>
> 또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>Visual Studio를 사용하여 설치

Visual Studio를 사용하여 .NET Core 앱을 개발하는 경우, 다음 표에서 대상 .NET Core SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.

| .NET Core SDK 버전 | Visual Studio 버전                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 버전 16.4 이상 |
| 3.0                   | Visual Studio 2019 버전 16.3 이상 |
| 2.2                   | Visual Studio 2017 버전 15.9 이상 |
| 2.1                   | Visual Studio 2017 버전 15.7 이상 |

Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.

01. Visual Studio를 엽니다.
01. **도움말** > **Microsoft Visual Studio 정보**를 선택합니다.
01. **정보** 대화 상자에서 버전 번호를 확인합니다.

Visual Studio가 최신 .NET Core SDK 및 런타임을 설치할 수 있습니다.

- [Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.

### <a name="select-a-workload"></a>워크로드 선택

Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.

- **기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드
- **웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드
- **웹 및 클라우드** 섹션의 **Azure 개발** 워크로드
- **데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드

[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Mac용 Visual Studio를 사용하여 설치

Mac용 Visual Studio는 **.NET Core** 워크로드가 선택된 경우 .NET Core SDK를 설치합니다. macOS에서 .NET Core 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요. 최신 릴리스인 .NET Core 3.1의 경우 Mac용 Visual Studio 8.4 미리 보기를 사용해야 합니다.

[![macOS Mac용 Visual Studio 2019 및 .NET Core 워크로드의 특징](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>Visual Studio Code와 함께 설치

Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다. Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.

Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.

01. [Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).
01. [.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).
01. [Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>PowerShell 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. .NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>배시 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. .NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>모든 .NET Core 다운로드

다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.

- [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [.NET Core 3.0 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [.NET Core 2.2 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다. 동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.

.NET Core는 Docker 컨테이너에서 실행할 수 있습니다. 공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다. 각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.

Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다. 예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.

Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.

## <a name="next-steps"></a>다음 단계

::: zone pivot="os-windows"

- [자습서: Hello World 자습서](../tutorials/with-visual-studio.md)
- [자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)
- [자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)

::: zone-end

::: zone pivot="os-macos"

- [자습서: macOS에서 시작](../tutorials/using-on-mac-vs.md)
- [자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)
- [자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)

::: zone-end

::: zone pivot="os-linux"

- [자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)
- [자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)

::: zone-end
