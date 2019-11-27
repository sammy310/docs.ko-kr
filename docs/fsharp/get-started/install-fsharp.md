---
title: F# 설치
description: 환경에 따라 F#을 설치하는 방법을 알아봅니다.
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204870"
---
# <a name="install-f"></a><span data-ttu-id="8dbe3-103">F\# 설치</span><span class="sxs-lookup"><span data-stu-id="8dbe3-103">Install F\#</span></span>

<span data-ttu-id="8dbe3-104">F#을 환경에 따라 여러 가지 방법으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="8dbe3-105">Visual Studio를 사용하여 F# 설치</span><span class="sxs-lookup"><span data-stu-id="8dbe3-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="8dbe3-106">[Visual studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) 를 처음 다운로드 하는 경우 visual studio 설치 관리자를 먼저 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="8dbe3-107">설치 관리자에서 적절한 SKU의 Visual Studio를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="8dbe3-108">이미 설치 되어 있는 경우 **수정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="8dbe3-109">다음으로 워크로드의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="8dbe3-110">ASP.NET Core 프로젝트에 대 한 지원 및 .NET F# Core 지원을 설치 하는 **ASP.NET 및 웹 개발** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="8dbe3-111">그런 다음 오른쪽 아래에서 **수정** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="8dbe3-112">그러면 선택한 모든 항목이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-112">This will install everything you have selected.</span></span> <span data-ttu-id="8dbe3-113">그런 다음 시작을 클릭 하 여 언어 F# 지원을 통해 Visual Studio2017을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="8dbe3-114">Visual Studio Code에서 F# 설치</span><span class="sxs-lookup"><span data-stu-id="8dbe3-114">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="8dbe3-115">먼저 [git를 설치](https://git-scm.com/download) 하 고 경로에 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-115">First, ensure you have [git installed](https://git-scm.com/download) and available on your PATH.</span></span> <span data-ttu-id="8dbe3-116">명령 프롬프트에서 `git --version`를 입력 하 고 **enter**키를 눌러 제대로 설치 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-116">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

<span data-ttu-id="8dbe3-117">그런 다음 [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-117">Next, install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="8dbe3-118">그런 다음 [Visual Studio Code](https://code.visualstudio.com) 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-118">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="8dbe3-119">그런 다음 확장 아이콘을 클릭하고 "Ionide"를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-119">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="8dbe3-120">Visual Studio Code 지원에 F# 필요한 유일한 플러그인은 [fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-120">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="8dbe3-121">그러나 [Paket](https://fsprojects.github.io/Paket/) 지원을 얻기 위해 Paket [를 설치 하 여](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) [가짜](https://fake.build/) 지원 및 고 [기능](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 을 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-121">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="8dbe3-122">FAKE와 Paket은 각각 프로젝트를 빌드하고 종속성을 관리하기 위한 부가적인  F# 커뮤니티 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-122">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="8dbe3-123">Mac 용 Visual Studio에서 F# 설치</span><span class="sxs-lookup"><span data-stu-id="8dbe3-123">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="8dbe3-124">F#는 선택한 구성에 관계 없이 기본적으로 [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-124">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="8dbe3-125">설치가 완료되면 "Visual Studio 시작"을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-125">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="8dbe3-126">macOS의 Finder를 통해 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-126">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="8dbe3-127">빌드 F# 서버에 설치</span><span class="sxs-lookup"><span data-stu-id="8dbe3-127">Install F# on a Build Server</span></span>

<span data-ttu-id="8dbe3-128">.Net Core 또는 .net SDK를 통해 .NET Framework를 사용 하는 경우 빌드 서버에 .NET SDK를 설치 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-128">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="8dbe3-129">필요한 모든 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-129">It has everything you need.</span></span>

<span data-ttu-id="8dbe3-130">.NET Framework를 사용 하 고 있고 .NET SDK를 사용 **하지** 않는 경우 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) 를 Windows Server에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-130">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="8dbe3-131">설치 관리자에서 **.net 데스크톱 빌드 도구** 를 선택 하 고 설치 관리자 메뉴의 오른쪽에 있는  **F# 컴파일러** 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dbe3-131">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
