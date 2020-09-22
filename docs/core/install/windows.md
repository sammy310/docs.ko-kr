---
title: Windows에 .NET Core 설치
description: .NET Core를 설치할 수 있는 Windows 버전에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 06/22/2020
ms.openlocfilehash: 12cffb78de803845a4b18adc70289993e67f64f1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538291"
---
# <a name="install-net-core-on-windows"></a>Windows에 .NET Core 설치

> [!div class="op_single_selector"]
>
> - [Windows에 설치](windows.md)
> - [macOS에 설치](macos.md)
> - [Linux에 설치](linux.md)

이 문서에서는 Windows에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core는 런타임과 SDK로 구성됩니다. 런타임은 .NET Core 앱을 실행하는 데 사용되며 앱에 포함되거나 포함되지 않을 수 있습니다. SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다. .NET Core 런타임은 항상 SDK와 함께 설치됩니다.

최신 버전의 .NET Core는 3.1입니다.

> [!div class="button"]
> [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>지원되는 릴리스

다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Windows 버전의 목록입니다. 이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 각 버전의 [Windows가 지원 종료에 도달](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)할 때까지 지원됩니다.

Windows 10 버전의 서비스 종료 날짜는 버전별로 분할됩니다. **Home**, **Pro**, **Pro Education** 및 **Pro for Workstations** 버전만 다음 표에서 다룹니다. 특정 세부 정보는 [Windows 수명 주기 팩트 시트](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)를 확인하세요.

- ✔️는 버전의 Windows 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.
- ❌는 Windows 또는 .NET Core 버전이 해당 Windows 릴리스에서 지원되지 않음을 나타냅니다.
- Windows 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.

| 운영 체제                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5 미리 보기 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ Windows 10, 버전 2004 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ Windows 10, 버전 1909 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ Windows 10, 버전 1903 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ✔️ Windows 10, 버전 1809 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1803 | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1709 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1703 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1607 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1511 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |
| ❌ Windows 10, 버전 1507 | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 미리 보기 |

## <a name="unsupported-releases"></a>지원되지 않는 릴리스

다음 .NET Core 버전은 ❌ 더 이상 지원되지 않습니다. 이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.

- 3.0
- 2.2
- 2.0

## <a name="runtime-information"></a>런타임 정보

런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다. 앱 작성자는 앱을 게시할 때 앱과 함께 런타임을 포함할 수 있습니다. 앱 작성자가 런타임을 포함하지 않는 경우, 사용자가 런타임을 설치할 수 있습니다.

Windows에 설치할 수 있는 세 가지 런타임이 있습니다.

‘ASP.NET Core 런타임’\
ASP.NET Core 앱을 실행합니다. .NET Core 런타임을 포함합니다.

‘데스크톱 런타임’\
Windows용 .NET Core WPF 및 .NET Core Windows Forms 데스크톱 앱을 실행합니다. .NET Core 런타임을 포함합니다.

‘.NET Core 런타임’\
이 런타임은 가장 간단한 런타임이며 다른 런타임을 포함하지 않습니다. .NET Core 앱과의 최상의 호환성을 위해 ‘ASP.NET Core 런타임’과 ‘데스크톱 런타임’을 모두 설치하는 것이 좋습니다. 

> [!div class="button"]
> [.NET Core 런타임 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>SDK 정보

SDK는 .NET Core 앱과 라이브러리를 빌드하고 게시하는 데 사용됩니다. SDK를 설치하면 ASP.NET Core, 데스크톱 및 .NET Core의 세 가지 [런타임](#runtime-information)이 모두 포함됩니다.

> [!div class="button"]
> [.NET Core SDK 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>종속성

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1609+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64, ARM32      |

.NET Core 3.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)(.NET Core 3.1이 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0은 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*

.NET Core 3.0이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2012 R2+                       | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64, ARM32      |

.NET Core 3.0이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)(.NET Core 3.0이 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2는 현재 지원되지 않습니다. 자세한 내용은 [.NET Core 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.*

.NET Core 2.2가 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 SP1+                   | x64, x86        |
| Nano 서버                   | 버전 1803+                   | x64, ARM32      |

.NET Core 2.2가 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)(.NET Core 2.2가 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1이 지원되는 Windows 버전은 다음과 같습니다.

> [!NOTE]
> `+` 기호는 최소 버전을 나타냅니다.

| OS                            | 버전                        | 아키텍처   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 클라이언트                | 7 SP1+, 8.1                    | x64, x86        |
| Windows 10 클라이언트             | 버전 1607+                  | x64, x86        |
| Windows Server                | 2008 R2 SP1+                   | x64, x86        |
| Nano 서버                   | 버전 1803+                  | x64,            |

.NET Core 2.1이 지원되는 운영 체제, 배포 및 수명 주기 정책에 대한 자세한 내용은 [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)(.NET Core 2.1이 지원되는 OS 버전)를 참조하세요.

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2

다음과 같은 Windows 버전에 .NET SDK 또는 런타임을 설치할 경우 추가 종속성이 필요합니다.

- ❌ Windows 7 SP1
- ❌ Windows Vista SP 2
- ✔️ Windows 8.1
- ✔️ Windows Server 2008 R2
- ✔️ Windows Server 2012 R2

다음을 설치합니다.

- [Microsoft Visual C++ 2015 재배포 가능 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

다음과 같은 오류가 발생할 경우에도 위 요구 사항이 요구됩니다.

> 컴퓨터에 *api-ms-win-crt-runtime-l1-1-0.dll*이(가) 없어 프로그램을 시작할 수 없습니다. 프로그램을 다시 설치하여 이 문제를 해결하세요.
>
> \- 또는 -
>
> 컴퓨터에 *api-ms-win-cor-timezone-l1-1-0.dll*이 없어 프로그램을 시작할 수 없습니다. 프로그램을 다시 설치하여 이 문제를 해결하세요.
>
> \- 또는 -
>
> 라이브러리 *hostfxr.dll*을 찾았으나, *C:\\\<path_to_app>\\hostfxr.dll*에서 로드하지 못했습니다.

## <a name="install-with-powershell-automation"></a>PowerShell 자동화를 사용하여 설치

[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 CI 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. 스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.

스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다. `Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다. 런타임을 설치하려면 `Runtime` 스위치를 포함합니다. 포함하지 않을 경우 스크립트가 SDK를 설치합니다.

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

`-Runtime` 스위치를 생략하여 SDK를 설치합니다. 이 예에서는 `-Channel` 스위치를 `Current`로 설정하여 최신 지원 버전을 설치합니다.

```powershell
dotnet-install.ps1 -Channel Current
```

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

> [!div class="button"]
> [Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.

### <a name="select-a-workload"></a>워크로드 선택

Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.

- **기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드
- **웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드
- **웹 및 클라우드** 섹션의 **Azure 개발** 워크로드
- **데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드

[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Visual Studio Code와 함께 설치

Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다. Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.

Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.

01. [Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).
01. [.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).
01. [Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="download-and-manually-install"></a>다운로드 및 수동으로 설치

.NET Core용 Windows 설치 프로그램의 대안으로, SDK나 런타임을 다운로드하여 수동으로 설치할 수 있습니다. 수동 설치는 일반적으로 연속 통합 테스트의 일부로 수행됩니다. 개발자 또는 사용자의 경우 일반적으로 [설치 관리자](https://dotnet.microsoft.com/download/dotnet-core)를 사용하는 것이 좋습니다.

.NET Core SDK와 .NET Core 런타임 모두 다운로드 후 수동으로 설치할 수 있습니다. .NET Core SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다. 먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 이진 릴리스를 다운로드합니다.

- ✔️ [.NET 5.0 미리보기 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [모든 .NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core)

.NET을 추출해서 넣을 디렉터리(예: `%USERPROFILE%\dotnet`)를 만듭니다. 그런 다음, 다운로드한 zip 파일을 이 디렉터리로 추출합니다.

기본적으로 .NET Core CLI 명령과 앱은 이런 방식으로 설치된 .NET Core를 사용하지 않으므로 명시적으로 사용을 선택해야 합니다. 이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.

`DOTNET_MULTILEVEL_LOOKUP`을 `0`으로 설정하면 .NET Core에서는 전역적으로 설치된 .NET Core 버전을 무시합니다. .NET Core에서 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 고려하도록 하려면 이러한 환경 설정을 제거합니다. 기본값은 일반적으로 `C:\Program Files\dotnet`입니다. 이 경로는 설치 관리자가 .NET Core를 설치하는 경로입니다.

## <a name="docker"></a>Docker

컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다. 동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.

.NET Core는 Docker 컨테이너에서 실행할 수 있습니다. 공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다. 각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.

Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다. 예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.

Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.

## <a name="next-steps"></a>다음 단계

- [.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md?pivots=os-windows)
- [자습서: Hello World 자습서](../tutorials/with-visual-studio.md)
- [자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)
- [자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)
