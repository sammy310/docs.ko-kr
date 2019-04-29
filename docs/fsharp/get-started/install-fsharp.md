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
# <a name="install-f"></a><span data-ttu-id="1f270-103">F를 설치 합니다.\#</span><span class="sxs-lookup"><span data-stu-id="1f270-103">Install F\#</span></span>

<span data-ttu-id="1f270-104">F#을 환경에 따라 여러 가지 방법으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="1f270-105">Visual Studio를 사용하여 F# 설치</span><span class="sxs-lookup"><span data-stu-id="1f270-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="1f270-106">처음으로 [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)를 다운로드하는 경우 Visual Studio 설치 관리자가 먼저 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="1f270-107">설치 관리자에서 적절한 SKU의 Visual Studio를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="1f270-108">이미 설치되어 있는 경우 **변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="1f270-109">다음 워크 로드의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="1f270-110">선택 **ASP.NET 및 웹 개발** 가 설치 하는 F# ASP.NET Core 프로젝트에 대 한 지원 및.NET Core를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="1f270-111">다음으로 오른쪽 아래에 있는 **변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="1f270-112">그러면 선택한 모든 항목이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-112">This will install everything you have selected.</span></span> <span data-ttu-id="1f270-113">**시작**을 클릭하면 F#언어를 지원하는 Visual Studio 2017을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="1f270-114">Mac 용 Visual Studio에서 F# 설치</span><span class="sxs-lookup"><span data-stu-id="1f270-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="1f270-115">[Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에서는 구성에 관계 없이 F#이 기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="1f270-116">설치가 완료되면 "Visual Studio 시작"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="1f270-117">macOS의 Finder를 통해 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="1f270-118">Visual Studio Code에서 F# 설치</span><span class="sxs-lookup"><span data-stu-id="1f270-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="1f270-119">프로젝트 템플릿을 사용하기 위해서는 사용 가능한 [설치된 git](https://git-scm.com/download)가 경로에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="1f270-120">명령 프롬프트에서 `git --version`를 입력하고 **Enter**키를 누르면 제대로 설치되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="1f270-121">macOS</span><span class="sxs-lookup"><span data-stu-id="1f270-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="1f270-122">[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="1f270-123">MacOS에서 Mono를 설치 하는 가장 쉬운 방법은 Homebrew 통해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="1f270-124">터미널에 다음을 입력 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="1f270-125">그리고, [.NET Core SDK](https://www.microsoft.com/net/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-125">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="1f270-126">Linux</span><span class="sxs-lookup"><span data-stu-id="1f270-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="1f270-127">[Mono](https://www.mono-project.com) 되 [ F# 대화형](../tutorials/fsharp-interactive/index.md) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="1f270-128">Debian 또는 Ubuntu의 경우 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="1f270-129">그리고, [.NET Core SDK](https://www.microsoft.com/net/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-129">Also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="1f270-130">Windows</span><span class="sxs-lookup"><span data-stu-id="1f270-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="1f270-131">[F# 지원 Visual Studio를 설치](#install-f-with-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="1f270-132">이 때 F# 코드를 작성하고 컴파일, 실행하는데 필요한 모든 구성 요소가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="1f270-133">그리고, [.NET Core SDK](https://www.microsoft.com/net/download/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-133">Also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="1f270-134">해야 [Visual Studio Code](https://code.visualstudio.com) 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="1f270-135">그런 다음 확장 아이콘을 클릭하고 "Ionide"를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="1f270-136">Visual Studio Code에서 F#을 지원하기 위해 필요한 유일한 플러그인은 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)입니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="1f270-137">하지만 [FAKE](https://fsharp.github.io/FAKE/) 지원을 위해 [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE)를 설치하고 [Paket](https://fsprojects.github.io/Paket/) 지원을 위해 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket)을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="1f270-138">FAKE와 Paket은 각각 프로젝트를 빌드하고 종속성을 관리하기 위한 부가적인  F# 커뮤니티 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1f270-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>
