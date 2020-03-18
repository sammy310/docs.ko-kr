---
title: Windows, Linux 및 macOS에 .NET Core 런타임 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 실행하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca55b8fab4aa9ca9f7e308cce57181e2c7e89f4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397964"
---
# <a name="install-the-net-core-runtime"></a>.NET Core 런타임 설치

이 문서에서는 .NET Core 런타임을 다운로드하고 설치하는 방법을 알아봅니다. .NET Core 런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>설치 프로그램을 사용하여 설치

Windows에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.

- [x64(64비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86(32비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>설치 프로그램을 사용하여 설치

macOS에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.

- [x64(64비트) CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

.NET Core용 macOS 설치 프로그램의 대안으로, 런타임을 다운로드하여 수동으로 설치할 수 있습니다.

런타임을 실행하고 터미널에서 사용 가능한 .NET Core CLI 명령을 사용하도록 설정하려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다. 그런 다음 터미널을 열고 다음 명령을 실행합니다. 런타임이 `~/Downloads/dotnet-runtime.pkg` 파일로 다운로드되었다고 가정합니다.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>패키지 관리자를 사용하여 설치

널리 사용되는 여러 Linux 패키지 관리자를 사용하여 .NET Core 런타임을 설치할 수 있습니다. 자세한 내용은 [Linux 패키지 관리자 - .NET Core 설치](linux-package-managers.md)를 참조하세요.

패키지 관리자를 사용한 설치는 x64 아키텍처에서만 지원됩니다. ARM과 같은 다른 아키텍처를 사용하여 .NET Core 런타임을 설치하는 경우 [다운로드 및 수동 설치](#download-and-manually-install) 섹션의 지침을 따릅니다. 지원되는 아키텍처에 대한 자세한 내용은 [.NET Core 종속성 및 요구 사항](dependencies.md)을 참조하세요.

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다. 그런 다음 터미널을 열고 다음 명령을 실행합니다.

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
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

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>PowerShell 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. `Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다. 런타임을 설치하려면 `Runtime` 스위치를 포함합니다. 포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> 위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다. ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다. 그런 다음 `%USERPROFILE%\dotnet`와 같이 설치할 디렉터리를 만듭니다. 마지막으로 다운로드한 zip 파일을 그 디렉터리로 추출합니다.

기본적으로 .NET Core CLI 명령과 앱은 이러한 방식으로 설치된 .NET Core를 사용하지 않습니다. 이를 사용하려면 명시적으로 선택해야 합니다. 이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.

이러한 환경 변수가 설정된 경우에도 .NET Core는 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 계속 고려합니다. 기본값은 일반적으로 설치 프로그램이 사용하는 `C:\Program Files\dotnet`입니다. 이 환경 변수를 설정하여 사용자 지정 설치 위치만 사용하도록 런타임에 지시할 수도 있습니다.

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>배시 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. `current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다. 런타임을 설치하려면 `runtime` 스위치를 포함합니다. 포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> 위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다. ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.

::: zone-end

## <a name="all-net-core-downloads"></a>모든 .NET Core 다운로드

다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.

- [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다. 동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.

.NET Core는 Docker 컨테이너에서 실행할 수 있습니다. 공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다. 각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.

Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다. 예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.

Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.

## <a name="next-steps"></a>다음 단계

- [.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md)
