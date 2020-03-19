---
title: F# 설치
description: 다양한 방법으로 F#을 설치하는 방법에 대해 알아봅니다.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401096"
---
# <a name="install-f"></a><span data-ttu-id="35e10-103">설치 F\#</span><span class="sxs-lookup"><span data-stu-id="35e10-103">Install F\#</span></span>

<span data-ttu-id="35e10-104">환경에 따라 여러 가지 방법으로 F#을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="35e10-105">비주얼 스튜디오로 F# 설치</span><span class="sxs-lookup"><span data-stu-id="35e10-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="35e10-106">[Visual Studio를](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 처음 다운로드하는 경우 먼저 Visual Studio 설치 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="35e10-107">설치 관리자에서 Visual Studio의 적절한 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="35e10-108">Visual Studio가 이미 설치되어 있는 경우 F#을 추가할 에디션 옆의 **수정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="35e10-109">워크로드 페이지에서 ASP.NET 핵심 프로젝트에 대한 F# 및 .NET Core 지원을 포함하는 **ASP.NET 및 웹 개발** 워크로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="35e10-110">오른쪽 하단 모서리에서 **수정을** 선택하여 선택한 모든 것을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="35e10-111">그런 다음 Visual Studio 설치 관리자에서 **시작을** 선택하여 F#으로 Visual Studio를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="35e10-112">비주얼 스튜디오 코드로 F# 설치</span><span class="sxs-lookup"><span data-stu-id="35e10-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="35e10-113">PATH에 [git을](https://git-scm.com/download) 설치하고 사용할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="35e10-114">명령 프롬프트를 입력하고 `git --version` **Enter**를 눌러 올바르게 설치되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="35e10-115">[.NET 코어 SDK](https://dotnet.microsoft.com/download) 및 [비주얼 스튜디오 코드를](https://code.visualstudio.com)설치합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="35e10-116">확장 아이콘을 선택하고 "Ionide"를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="35e10-117">비주얼 스튜디오 코드에서 F # 지원에 필요한 유일한 플러그인은 [Ionide-fsharp입니다.](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)</span><span class="sxs-lookup"><span data-stu-id="35e10-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="35e10-118">그러나, 당신은 또한 [가짜](https://fake.build/) 지원을 얻기 위해 [이오네이드 페이크를](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 설치하고 [이오니드 - Paket는](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) [Paket](https://fsprojects.github.io/Paket/) 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="35e10-119">FAKE와 Paket은 각각 프로젝트를 구축하고 종속성을 관리하기 위한 추가 F# 커뮤니티 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="35e10-120">Mac용 비주얼 스튜디오로 F# 설치</span><span class="sxs-lookup"><span data-stu-id="35e10-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="35e10-121">F#은 어떤 구성을 선택하든 [Mac용 Visual Studio에](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="35e10-122">설치가 완료되면 시각적 **스튜디오 시작을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="35e10-123">macOS에서 파인더를 통해 비주얼 스튜디오를 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="35e10-124">빌드 서버에 F# 설치</span><span class="sxs-lookup"><span data-stu-id="35e10-124">Install F# on a build server</span></span>

<span data-ttu-id="35e10-125">.NET SDK를 통해 .NET 코어 또는 .NET 프레임워크를 사용하는 경우 빌드 서버에 .NET SDK를 설치하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="35e10-126">그것은 당신이 필요로하는 모든 것을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-126">It has everything you need.</span></span>

<span data-ttu-id="35e10-127">.NET Framework를 사용하고 있고 .NET SDK를 사용하지 **않는** 경우 Windows 서버에 [Visual Studio 빌드 도구 SKU를](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="35e10-128">설치 관리자에서 **.NET 데스크톱 빌드 도구를**선택한 다음 설치 프로그램 메뉴의 오른쪽에 있는 **F# 컴파일러** 구성 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35e10-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
