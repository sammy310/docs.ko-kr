---
title: 설치F#
description: 설치 하는 방법에 알아봅니다 F# 환경을 기반으로 합니다.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331977"
---
# <a name="install-f"></a>F를 설치 합니다.\#

설치할 수 있습니다 F# 환경에 따라 여러 가지 방법으로 합니다.

## <a name="install-f-with-visual-studio"></a>설치 F# Visual Studio를 사용 하 여

다운로드 하는 경우 [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 처음으로이 먼저 설치는 Visual Studio 설치 관리자입니다. 설치 관리자에서 적절 한 SKU의 Visual Studio를 설치 합니다. 이미 있는 경우 설치를 클릭 **수정**합니다.

다음 워크 로드의 목록이 표시 됩니다. 선택 **ASP.NET 및 웹 개발** 가 설치 하는 F# ASP.NET Core 프로젝트에 대 한 지원 및.NET Core를 지원 합니다.

다음으로, 클릭 **수정** 오른쪽 아래에 있습니다.  그러면 선택한 모든 항목이 설치 됩니다. Visual Studio 2017을 열 수 있습니다 F# 를 클릭 하 여 언어 지원을 **시작할**합니다.

## <a name="install-f-with-visual-studio-for-mac"></a>설치 F# Mac 용 Visual Studio를 사용 하 여

F#기본적으로 설치 됩니다 [Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), 원하는 구성에 관계 없이 합니다.

설치가 완료 되 면 "Visual Studio 시작"을 선택 합니다. 또한 macOS에서 Finder를 통해 시작할 수도 있습니다.

## <a name="install-f-with-visual-studio-code"></a>설치 F# Visual Studio Code를 사용 하 여

있어야 [설치 된 git가](https://git-scm.com/download) 되도록 경로에서 사용할 수 있습니다 프로젝트 템플릿을 사용 합니다. 입력 하 여 제대로 설치 되었는지 확인할 수 있습니다 `git --version` 명령 프롬프트 및 키를 눌러 **Enter**합니다.

### [<a name="macos"></a>macOS](#tab/macos)

[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다. MacOS에서 Mono를 설치 하는 가장 쉬운 방법은 Homebrew 통해 됩니다. 터미널에 다음을 입력 하기만 하면 됩니다.

```console
brew install mono
```

또한 설치 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.

### [<a name="linux"></a>Linux](#tab/linux)

[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다. Debian 또는 Ubuntu의 경우 다음을 사용할 수 있습니다.

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

또한 설치 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.

### [<a name="windows"></a>Windows](#tab/windows)

설치할 [사용 하 여 Visual Studio F# 지원](#install-f-with-visual-studio)합니다. 작성, 컴파일 및 실행 하는 데 필요한 모든 구성 요소 설치 F# 코드입니다.

또한 설치 합니다 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.

---

해야 [Visual Studio Code](https://code.visualstudio.com) 설치 합니다.

그런 다음 확장 아이콘 및 "Ionide"에 대 한 검색을 클릭 합니다.

에 필요한 유일한 플러그 인 F# Visual Studio Code의 지원은 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다. 그러나 설치할 수도 있습니다 [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 가져오려는 [가짜](https://fsharp.github.io/FAKE/) 지원 및 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 가져오려면 [Paket](https://fsprojects.github.io/Paket/) 지원 합니다. 모조 Paket 추가 되며 F# 프로젝트를 빌드하고 각각 종속성을 관리 하기 위한 커뮤니티 도구입니다.
