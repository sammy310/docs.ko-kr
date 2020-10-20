---
title: F# 설치
description: '여러 가지 방법으로 F #을 설치 하는 방법을 알아봅니다.'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224286"
---
# <a name="install-f"></a><span data-ttu-id="9ef95-103">F 설치\#</span><span class="sxs-lookup"><span data-stu-id="9ef95-103">Install F\#</span></span>

<span data-ttu-id="9ef95-104">사용자 환경에 따라 여러 가지 방법으로 F #을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="9ef95-105">Visual Studio를 사용 하 여 F # 설치</span><span class="sxs-lookup"><span data-stu-id="9ef95-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="9ef95-106">처음으로 [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 를 다운로드 하는 경우 Visual Studio 설치 관리자를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="9ef95-107">설치 관리자에서 적절 한 버전의 Visual Studio를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="9ef95-108">Visual Studio가 이미 설치 되어 있는 경우 F #을 추가 하려는 버전 옆에 있는 **수정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="9ef95-109">작업 페이지에서 **ASP.NET 및 웹 개발** 워크 로드를 선택 합니다. 여기에는 ASP.NET Core 프로젝트에 대 한 F # 및 .net Core 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="9ef95-110">오른쪽 아래 모서리에서 **수정** 을 선택 하 여 선택한 모든 항목을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="9ef95-111">그런 다음 Visual Studio 설치 관리자에서 **시작** 을 선택 하 여 F #을 사용 하 여 Visual Studio를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="9ef95-112">Visual Studio Code를 사용 하 여 F # 설치</span><span class="sxs-lookup"><span data-stu-id="9ef95-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="9ef95-113">[Git](https://git-scm.com/download) 를 설치 하 고 경로에 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="9ef95-114">`git --version`명령 프롬프트에서를 입력 하 고 **enter**키를 눌러 제대로 설치 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="9ef95-115">[.NET Core SDK](https://dotnet.microsoft.com/download) 를 설치 하 고 [Visual Studio Code](https://code.visualstudio.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="9ef95-116">확장 아이콘을 선택 하 고 "이상 Ide"를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="9ef95-117">Visual Studio Code에서 F # 지원에 필요한 유일한 플러그인은 [fsharp.core](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="9ef95-118">그러나 [Paket](https://fsprojects.github.io/Paket/) 지원을 얻기 위해 Paket [를 설치 하 여](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) [가짜](https://fake.build/) 지원 및 고 [기능](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 을 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="9ef95-119">가짜 및 Paket는 각각 프로젝트를 빌드하고 종속성을 관리 하기 위한 추가 F # 커뮤니티 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="9ef95-120">Mac용 Visual Studio를 사용 하 여 F # 설치</span><span class="sxs-lookup"><span data-stu-id="9ef95-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="9ef95-121">F #은 선택한 구성에 관계 없이 기본적으로 [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="9ef95-122">설치가 완료 되 면 **Visual Studio 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="9ef95-123">MacOS에서 Finder를 통해 Visual Studio를 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="9ef95-124">빌드 서버에 F # 설치</span><span class="sxs-lookup"><span data-stu-id="9ef95-124">Install F# on a build server</span></span>

<span data-ttu-id="9ef95-125">.Net Core 또는 .net SDK를 통해 .NET Framework를 사용 하는 경우 빌드 서버에 .NET SDK를 설치 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="9ef95-126">필요한 모든 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-126">It has everything you need.</span></span>

<span data-ttu-id="9ef95-127">.NET Framework를 사용 하는 경우 .NET SDK를 사용 **하지 않는** 경우 [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) 를 Windows Server에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="9ef95-128">설치 관리자에서 **.net 데스크톱 빌드 도구**를 선택 하 고 설치 관리자 메뉴의 오른쪽에서 **F # 컴파일러** 구성 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef95-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
