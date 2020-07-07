---
title: .NET Framework 및 번외 릴리스
description: .NET 및 번외 릴리스에 대해 알아봅니다. 새로운 기능이 플랫폼 간 개발을 개선하거나 새로운 기능을 도입하기 위해 OOB(번외)로 릴리스됩니다.
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 9653696f46279e0c23418f92030d64839cc20518
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618768"
---
# <a name="net-framework-and-out-of-band-releases"></a><span data-ttu-id="ba337-104">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="ba337-104">.NET Framework and out-of-band releases</span></span>

<span data-ttu-id="ba337-105">.NET Framework는 UWP 앱, 기존의 데스크톱, 웹앱과 같은 다양한 플랫폼을 수용하고 코드 재사용을 최대화하는 방향으로 발전해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-105">.NET Framework has evolved to accommodate different platforms, such as UWP apps and traditional desktop and web apps, and to maximize code reuse.</span></span> <span data-ttu-id="ba337-106">정기적인 .NET Framework 릴리스 이외에 새로운 기능을 번외(OOB)로 릴리스하여 플랫폼 간 개발을 향상하거나 새 기능을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-106">In addition to regular .NET Framework releases, new features are released out of band (OOB) to improve cross-platform development or to introduce new functionality.</span></span>

## <a name="advantages-of-oob-releases"></a><span data-ttu-id="ba337-107">OOB 릴리스의 장점</span><span class="sxs-lookup"><span data-stu-id="ba337-107">Advantages of OOB releases</span></span>

<span data-ttu-id="ba337-108">Microsoft는 새 구성 요소 또는 구성 요소 OOB에 대한 업데이트를 제공함으로써 .NET Framework를 보다 자주 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-108">Shipping new components or updates to components out of band enables Microsoft to provide more frequent updates to .NET Framework.</span></span> <span data-ttu-id="ba337-109">또한 보다 신속하게 고객 의견을 수집하고 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-109">In addition, we can gather and respond to customer feedback more quickly.</span></span>

<span data-ttu-id="ba337-110">애플리케이션에서 OOB 기능을 사용하면 OOB 어셈블리가 앱 패키지와 함께 배포되므로 사용자는 애플리케이션을 실행하기 위해 최신 버전의 .NET Framework를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-110">When you use an OOB feature in your app, your users do not have to install the latest version of .NET Framework to run your app, because the OOB assemblies deploy with your app package.</span></span>

## <a name="how-oob-packages-are-distributed"></a><span data-ttu-id="ba337-111">OOB 패키지 분산 방식</span><span class="sxs-lookup"><span data-stu-id="ba337-111">How OOB packages are distributed</span></span>

