---
title: F# 설치
description: 환경에 따라 F#을 설치하는 방법을 알아봅니다.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017022"
---
# <a name="install-f"></a>F를 설치 합니다.\#

F#을 환경에 따라 여러 가지 방법으로 설치할 수 있습니다.

## <a name="install-f-with-visual-studio"></a>Visual Studio를 사용하여 F# 설치

처음으로 [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 다운로드하는 경우 Visual Studio 설치 관리자가 먼저 설치됩니다. 설치 관리자에서 적절한 SKU의 Visual Studio를 설치합니다. 이미 설치되어 있는 경우 **변경**을 클릭합니다.

다음 워크 로드의 목록이 표시 됩니다. 선택 **ASP.NET 및 웹 개발** 가 설치 하는 F# ASP.NET Core 프로젝트에 대 한 지원 및.NET Core를 지원 합니다.

다음으로 오른쪽 아래에 있는 **변경**을 클릭합니다.  그러면 선택한 모든 항목이 설치됩니다. **시작**을 클릭하면 F#언어를 지원하는 Visual Studio 2017을 열 수 있습니다.

## <a name="install-f-with-visual-studio-for-mac"></a>Mac 용 Visual Studio에서 F# 설치

[Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에서는 구성에 관계 없이 F#이 기본적으로 설치됩니다.

설치가 완료되면 "Visual Studio 시작"을 선택합니다. macOS의 Finder를 통해 시작할 수도 있습니다.

## <a name="install-f-with-visual-studio-code"></a>Visual Studio Code에서 F# 설치

프로젝트 템플릿을 사용하기 위해서는 사용 가능한 [설치된 git](https://git-scm.com/download)가 경로에 있어야 합니다. 명령 프롬프트에서 `git --version`를 입력하고 **Enter**키를 누르면 제대로 설치되었는지 확인할 수 있습니다.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다. MacOS에서 Mono를 설치 하는 가장 쉬운 방법은 Homebrew 통해 됩니다. 터미널에 다음을 입력 하기만 하면 됩니다.

```console
brew install mono
```

그리고, [.NET Core SDK](https://www.microsoft.com/net/download)를 설치합니다.

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다. Debian 또는 Ubuntu의 경우 다음을 사용할 수 있습니다.

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

그리고, [.NET Core SDK](https://www.microsoft.com/net/download)를 설치합니다.

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

[F# 지원 Visual Studio를 설치](#install-f-with-visual-studio)합니다. 이 때 F# 코드를 작성하고 컴파일, 실행하는데 필요한 모든 구성 요소가 설치됩니다.

그리고, [.NET Core SDK](https://www.microsoft.com/net/download/)를 설치합니다.

---

해야 [Visual Studio Code](https://code.visualstudio.com) 설치 합니다.

그런 다음 확장 아이콘을 클릭하고 "Ionide"를 검색합니다.

Visual Studio Code에서 F#을 지원하기 위해 필요한 유일한 플러그인은 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)입니다. 하지만 [FAKE](https://fsharp.github.io/FAKE/) 지원을 위해 [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)를 설치하고 [Paket](https://fsprojects.github.io/Paket/) 지원을 위해 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)을 설치할 수 있습니다. FAKE와 Paket은 각각 프로젝트를 빌드하고 종속성을 관리하기 위한 부가적인  F# 커뮤니티 도구입니다.