<span data-ttu-id="ba337-112">핵심 CLR(공용 언어 런타임) 구성 요소에 대한 OOB 릴리스는 .NET용 패키지 관리자인 [NuGet](https://www.nuget.org/)을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-112">OOB releases for core common language runtime (CLR) components are delivered through [NuGet](https://www.nuget.org/), which is the package manager for .NET.</span></span> <span data-ttu-id="ba337-113">NuGet을 사용하면 Visual Studio 내에서 간단하게 라이브러리를 찾아 .NET Framework 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-113">NuGet enables you to browse and add libraries to your .NET Framework projects easily from within Visual Studio.</span></span> <span data-ttu-id="ba337-114">NuGet 패키지 관리자는 Visual Studio 2012부터 Visual Studio의 모든 버전에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-114">NuGet Package Manager is included with all editions of Visual Studio starting with Visual Studio 2012.</span></span> <span data-ttu-id="ba337-115">Visual Studio의 **도구** 메뉴에서 **NuGet 패키지 관리자**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-115">Look for **NuGet Package Manager** on the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="ba337-116">설치되지 않은 경우 [NuGet 설치](/nuget/install-nuget-client-tools)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-116">If it's not installed, follow the instructions on [Installing NuGet](/nuget/install-nuget-client-tools).</span></span> <span data-ttu-id="ba337-117">NuGet에 대한 자세한 내용은 [NuGet 문서](/nuget)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba337-117">For more information about NuGet, see the [NuGet docs](/nuget).</span></span>

## <a name="use-a-nuget-oob-package"></a><span data-ttu-id="ba337-118">NuGet OOB 패키지 사용</span><span class="sxs-lookup"><span data-stu-id="ba337-118">Use a NuGet OOB package</span></span>

<span data-ttu-id="ba337-119">NuGet 패키지 관리자가 설치되어 있는 경우 Visual Studio의 솔루션 탐색기를 사용하여 NuGet 패키지에 대한 참조를 찾아보고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-119">If NuGet Package Manager is installed, you can browse and add references to NuGet packages by using Solution Explorer in Visual Studio:</span></span>

1. <span data-ttu-id="ba337-120">Visual Studio에서 프로젝트의 바로 가기 메뉴를 열고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-120">Open the shortcut menu for your project in Visual Studio, and then choose **Manage NuGet Packages**.</span></span> <span data-ttu-id="ba337-121">(이 옵션은 **프로젝트** 메뉴에서도 사용 가능합니다.)</span><span class="sxs-lookup"><span data-stu-id="ba337-121">(This option is also available from the **Project** menu.)</span></span>

2. <span data-ttu-id="ba337-122">왼쪽 창에서 **온라인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-122">In the left pane, choose **Online**.</span></span>

3. <span data-ttu-id="ba337-123">시험판 패키지를 사용할 경우 중간 창의 드롭다운 목록 상자에서 **안정된 상태만** 대신 **시험판 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-123">If you want to use prerelease packages, in the drop-down list box in the middle pane, choose **Include Prerelease** instead of **Stable Only**.</span></span>

4. <span data-ttu-id="ba337-124">오른쪽 창에서 **검색** 상자를 사용하여 사용하려는 패키지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-124">In the right pane, use the **Search** box to locate the package you would like to use.</span></span> <span data-ttu-id="ba337-125">일부 Microsoft 패키지는 Microsoft .NET Framework 로고로 식별되며 모두 Microsoft를 게시자로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-125">Some Microsoft packages are identified by the Microsoft .NET Framework logo, and all identify Microsoft as the publisher.</span></span>

![NuGet 패키지 관리자.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

<span data-ttu-id="ba337-127">앞에서 언급했듯이 OOB 패키지를 사용하는 응용 프로그램을 배포하면 응용 프로그램 패키지와 함께 OOB 어셈블리가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-127">As mentioned previously, when you deploy an app that uses an OOB package, the OOB assemblies will ship with your app package.</span></span>

## <a name="types-of-oob-releases"></a><span data-ttu-id="ba337-128">OOB 릴리스 형식</span><span class="sxs-lookup"><span data-stu-id="ba337-128">Types of OOB releases</span></span>

<span data-ttu-id="ba337-129">일반적으로 OOB 패키지에는 하나 이상의 시험판 버전 및 안정적인 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-129">Typically, an OOB package has one or more prerelease versions and a stable version.</span></span> <span data-ttu-id="ba337-130">시험판과 함께 제공되는 라이선스는 일반적으로 재배포할 수 없지만 패키지를 사용해 보고 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-130">The license that accompanies a prerelease doesn't typically allow redistribution, but enables you to try out a package and provide feedback.</span></span> <span data-ttu-id="ba337-131">피드백이 패키지의 모든 업데이트에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-131">Feedback is incorporated in any updates made to the package.</span></span> <span data-ttu-id="ba337-132">최종 릴리스는 NuGet과 함께 안정적인 패키지로 분산되며 응용 프로그램과 함께 NuGet 패키지를 재배포할 수 있는 라이선스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-132">A final release is distributed as a stable package with NuGet and includes a license that lets you redistribute the NuGet package with your app.</span></span> <span data-ttu-id="ba337-133">안정적인 패키지가 Microsoft에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-133">Stable packages are supported by Microsoft.</span></span> <span data-ttu-id="ba337-134">Microsoft는 모든 패키지에 대한 블로그 게시물 및 포럼 답변과 같은 다른 유형의 문서는 물론 IntelliSense 지원도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-134">Microsoft provides IntelliSense support as well as other types of documentation such as blog posts and forum answers for all packages.</span></span> <span data-ttu-id="ba337-135">또한 소스 코드는 전부는 아니지만 일부 패키지에서 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-135">In addition, source code may be available with some, but not all, packages.</span></span> <span data-ttu-id="ba337-136">[.NET Framework 블로그](https://devblogs.microsoft.com/dotnet/)를 구독하면 새 패키지 및 업데이트된 패키지에 대한 알림을 받아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-136">For announcements regarding new and updated packages, you can subscribe to [the .NET Framework Blog](https://devblogs.microsoft.com/dotnet/).</span></span>

<span data-ttu-id="ba337-137">시험판과 안정적인 패키지를 둘 다 찾아보려면 NuGet 패키지 관리자에서 **시험판 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ba337-137">To find both prerelease and stable packages, choose **Include Prerelease** in NuGet Package Manager.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba337-138">참조</span><span class="sxs-lookup"><span data-stu-id="ba337-138">See also</span></span>

- [<span data-ttu-id="ba337-139">시작</span><span class="sxs-lookup"><span data-stu-id="ba337-139">Getting started</span></span>](index.md)
