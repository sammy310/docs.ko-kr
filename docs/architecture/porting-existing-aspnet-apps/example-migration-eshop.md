---
title: ASP.NET Core에 대 한 eShop 마이그레이션 예제
description: 샘플 온라인 스토어 앱을 참조로 사용 하 여 기존 ASP.NET MVC 앱을 ASP.NET Core로 마이그레이션하는 연습입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 83110909632e4eb433e1fabaedf3490ce594e12e
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401777"
---
# <a name="example-migration-of-eshop-to-aspnet-core"></a><span data-ttu-id="8dd62-103">ASP.NET Core에 대 한 eShop 마이그레이션 예제</span><span class="sxs-lookup"><span data-stu-id="8dd62-103">Example migration of eShop to ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8dd62-104">이 장에서는 .NET Framework 앱을 .NET Core로 마이그레이션하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-104">In this chapter, you'll see how to migrate a .NET Framework app to .NET Core.</span></span> <span data-ttu-id="8dd62-105">이 장에서는 ASP.NET 5.0 용으로 작성 된 샘플 온라인 스토어 앱을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-105">The chapter examines a sample online store app written for ASP.NET 5.0.</span></span> <span data-ttu-id="8dd62-106">앱은이 책의 앞부분에서 설명한 많은 개념과 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-106">The app will use many of the concepts and tools described earlier in this book.</span></span> <span data-ttu-id="8dd62-107">[ *EShopModernizing* GitHub 리포지토리에서](https://github.com/dotnet-architecture/eShopModernizing)시작 지점 앱을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-107">You'll find the starting point app in the [*eShopModernizing* GitHub repository](https://github.com/dotnet-architecture/eShopModernizing).</span></span> <span data-ttu-id="8dd62-108">여러 가지 시작 지점 앱이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-108">There are several different starting point apps.</span></span> <span data-ttu-id="8dd62-109">이 장에서는 *eShopLegacyMVCSolution* 를 집중적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-109">This chapter focuses on the *eShopLegacyMVCSolution*.</span></span>

<span data-ttu-id="8dd62-110">프로젝트의 초기 버전은 그림 4-1에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-110">The initial version of the project is shown in Figure 4-1.</span></span> <span data-ttu-id="8dd62-111">매우 표준 ASP.NET MVC 5 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-111">It's a fairly standard ASP.NET MVC 5 app.</span></span>

![그림 4-1](media/Figure4-1.png)

<span data-ttu-id="8dd62-113">**그림 4-1.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-113">**Figure 4-1.**</span></span> <span data-ttu-id="8dd62-114">*EShopModernizing* MVC 샘플 프로젝트 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-114">The *eShopModernizing* MVC sample project structure.</span></span>

<span data-ttu-id="8dd62-115">이 장에서는 많은 업그레이드 단계를 직접 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-115">This chapter demonstrates how to perform many of the upgrade steps by hand.</span></span> <span data-ttu-id="8dd62-116">또는 [.Net 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant) 를 사용 하 여 프로젝트 파일을 변환 하 고, 대상 프레임 워크를 변경 하 고, NuGet 패키지를 업데이트 하는 등의 다양 한 초기 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-116">Alternatively, you can use the [.NET Upgrade Assistant tool](https://aka.ms/dotnet-upgrade-assistant) to perform many of the initial steps, like converting the project file, changing the target framework, and updating NuGet packages.</span></span>

## <a name="run-apiport-to-identify-problematic-apis"></a><span data-ttu-id="8dd62-117">*Apiport* 를 실행 하 여 문제가 있는 api 식별</span><span class="sxs-lookup"><span data-stu-id="8dd62-117">Run *ApiPort* to identify problematic APIs</span></span>

<span data-ttu-id="8dd62-118">마이그레이션을 준비 하는 첫 번째 단계는 *Apiport* 도구를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-118">The first step in preparing to migrate is to run the *ApiPort* tool.</span></span> <span data-ttu-id="8dd62-119">이 도구는 앱에서 호출 하는 .NET Framework Api 수와 .NET Standard 또는 .NET Core의 해당 항목 수를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-119">The tool identifies how many .NET Framework APIs the app calls and how many of these have .NET Standard or .NET Core equivalents.</span></span> <span data-ttu-id="8dd62-120">주로 사용자의 앱 논리에 초점을 맞춘 후 타사 종속성이 아니라 이식 해야 하는 종속성에 주의를 기울여야 `System.Web` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-120">Focus primarily on your own app's logic, not third-party dependencies, and pay attention to `System.Web` dependencies that will need to be ported.</span></span> <span data-ttu-id="8dd62-121">ApiPort 도구는 [종속성을 이해 하 고 업데이트 하](/understand-update-dependencies.md)는 마지막 챕터에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-121">The ApiPort tool was introduced in the last chapter on [understanding and updating dependencies](/understand-update-dependencies.md).</span></span>

<span data-ttu-id="8dd62-122">[ *Apiport* 도구를 설치 하 고 구성한](../../standard/analyzers/portability-analyzer.md)후에는 그림 4-2에 나와 있는 것 처럼 Visual Studio 내에서 분석을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-122">After [installing and configuring the *ApiPort* tool](../../standard/analyzers/portability-analyzer.md), run the analysis from within Visual Studio, as shown in Figure 4-2.</span></span>

![그림 4-2](media/Figure4-2.png)

<span data-ttu-id="8dd62-124">**그림 4-2.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-124">**Figure 4-2.**</span></span> <span data-ttu-id="8dd62-125">Visual Studio에서 어셈블리 이식성을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-125">Analyze assembly portability in Visual Studio.</span></span>

<span data-ttu-id="8dd62-126">그림 4-3에 표시 된 것 처럼 프로젝트의 *bin* 폴더에서 웹 프로젝트의 어셈블리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-126">Choose the web project's assembly from the project's *bin* folder, as shown in Figure 4-3.</span></span>

![그림 4-3](media/Figure4-3.png)

<span data-ttu-id="8dd62-128">**그림 4-3.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-128">**Figure 4-3.**</span></span> <span data-ttu-id="8dd62-129">프로젝트의 웹 어셈블리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-129">Choose the project's web assembly.</span></span>

<span data-ttu-id="8dd62-130">솔루션에 여러 프로젝트가 포함 되어 있는 경우 모두 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-130">If your solution includes several projects, you can choose all of them.</span></span> <span data-ttu-id="8dd62-131">*EShop* 샘플에는 단일 MVC 프로젝트만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-131">The *eShop* sample includes just a single MVC project.</span></span>

<span data-ttu-id="8dd62-132">보고서가 생성 되 면 파일을 열고 결과를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-132">Once the report is generated, open the file and review the results.</span></span> <span data-ttu-id="8dd62-133">이 요약은 앱에서 호환 되는 버전을 만드는 .NET Framework 호출의 비율을 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-133">The summary provides a high-level view of what percentage of .NET Framework calls your app is making have compatible versions.</span></span> <span data-ttu-id="8dd62-134">그림 4-4에서는 *eShop* MVC 프로젝트에 대 한 요약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-134">Figure 4-4 shows the summary for the *eShop* MVC project.</span></span>

![그림 4-4](media/Figure4-4.png)

<span data-ttu-id="8dd62-136">**그림 4-4.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-136">**Figure 4-4.**</span></span> <span data-ttu-id="8dd62-137">ApiPort 요약.</span><span class="sxs-lookup"><span data-stu-id="8dd62-137">ApiPort summary.</span></span>

<span data-ttu-id="8dd62-138">이 앱의 경우 .NET Framework 호출의 약 80%가 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-138">For this app, about 80 percent of the .NET Framework calls are compatible.</span></span> <span data-ttu-id="8dd62-139">호출의 20%는 이식 프로세스 중에 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-139">20 percent of the calls need to be addressed during the porting process.</span></span> <span data-ttu-id="8dd62-140">세부 정보를 보면 호환 되지 않는 호출이 모두에 포함 된다는 것을 알 수 `System.Web` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-140">Viewing the details reveals that all of the incompatible calls are part of `System.Web`, which is an expected incompatibility.</span></span> <span data-ttu-id="8dd62-141">`System.Web`응용 프로그램의 컨트롤러 및 관련 클래스가 이후 단계에서 마이그레이션되면 호출에 대 한 종속성이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-141">The dependencies on `System.Web` calls will be addressed when the app's controllers and related classes are migrated in a later step.</span></span> <span data-ttu-id="8dd62-142">그림 4-5에는 도구에서 찾을 수 있는 특정 형식이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-142">Figure 4-5 lists some of the specific types found by the tool:</span></span>

![그림 4-5](media/Figure4-5.png)

<span data-ttu-id="8dd62-144">**그림 4-5.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-144">**Figure 4-5.**</span></span> <span data-ttu-id="8dd62-145">*Apiport* 호환 되지 않는 형식 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-145">*ApiPort* incompatible type details.</span></span>

<span data-ttu-id="8dd62-146">호환 되지 않는 대부분의 형식은 `Controller` ASP.NET Core에 해당 하는 및 관련 된 다양 한 특성을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-146">Most of the incompatible types refer to `Controller` and various related attributes that have equivalents in ASP.NET Core.</span></span>

## <a name="update-project-files-and-nuget-reference-syntax"></a><span data-ttu-id="8dd62-147">프로젝트 파일 및 NuGet 참조 구문 업데이트</span><span class="sxs-lookup"><span data-stu-id="8dd62-147">Update project files and NuGet reference syntax</span></span>

<span data-ttu-id="8dd62-148">다음으로 이전 *.csproj* 파일 구조에서 .net Core를 사용 하 여 더 간단 하 고 더 간단한 구조로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-148">Next, migrate from the older *.csproj* file structure to the newer, simpler structure introduced with .NET Core.</span></span> <span data-ttu-id="8dd62-149">이 작업을 수행 하는 경우  `<PackageReference>` 프로젝트 파일에서 요소를 사용 하기 위한 NuGet 참조를 위해packages.config파일을 사용 하는 것 에서도 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-149">In doing so, you'll also migrate from using a *packages.config* file for NuGet references to using `<PackageReference>` elements in the project file.</span></span>

<span data-ttu-id="8dd62-150">원본 프로젝트의 *eShopLegacyMVC* 파일 길이는 418 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-150">The original project's *eShopLegacyMVC.csproj* file is 418 lines long.</span></span> <span data-ttu-id="8dd62-151">그림 4-6에는 프로젝트 파일의 샘플이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-151">A sample of the project file is shown in Figure 4-6.</span></span> <span data-ttu-id="8dd62-152">전반적인 크기와 복잡도를 이해 하기 위해 이미지의 오른쪽에는 전체 파일의 축소 된 보기가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-152">To offer a sense of its overall size and complexity, the right side of the image contains a miniature view of the entire file.</span></span>

![그림 4-6](media/Figure4-6.png)

<span data-ttu-id="8dd62-154">**그림 4-6.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-154">**Figure 4-6.**</span></span> <span data-ttu-id="8dd62-155">*EShopLegacyMVC* 파일 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-155">The *eShopLegacyMVC.csproj* file structure.</span></span>

<span data-ttu-id="8dd62-156">기존 ASP.NET 프로젝트에 대 한 새 프로젝트 파일을 만드는 일반적인 방법은 `dotnet new`   >    >  Visual Studio에서 또는 파일 새로 만들기 **프로젝트** 를 사용 하 여 새 ASP.NET Core 앱을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-156">A common way to create a new project file for an existing ASP.NET project is to create a new ASP.NET Core app using `dotnet new` or **File** > **New** > **Project** in Visual Studio.</span></span> <span data-ttu-id="8dd62-157">그런 다음 이전 프로젝트에서 새 프로젝트에 파일을 복사 하 여 마이그레이션을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-157">Then files can be copied from the old project to the new one to complete the migration.</span></span>

<span data-ttu-id="8dd62-158">C # 프로젝트 파일 외에도 NuGet 종속성은 그림 4-7과 같이 별도의 45 줄 *packages.config* 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-158">In addition to the C# project file, NuGet dependencies are stored in a separate 45-line *packages.config* file, as shown in Figure 4-7.</span></span>

![그림 4-7](media/Figure4-7.png)

<span data-ttu-id="8dd62-160">**그림 4-7.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-160">**Figure 4-7.**</span></span> <span data-ttu-id="8dd62-161">*packages.config* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-161">The *packages.config* file.</span></span>

<span data-ttu-id="8dd62-162">새 *.csproj* 파일 형식으로 업그레이드 한 후에는 Visual Studio를 사용 하 여 클래스 라이브러리 프로젝트의 *packages.config* 를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-162">After upgrading to the new *.csproj* file format, you can migrate *packages.config* in class library projects using Visual Studio.</span></span> <span data-ttu-id="8dd62-163">그러나이 기능은 ASP.NET 프로젝트에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-163">This functionality doesn't work with ASP.NET projects, however.</span></span> <span data-ttu-id="8dd62-164">[ `<PackageReference>` Visual Studio에서 *packages.config* 로 마이그레이션에 대해 자세히 알아보세요](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="8dd62-164">[Learn more about migrating *packages.config* to `<PackageReference>` in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span> <span data-ttu-id="8dd62-165">마이그레이션할 프로젝트 수가 많은 경우 [이 커뮤니티 도구가 도움이 될 수 있습니다](https://github.com/MarkKharitonov/NuGetPCToPRMigrator).</span><span class="sxs-lookup"><span data-stu-id="8dd62-165">If you have a large number of projects to migrate, [this community tool may help](https://github.com/MarkKharitonov/NuGetPCToPRMigrator).</span></span>

## <a name="create-new-aspnet-core-project"></a><span data-ttu-id="8dd62-166">새 ASP.NET Core 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="8dd62-166">Create new ASP.NET Core project</span></span>

<span data-ttu-id="8dd62-167">Visual Studio의 **솔루션 탐색기** 내에서 대부분의 작업을 수행할 수 있기 때문에 기존 앱의 솔루션에 새 ASP.NET Core 프로젝트를 추가 하 여 파일을 더 쉽게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-167">Add a new ASP.NET Core project to the existing app's solution to make moving files easier, as most of the work can be done from within Visual Studio's **Solution Explorer**.</span></span> <span data-ttu-id="8dd62-168">Visual Studio에서 앱 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가 새 프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-168">In Visual Studio, right-click on your app's solution and choose **Add New Project**.</span></span> <span data-ttu-id="8dd62-169">**ASP.NET Core 웹 응용 프로그램** 을 선택 하 고 그림 4-8에 표시 된 것 처럼 새 프로젝트에 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-169">Choose **ASP.NET Core web application**, and give the new project a name as shown in Figure 4-8.</span></span>

![그림 4-8](media/Figure4-8.png)

<span data-ttu-id="8dd62-171">**그림 4-8.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-171">**Figure 4-8.**</span></span> <span data-ttu-id="8dd62-172">새 ASP.NET Core 웹 응용 프로그램을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-172">Add new ASP.NET Core web application.</span></span>

<span data-ttu-id="8dd62-173">다음 대화 상자에서 사용할 템플릿을 선택 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-173">The next dialog will ask you to choose which template to use.</span></span> <span data-ttu-id="8dd62-174">**비어 있는** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-174">Select the **Empty** template.</span></span> <span data-ttu-id="8dd62-175">또한 드롭다운을 **.Net Core** 에서 **.NET Framework** 로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-175">Be sure to also change the dropdown from **.NET Core** to **.NET Framework**.</span></span> <span data-ttu-id="8dd62-176">그림 4-9와 같이 **ASP.NET Core 2.2** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-176">Select **ASP.NET Core 2.2**, as shown in Figure 4-9.</span></span>

![그림 4-9](media/Figure4-9.png)

<span data-ttu-id="8dd62-178">**그림 4-9.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-178">**Figure 4-9.**</span></span> <span data-ttu-id="8dd62-179">ASP.NET Core 2.2를 사용 하 여 .NET Framework를 대상으로 하는 빈 프로젝트 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-179">Choose an Empty project template targeting .NET Framework with ASP.NET Core 2.2.</span></span>

### <a name="migrating-nuget-packages"></a><span data-ttu-id="8dd62-180">NuGet 패키지 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-180">Migrating NuGet Packages</span></span>

<span data-ttu-id="8dd62-181">*packages.config* 로 마이그레이션하기 위한 기본 제공 마이그레이션 도구는 `<PackageReference>` ASP.NET 프로젝트에서 작동 하지 않기 때문에 대신 커뮤니티 도구를 사용 하거나 직접 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-181">Since the built-in migration tool for migrating *packages.config* to `<PackageReference>` doesn't work on ASP.NET projects, you can use a community tool instead, or migrate by hand.</span></span> <span data-ttu-id="8dd62-182">[사용한 커뮤니티 도구](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) 는 XSL 파일을 사용 하 여 한 형식에서 다른 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-182">A [community tool I've used](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) uses an XSL file to transform from one format to the other.</span></span> <span data-ttu-id="8dd62-183">이를 사용 하려면 먼저 *packages.config* 파일을 새로 만든 ASP.NET Core 프로젝트 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-183">To use it, first copy the *packages.config* file to the newly created ASP.NET Core project folder.</span></span> <span data-ttu-id="8dd62-184">이 스크립트는 스크립트를 실행 하는 모든 폴더에서 *packages.config* 파일을 제거 하므로 파일의 백업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-184">Make a backup of your files, as this script removes the *packages.config* file from all folders under where you run the script.</span></span> <span data-ttu-id="8dd62-185">그런 다음 프로젝트 폴더 (또는 원하는 경우 전체 솔루션)에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-185">Then run these commands from the project folder (or for the entire solution if you prefer):</span></span>

```powershell
iwr https://git.io/vdKaV -OutFile Convert-ToPackageReference.ps1
iwr https://git.io/vdKar -OutFile  Convert-ToPackageReference.xsl
./Convert-ToPackageReference.ps1 | Out-Null
```

<span data-ttu-id="8dd62-186">처음 두 명령은 파일이 로컬로 존재 하도록 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-186">The first two commands download files so that they exist locally.</span></span> <span data-ttu-id="8dd62-187">마지막 줄은 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-187">The last line runs the script.</span></span> <span data-ttu-id="8dd62-188">실행 한 후 새 프로젝트 빌드를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-188">After running it, try to build the new project.</span></span> <span data-ttu-id="8dd62-189">오류가 발생 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-189">You'll most likely get some errors.</span></span> <span data-ttu-id="8dd62-190">이를 해결 하려면 일부 참조 (대부분 `Microsoft.AspNet` 및 패키지)를 제거 하 `System` 고 일부 특성을 제거 해야 할 수 있습니다 `xmlns` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-190">To resolve them, you'll want to eliminate some references (like most of the `Microsoft.AspNet` and `System` packages), and you may need to remove some `xmlns` attributes.</span></span>

<span data-ttu-id="8dd62-191">대부분의 ASP.NET MVC 앱에서 부트스트랩 및 jQuery와 같은 많은 클라이언트 쪽 종속성이 NuGet 패키지를 사용 하 여 배포 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-191">In most ASP.NET MVC apps, many client-side dependencies like Bootstrap and jQuery were deployed using NuGet packages.</span></span> <span data-ttu-id="8dd62-192">ASP.NET Core에서 NuGet 패키지는 서버 쪽 기능에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-192">In ASP.NET Core, NuGet packages are only used for server-side functionality.</span></span> <span data-ttu-id="8dd62-193">클라이언트 파일은 다른 방법으로 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-193">Client files should be managed through other means.</span></span> <span data-ttu-id="8dd62-194">`<PackageReference>`추가 및 제거 요소 목록을 검토 하 고 다음을 비롯 한 클라이언트 라이브러리에 대 한 정보를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-194">Review the list of `<PackageReference>` elements added and remove and make note of any that are for client libraries, including:</span></span>

- <span data-ttu-id="8dd62-195">부트스트랩</span><span class="sxs-lookup"><span data-stu-id="8dd62-195">Bootstrap</span></span>
- <span data-ttu-id="8dd62-196">jQuery</span><span class="sxs-lookup"><span data-stu-id="8dd62-196">jQuery</span></span>
- <span data-ttu-id="8dd62-197">jQuery. 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8dd62-197">jQuery.Validation</span></span>
- <span data-ttu-id="8dd62-198">Modernizr</span><span class="sxs-lookup"><span data-stu-id="8dd62-198">Modernizr</span></span>
- <span data-ttu-id="8dd62-199">popper.js</span><span class="sxs-lookup"><span data-stu-id="8dd62-199">popper.js</span></span>
- <span data-ttu-id="8dd62-200">대응</span><span class="sxs-lookup"><span data-stu-id="8dd62-200">Respond</span></span>

<span data-ttu-id="8dd62-201">이러한 패키지에 대해 NuGet에 의해 설치 된 정적 클라이언트 파일은 새 프로젝트의 *wwwroot* 폴더에 복사 되 고 여기에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-201">The static client files installed by NuGet for these packages will be copied over to the new project's *wwwroot* folder and hosted from there.</span></span> <span data-ttu-id="8dd62-202">앱에서 이러한 파일을 계속 사용 하 고 있는지 여부와이 파일을 계속 호스팅하거나 CDN (content delivery network)을 사용 하는 것이 적절 한지 여부를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-202">It's worth considering whether these files are still needed by the app, and whether it makes sense to continue hosting them or to use a content delivery network (CDN) instead.</span></span> <span data-ttu-id="8dd62-203">이러한 라이브러리 버전은 [npm](https://www.npmjs.com/) [와 같은 도구](/aspnet/core/client-side/libman/) 를 사용 하 여 빌드 시 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-203">These library versions can be managed at build time using tools like [LibMan](/aspnet/core/client-side/libman/) or [npm](https://www.npmjs.com/).</span></span> <span data-ttu-id="8dd62-204">그림 4-10은 표시 된 변환 도구를 사용 하 여 패키지 참조를 마이그레이션한 후에 불필요 한 패키지를 제거 하는 전체 *eShopPorted* 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-204">Figure 4-10 shows the full *eShopPorted.csproj* file after migrating package references using the conversion tool shown and removing unnecessary packages.</span></span>

![그림 4-10](media/Figure4-10.png)

<span data-ttu-id="8dd62-206">**그림 4-10.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-206">**Figure 4-10.**</span></span> <span data-ttu-id="8dd62-207">*EShopPorted* 파일의 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="8dd62-207">Package references in the *eShopPorted.csproj* file.</span></span>

<span data-ttu-id="8dd62-208">요소를의 특성으로 만들어 패키지 참조를 추가로 압축할 수 있습니다 `<Version>1.0.0.0</Version>` `Version=1.0.0.0` `<PackageReference>` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-208">The package references can be further compacted by making the `<Version>1.0.0.0</Version>` element a `Version=1.0.0.0` attribute on `<PackageReference>`.</span></span>

### <a name="migrate-static-files"></a><span data-ttu-id="8dd62-209">정적 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-209">Migrate static files</span></span>

<span data-ttu-id="8dd62-210">타사 스크립트 및 프레임 워크를 비롯 하 여 앱에서 사용 하는 모든 정적 파일 (사용자 지정 이미지 및 스타일 시트)을 이전 프로젝트에서 새 프로젝트에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-210">Any static files the app uses, including third-party scripts and frameworks but also custom images and stylesheets, must be copied from the old project to the new one.</span></span> <span data-ttu-id="8dd62-211">ASP.NET MVC 앱에서 파일은 일반적으로 프로젝트 폴더 내에서의 위치에 따라 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-211">In ASP.NET MVC apps, files were typically accessed based on their location within the project folder.</span></span> <span data-ttu-id="8dd62-212">ASP.NET Core apps에서 이러한 정적 파일은 *wwwroot* 폴더 내에서의 위치에 따라 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-212">In ASP.NET Core apps, these static files will be accessed based on their location within the *wwwroot* folder.</span></span> <span data-ttu-id="8dd62-213">*EShop* 프로젝트의 경우 다음 폴더에 정적 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-213">For the *eShop* project, there are static files in the following folders:</span></span>

* <span data-ttu-id="8dd62-214">*콘텐츠*</span><span class="sxs-lookup"><span data-stu-id="8dd62-214">*Content*</span></span>
* <span data-ttu-id="8dd62-215">*글자만*</span><span class="sxs-lookup"><span data-stu-id="8dd62-215">*fonts*</span></span>
* <span data-ttu-id="8dd62-216">*이미지*</span><span class="sxs-lookup"><span data-stu-id="8dd62-216">*Images*</span></span>
* <span data-ttu-id="8dd62-217">*Pics*</span><span class="sxs-lookup"><span data-stu-id="8dd62-217">*Pics*</span></span>
* <span data-ttu-id="8dd62-218">*스크립트*</span><span class="sxs-lookup"><span data-stu-id="8dd62-218">*Scripts*</span></span>

<span data-ttu-id="8dd62-219">이전 단계에서 사용 되는 **빈** 프로젝트 템플릿에는 기본적으로이 폴더가 포함 되지 않으며, 작업에 필요한 미들웨어가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-219">The **Empty** project template used in the previous step doesn't include this folder by default, or the middleware needed for it to work.</span></span> <span data-ttu-id="8dd62-220">추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-220">You'll need to add them.</span></span>

<span data-ttu-id="8dd62-221">프로젝트의 루트에 *wwwroot* 폴더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-221">Add a *wwwroot* folder to the root of the project.</span></span>

<span data-ttu-id="8dd62-222">NuGet 패키지의 버전 2.2.0을 추가 `Microsoft.AspNetCore.StaticFiles` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-222">Add version 2.2.0 of the `Microsoft.AspNetCore.StaticFiles` NuGet package.</span></span>

<span data-ttu-id="8dd62-223">*Startup.cs* 의 메서드에 대 한 호출을 추가 합니다 `app.UseStaticFiles()` `Configure` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-223">In *Startup.cs*, add a call to `app.UseStaticFiles()` in the `Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseStaticFiles();

    // ...
}
```

<span data-ttu-id="8dd62-224">ASP.NET MVC 앱의 *콘텐츠* 폴더를 새 프로젝트의 *wwwroot* 폴더로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-224">Copy the *Content* folder from the ASP.NET MVC app to the new project's *wwwroot* folder.</span></span>

<span data-ttu-id="8dd62-225">앱을 실행 하 고 해당 파일의/i o n t i o n *>* 로 이동 하 여 정적 파일이 예상 되는 경로에서 올바르게 처리 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-225">Run the app and navigate to its */Content/base.css* folder to verify that the static file is served correctly from its expected path.</span></span> <span data-ttu-id="8dd62-226">정적 파일이 포함 된 나머지 폴더를 새 프로젝트에 계속 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-226">Continue copying the rest of the folders containing static files to the new project.</span></span> <span data-ttu-id="8dd62-227">또한 프로젝트의 루트에서 *wwwroot* 폴더로 *favicon* 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-227">You'll also want to copy the *favicon.ico* file from the project's root to the *wwwroot* folder.</span></span> <span data-ttu-id="8dd62-228">그림 4-11에서는 이러한 파일과 해당 폴더가 모두 복사 된 후의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-228">Figure 4-11 shows the results after these files and their folders have all been copied.</span></span>

![그림 4-11](media/Figure4-11.png)

<span data-ttu-id="8dd62-230">**그림 4-11.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-230">**Figure 4-11.**</span></span> <span data-ttu-id="8dd62-231">*Wwwroot* 폴더로 복사 되는 정적 폴더.</span><span class="sxs-lookup"><span data-stu-id="8dd62-231">Static folders copied over to *wwwroot* folder.</span></span>

### <a name="migrate-c-files"></a><span data-ttu-id="8dd62-232">C # 파일 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-232">Migrate C# files</span></span>

<span data-ttu-id="8dd62-233">그런 다음 표준 MVC 폴더 및 *컨트롤러*, *모델*, *ViewModel*, *서비스* 등의 내용을 포함 하 여 앱에서 사용 하는 c # 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-233">Next, copy over the C# files used by the app, including standard MVC folders and their contents like *Controllers*, *Models*, *ViewModel*, and *Services*.</span></span> <span data-ttu-id="8dd62-234">이러한 파일에는 변경 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-234">There will most likely be some changes needed in these files.</span></span> <span data-ttu-id="8dd62-235">한 번에 하나의 폴더 (또는 하위 폴더)를 복사 하 여 컴파일할 때 해결 해야 하는 오류를 확인 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-235">It's best to copy one folder (or subfolder) at a time and compile to see what errors need to be addressed as you go.</span></span>

<span data-ttu-id="8dd62-236">*EShop* 샘플의 경우 마이그레이션하려는 첫 번째 폴더는 c # 엔터티와 Entity Framework 클래스를 포함 하는 *모델* 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-236">For the *eShop* sample, the first folder I choose to migrate is the *Models* folder, which includes C# entities and Entity Framework classes.</span></span> <span data-ttu-id="8dd62-237">이 폴더의 클래스는 대부분 다른 클래스에서 사용 되므로 이러한 클래스가 복사 될 때까지 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-237">This folder's classes are used by most of the others, so they won't work until these classes have been copied.</span></span> <span data-ttu-id="8dd62-238">폴더 및 빌드를 복사 하면 컴파일러가 누락 된 네임 스페이스,에 대 한 `System.Web.Hosting` 관련 액세스 및에 대 한 참조와 관련 된 오류를 표시 합니다 `HostingEnvironment` `ConfigurationManager.AppSettings` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-238">After copying the folder and building, the compiler revealed errors related to missing namespace `System.Web.Hosting`, related access to `HostingEnvironment`, and a reference to `ConfigurationManager.AppSettings`.</span></span> <span data-ttu-id="8dd62-239">이러한 문제에 대 한 해결 방법은 필요한 경로 데이터를 전달 하는 것입니다. 지금은 줄 바꿈이 주석 처리 되 고 `TODO:` 각 줄에 주석이 추가 되어 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-239">The solution to these issues will be to pass in the necessary path data; for now the breaking lines are commented out and a `TODO:` comment is added to each one to track it.</span></span> <span data-ttu-id="8dd62-240">5 개 줄을 변경한 후 **작업 목록** 에는 5 개의 항목과 프로젝트 빌드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-240">After changing five lines, the **Task List** shows five items and the project builds.</span></span>

<span data-ttu-id="8dd62-241">그런 다음, 하나의 클래스를 사용 하 여 *ViewModel* 폴더를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-241">Next, the *ViewModel* folder, with its one class, is copied over.</span></span> <span data-ttu-id="8dd62-242">이는 간단 하 고 즉시 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-242">It's an easy one, and builds immediately.</span></span>

<span data-ttu-id="8dd62-243">*서비스* 폴더가에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-243">The *Services* folder is copied over.</span></span> <span data-ttu-id="8dd62-244">이 폴더의 클래스는 *모델* 폴더의 Entity Framework 클래스에 종속 되므로 해당 폴더 뒤에 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-244">This folder's classes depend on Entity Framework classes from the *Models* folder, which is why it needed to be copied after that folder.</span></span> <span data-ttu-id="8dd62-245">다행히 오류가 발생 하지 않고 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-245">Fortunately, it too builds without errors.</span></span>

<span data-ttu-id="8dd62-246">이는 *컨트롤러* 폴더와 두 개의 클래스를 유지 합니다 `Controller` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-246">That leaves the *Controllers* folder and its two `Controller` classes.</span></span> <span data-ttu-id="8dd62-247">새 프로젝트에 폴더를 복사 하 고 빌드한 후에는 7 개의 빌드 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-247">After copying the folder to the new project and building, there are seven build errors.</span></span> <span data-ttu-id="8dd62-248">그 중 4 개는 `ViewBag` 액세스 및 오류 보고와 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-248">Four of them are related to `ViewBag` access and report an error of:</span></span>

> `Missing compiler required member 'Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo.Create'`

<span data-ttu-id="8dd62-249">이 오류를 해결 하려면 c #에 대 한 NuGet 패키지 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-249">To resolve this error add a NuGet package reference to C#:</span></span>

```xml
<PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
```

<span data-ttu-id="8dd62-250">나머지 세 개의 오류는 참조 되지 않는 어셈블리에 정의 된 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-250">The remaining three errors specify types that are defined in an assembly that isn't referenced.</span></span> <span data-ttu-id="8dd62-251">특히 다음과 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-251">Specifically these types:</span></span>

- `HttpServerUtilityBase`
- `RouteValueDictionary`
- `HttpRequestBase`

<span data-ttu-id="8dd62-252">각 오류를 하나씩 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-252">Let's look at each error one by one.</span></span> <span data-ttu-id="8dd62-253">`Server`더 이상 존재 하지 않는의 속성을 참조 하는 동안 첫 번째 오류가 발생 합니다 `Controller` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-253">The first error occurs while trying to reference the `Server` property of `Controller`, which no longer exists.</span></span> <span data-ttu-id="8dd62-254">작업의 목표는 앱의 이미지 파일에 대 한 경로를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-254">The goal of the operation is to get the path to an image file in the app:</span></span>

```csharp
if (item != null)
{
    var webRoot = Server.MapPath("~/Pics"); // compiler error on this line
    var path = Path.Combine(webRoot, item.PictureFileName);

    string imageFileExtension = Path.GetExtension(item.PictureFileName);
    string mimetype = GetImageMimeTypeFromImageFileExtension(imageFileExtension);

    var buffer = System.IO.File.ReadAllBytes(path);

    return File(buffer, mimetype);
}
```

<span data-ttu-id="8dd62-255">이 문제는 두 가지 방법으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-255">There are two possible solutions to this problem.</span></span> <span data-ttu-id="8dd62-256">첫 번째 방법은 기능을 그대로 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-256">The first is to keep the functionality as it is.</span></span> <span data-ttu-id="8dd62-257">이 경우를 사용 하는 대신 `Server.MapPath` *wwwroot* 에서 이미지 파일의 위치를 참조 하는 고정 경로를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-257">In this case, rather than using `Server.MapPath`, a fixed path referencing the image files' location in *wwwroot* should be used.</span></span> <span data-ttu-id="8dd62-258">또는이 작업 메서드의 유일한 용도는 정적 이미지 파일을 반환 하는 것 이므로 파일 보기에서이 작업에 대 한 참조를 업데이트 하 여 정적 파일을 직접 참조 하 여 런타임 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-258">Alternately, since the only purpose of this action method is to return a static image file, the references to this action in view files can be updated to reference the static files directly, which improves runtime performance.</span></span> <span data-ttu-id="8dd62-259">이 작업의 일부로 처리가 수행 되지 않으므로 파일을 직접 제공 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-259">Since no processing is being done as part of this action, there's no reason not to just serve the files directly.</span></span> <span data-ttu-id="8dd62-260">이 작업에 대 한 모든 참조를 업데이트 하기 위해 tenable을 사용 하지 않는 경우 정적 파일의 위치에 대 한 리디렉션을 생성 하도록 작업을 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-260">If it's not tenable to update all references to this action, the action could be rewritten to produce a redirect to the static file's location.</span></span>

<span data-ttu-id="8dd62-261">다음 두 오류는 동일한 코드 줄의 동일한 private 메서드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-261">The next two errors both occur in the same private method in the same line of code:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

<span data-ttu-id="8dd62-262">`this.Url`및 모두 `this.Request` 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-262">Both `this.Url` and `this.Request` cause compiler errors.</span></span> <span data-ttu-id="8dd62-263">이 코드를 사용 하는 방법을 살펴보면 `PicController` 이미지 파일을 렌더링 하는 작업에 대 한 링크를 작성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-263">Looking at how this code is used, its purpose is to build a link to the `PicController` action that renders image files.</span></span> <span data-ttu-id="8dd62-264">방금 검색 한 것과 동일한 것을 *wwwroot* 에 있는 정적 파일에 대 한 직접 링크로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-264">The same one we just discovered could probably be replaced with direct links to the static files located in *wwwroot*.</span></span> <span data-ttu-id="8dd62-265">지금은이 코드를 주석으로 처리 하 고 다른 사람을 참조 하도록 주석을 추가 하는 것이 좋습니다 `TODO:` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-265">For now, it's worth commenting out this code and adding a `TODO:` comment to reference the pics another way.</span></span>

<span data-ttu-id="8dd62-266">`Controller`이 코드가 표시 되는 클래스에서 사용 되는 기본 클래스는 `CatalogController` 여전히를 참조 하 고 `System.Web.Mvc.Controller` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-266">It's worth noting that the base `Controller` class, used by the `CatalogController` class in which this code appears, is still referring to `System.Web.Mvc.Controller`.</span></span> <span data-ttu-id="8dd62-267">ASP.NET Core를 사용 하도록 업데이트 한 후에는 수정 하는 데 더 많은 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-267">There will undoubtedly be more errors to fix once we update this to use ASP.NET Core.</span></span> <span data-ttu-id="8dd62-268">먼저 `using System.Web.Mvc;` 의 문 목록에서 줄을 제거 `using` `CatalogController` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-268">First, remove the `using System.Web.Mvc;` line from the list of `using` statements in `CatalogController`.</span></span> <span data-ttu-id="8dd62-269">그런 다음 NuGet 패키지를 추가 `Microsoft.AspNetCore.Mvc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-269">Next, add the NuGet package `Microsoft.AspNetCore.Mvc`.</span></span> <span data-ttu-id="8dd62-270">마지막으로 문을 추가 하 `using Microsoft.AspNetCore.Mvc;` 고 앱을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-270">Finally, add a `using Microsoft.AspNetCore.Mvc;` statement, and build the app again.</span></span>

<span data-ttu-id="8dd62-271">이번에는 16 개 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-271">This time, there are 16 errors:</span></span>

- <span data-ttu-id="8dd62-272">`Include` 은 (는) 올바른 명명 된 특성 인수가 아닙니다 (2).</span><span class="sxs-lookup"><span data-stu-id="8dd62-272">`Include` is not a valid named attribute argument (2)</span></span>
- <span data-ttu-id="8dd62-273">`HttpStatusCodeResult` 찾을 수 없음 (3)</span><span class="sxs-lookup"><span data-stu-id="8dd62-273">`HttpStatusCodeResult` not found (3)</span></span>
- <span data-ttu-id="8dd62-274">`HttpNotFound` 존재 하지 않음 (3)</span><span class="sxs-lookup"><span data-stu-id="8dd62-274">`HttpNotFound` does not exist (3)</span></span>
- <span data-ttu-id="8dd62-275">`SelectList` 찾을 수 없음 (8)</span><span class="sxs-lookup"><span data-stu-id="8dd62-275">`SelectList` not found (8)</span></span>

<span data-ttu-id="8dd62-276">그 후에는 이러한 오류를 하나씩 검토해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-276">Once more, let's review these errors one by one.</span></span> <span data-ttu-id="8dd62-277">첫째,를 `SelectList` 추가 하 여 해결할 수 있습니다 `using Microsoft.AspNetCore.Mvc.Rendering;` . 그러면 오류가 거의 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-277">First, `SelectList` can be fixed by adding `using Microsoft.AspNetCore.Mvc.Rendering;`, which eliminates half of the errors.</span></span>

<span data-ttu-id="8dd62-278">에 대 한 모든 참조 `return HttpNotFound();` 는로 바꾸어야 합니다 `return NotFound();` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-278">All references to `return HttpNotFound();` should be replaced with `return NotFound();`.</span></span>

<span data-ttu-id="8dd62-279">에 대 한 모든 참조 `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` 는로 바꾸어야 합니다 `return BadRequest();` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-279">All references to `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` should be replaced with `return BadRequest();`.</span></span>

<span data-ttu-id="8dd62-280">`Include` `[Bind]` 이는 다음과 같은 몇 가지 동작 메서드에서 특성을 사용 하는 것을 그대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-280">That just leaves the use of `Include` with a `[Bind]` attribute on a couple of action methods that look like this:</span></span>

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind(Include = "Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

<span data-ttu-id="8dd62-281">위의 코드는 문자열에 나열 된 속성에 대 한 모델 바인딩을 제한 합니다 `Include` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-281">The preceding code restricts model binding to the properties listed in the `Include` string.</span></span> <span data-ttu-id="8dd62-282">MVC ASP.NET Core `[Bind]` 특성은 여전히 존재 하지만 더 이상 인수가 필요 하지 않습니다 `Include =` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-282">In ASP.NET Core MVC, the `[Bind]` attribute still exists, but no longer needs the `Include =` argument.</span></span> <span data-ttu-id="8dd62-283">속성 목록을 특성에 직접 전달 합니다 `[Bind]` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-283">Pass the list of properties directly to the `[Bind]` attribute:</span></span>

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind("Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

<span data-ttu-id="8dd62-284">이러한 변경 내용으로 프로젝트를 한 번 더 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-284">With these changes, the project compiles once more.</span></span> <span data-ttu-id="8dd62-285">일반적으로 도메인 모델 또는 데이터 모델 형식에 대 한 모델 바인딩을 직접 사용 하는 대신 컨트롤러 입력에 별도의 모델 유형을 사용 하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-285">It's generally a better practice to use separate model types for controller inputs, rather than using model binding directly to your domain model or data model types.</span></span>

## <a name="migrate-views"></a><span data-ttu-id="8dd62-286">뷰 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-286">Migrate views</span></span>

<span data-ttu-id="8dd62-287">뷰와 관련 된 가장 큰 두 가지 ASP.NET Core MVC 기능은 [Razor Pages](/aspnet/core/razor-pages/) 및 [태그 도우미](/aspnet/core/mvc/views/tag-helpers/built-in/)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-287">The two biggest ASP.NET Core MVC features related to views are [Razor Pages](/aspnet/core/razor-pages/) and [Tag Helpers](/aspnet/core/mvc/views/tag-helpers/built-in/).</span></span> <span data-ttu-id="8dd62-288">초기 마이그레이션의 경우 두 기능을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-288">For the initial migration, we won't use either feature.</span></span> <span data-ttu-id="8dd62-289">그러나 앱을 마이그레이션한 후에도 계속 지원 하면 기능을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-289">You should, however, keep the features in mind if you continue supporting the app once it's been migrated.</span></span> <span data-ttu-id="8dd62-290">다음 단계는 원본 프로젝트의 *Views* 폴더를 새 프로젝트에 복사 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-290">The next step is to copy the *Views* folder from the original project into the new one.</span></span> <span data-ttu-id="8dd62-291">빌드 후에는 9 개의 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-291">After building, there are nine errors:</span></span>

- <span data-ttu-id="8dd62-292">HttpContext가 없습니다 (2).</span><span class="sxs-lookup"><span data-stu-id="8dd62-292">HttpContext does not exist (2)</span></span>
- <span data-ttu-id="8dd62-293">스크립트가 없습니다 (5).</span><span class="sxs-lookup"><span data-stu-id="8dd62-293">Scripts does not exist (5)</span></span>
- <span data-ttu-id="8dd62-294">스타일이 존재 하지 않습니다 (1).</span><span class="sxs-lookup"><span data-stu-id="8dd62-294">Styles does not exist (1)</span></span>
- <span data-ttu-id="8dd62-295">HtmlString을 찾을 수 없습니다 (1).</span><span class="sxs-lookup"><span data-stu-id="8dd62-295">HtmlString could not be found(1)</span></span>

<span data-ttu-id="8dd62-296">이러한 오류를 조사 하면 대부분의 작업이 주 *_Layout. cshtml* 에 있고, 스크립트 및 스타일 태그 렌더링과 관련 된 몇 가지를 포함 하거나, 앱을 호스트 하는 서버를 마지막으로 다시 시작한 경우 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-296">Investigating these errors finds that most of them are in the main *_Layout.cshtml*, with several related to rendering script and style tags, or displaying when the server hosting the app was last restarted.</span></span> <span data-ttu-id="8dd62-297">다음 코드 목록에서는 *_Layout. cshtml* 파일의 문제 영역을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-297">The following code listing shows problem areas in the *_Layout.cshtml* file:</span></span>

```razor
// other lines omitted; only errors shown
@Styles.Render("~/Content/css")
@Scripts.Render("~/bundles/modernizr")

@{ var sessionInfo = new HtmlString($"{HttpContext.Current.Session["MachineName"]}, {HttpContext.Current.Session["SessionStartTime"]}");}

@Scripts.Render("~/bundles/jquery")
@Scripts.Render("~/bundles/bootstrap")
```

<span data-ttu-id="8dd62-298">Modernizr에 대 한 참조를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-298">The reference to Modernizr can be removed.</span></span> <span data-ttu-id="8dd62-299">부트스트랩 및 jQuery에 대 한 참조를 CDN 링크를 적절 한 버전으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-299">The references to Bootstrap and jQuery can be replaced with CDN links to the appropriate version.</span></span>

<span data-ttu-id="8dd62-300">`@Styles.Render`줄을 다음으로 바꾸기:</span><span class="sxs-lookup"><span data-stu-id="8dd62-300">Replace `@Styles.Render` line with:</span></span>

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

<span data-ttu-id="8dd62-301">마지막 두 줄을 `Scripts.Render` 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-301">Replace the last two `Scripts.Render` lines with:</span></span>

```html
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```

<span data-ttu-id="8dd62-302">마지막으로 부트스트랩 후에 `<link>` `<link>` 앱에서 사용 하는 로컬 스타일에 대 한 추가 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-302">Finally, after the Bootstrap `<link>`, add additional `<link>` elements for local styles your app uses.</span></span> <span data-ttu-id="8dd62-303">*EShop* 의 경우 결과는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-303">For *eShop*, the result is shown here:</span></span>

```html
<link rel="stylesheet" href="~/Content/custom.css" />
<link rel="stylesheet" href="~/Content/base.css" />
<link rel="stylesheet" href="~/Content/Site.css" />
```

<span data-ttu-id="8dd62-304">요소가 표시 되는 순서를 결정 하려면 `<link>` 원래 앱의 렌더링 된 HTML을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="8dd62-304">To determine the order in which the `<link>` elements should appear, look at your original app's rendered HTML.</span></span> <span data-ttu-id="8dd62-305">또는 *eShop* 샘플에 대해 적절 한 시퀀스를 나타내는이 코드를 포함 하는 *BundleConfig.cs* 를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-305">Alternatively, review *BundleConfig.cs*, which for the *eShop* sample includes this code indicating the appropriate sequence:</span></span>

```csharp
bundles.Add(new StyleBundle("~/Content/css").Include(
          "~/Content/bootstrap.css",
          "~/Content/custom.css",
          "~/Content/base.css",
          "~/Content/site.css"));
```

<span data-ttu-id="8dd62-306">*만들기* 및 *편집* 보기에서 jQuery 유효성 검사를 로드 하는 중에 다시 빌드하면 하나 이상의 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-306">Building again reveals one more error loading jQuery Validation on the *Create* and *Edit* views.</span></span> <span data-ttu-id="8dd62-307">다음 스크립트로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-307">Replace it with this script:</span></span>

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.17.0/jquery.validate.min.js" integrity="sha512-O/nUTF5mdFkhEoQHFn9N5wmgYyW323JO6v8kr6ltSRKriZyTr/8417taVWeabVS4iONGk2V444QD0P2cwhuTkg==" crossorigin="anonymous"></script>
```

<span data-ttu-id="8dd62-308">뷰에서 마지막으로 수정할 사항은 앱이 실행 되는 `Session` 시간 및 해당 컴퓨터를 표시 하는에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-308">The last thing to fix in the views is the reference to `Session` to display how long the app has been running, and on which machine.</span></span> <span data-ttu-id="8dd62-309">에서이 데이터를 `Startup` 정적 변수로 수집 하 고 레이아웃 페이지에 변수를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-309">We can collect this data in `Startup` as static variables and display the variables on the layout page.</span></span> <span data-ttu-id="8dd62-310">*Startup.cs* 에 다음 속성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-310">Add the following properties to *Startup.cs*:</span></span>

```csharp
public static DateTime StartTime { get; } = DateTime.UtcNow;
public static string MachineName { get; } = Environment.MachineName;
```

<span data-ttu-id="8dd62-311">그런 다음 레이아웃의 바닥글 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-311">Then replace the content of the footer in the layout with the following code:</span></span>

```razor
<section class="col-sm-6">
    <img class="esh-app-footer-text hidden-xs" src="~/images/main_footer_text.png" width="335" height="26" alt="footer text image" />
    <br />
<small>@eShopPorted.Startup.MachineName - @eShopPorted.Startup.StartTime.ToString() UTC</small>
</section>
```

<span data-ttu-id="8dd62-312">이 시점에서 앱은 성공적으로 빌드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-312">At this point, the app once more builds successfully.</span></span> <span data-ttu-id="8dd62-313">그러나이 도구를 실행 하려고 하면 *헬로 월드 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="8dd62-313">However, trying to run it just yields *Hello World!*</span></span> <span data-ttu-id="8dd62-314">**빈** ASP.NET Core 템플릿은 모든 요청에 대 한 응답으로 표시 하도록 구성 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-314">because the **Empty** ASP.NET Core template is only configured to display that in response to any request.</span></span> <span data-ttu-id="8dd62-315">다음 섹션에서는 종속성 주입 및 구성을 비롯 하 여 ASP.NET Core MVC를 사용 하도록 앱을 구성 하 여 마이그레이션을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-315">In the next section, I complete the migration by configuring the app to use ASP.NET Core MVC, including dependency injection and configuration.</span></span> <span data-ttu-id="8dd62-316">앱이 준비 되 면 앱이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-316">Once that's in place, the app should run.</span></span> <span data-ttu-id="8dd62-317">그런 다음 이전에 생성 된 작업을 수정 해야 합니다 `TODO:` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-317">Then it will be time to fix the `TODO:` tasks that were created earlier.</span></span>

## <a name="migrate-app-startup-components"></a><span data-ttu-id="8dd62-318">앱 시작 구성 요소 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-318">Migrate app startup components</span></span>

<span data-ttu-id="8dd62-319">마지막 마이그레이션 단계는 *global.asax에서 앱 시작 작업을 수행* 하 고이 작업을 호출 하는 클래스를 사용 하 여 해당 작업을 해당 하는 ASP.NET Core로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-319">The last migration step is to take the app startup tasks from *Global.asax*, and the classes it calls, and migrate these to their ASP.NET Core equivalents.</span></span> <span data-ttu-id="8dd62-320">이러한 작업에는 MVC 자체의 구성, 종속성 주입 설정 및 새 구성 시스템 사용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-320">These tasks include configuration of MVC itself, setting up dependency injection, and working with the new configuration system.</span></span> <span data-ttu-id="8dd62-321">ASP.NET Core에서 이러한 작업은 *Startup.cs* 파일에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-321">In ASP.NET Core, these tasks are handled in the *Startup.cs* file.</span></span>

### <a name="configure-mvc"></a><span data-ttu-id="8dd62-322">MVC 구성</span><span class="sxs-lookup"><span data-stu-id="8dd62-322">Configure MVC</span></span>

<span data-ttu-id="8dd62-323">원본 ASP.NET MVC 앱의 `Application_Start` *global.asax* 에는 앱이 시작 될 때 실행 되는 다음 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-323">The original ASP.NET MVC app has the following code in its `Application_Start` in *Global.asax*, which runs when the app starts up:</span></span>

```csharp
protected void Application_Start()
{
    container = RegisterContainer();
    AreaRegistration.RegisterAllAreas();
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
    RouteConfig.RegisterRoutes(RouteTable.Routes);
    BundleConfig.RegisterBundles(BundleTable.Bundles);
    ConfigDataBase();
}
```

<span data-ttu-id="8dd62-324">이러한 줄을 하나씩 살펴보면 메서드는 아래에 `RegisterContainer` 이식할 종속성 주입을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-324">Looking at these lines one by one, the `RegisterContainer` method sets up dependency injection, which will be ported below.</span></span> <span data-ttu-id="8dd62-325">다음 세 줄은 MVC의 서로 다른 부분, 즉 영역, 필터 및 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-325">The next three lines configure different parts of MVC: areas, filters, and routes.</span></span> <span data-ttu-id="8dd62-326">번들은 이식 된 앱에서 정적 파일로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-326">Bundles are replaced by static files in the ported app.</span></span> <span data-ttu-id="8dd62-327">마지막 줄은 응용 프로그램에 대 한 데이터 액세스를 설정 합니다 .이에 대해서는 이후 섹션에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-327">The last line sets up data access for the app, which will be shown in a later section.</span></span>

<span data-ttu-id="8dd62-328">이 앱은 실제로 영역을 사용 하지 않으므로 영역 등록 호출을 마이그레이션하기 위해 수행 해야 하는 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-328">Since this app isn't actually using areas, there's nothing that needs to be done to migrate the area registration call.</span></span> <span data-ttu-id="8dd62-329">앱에서 영역을 마이그레이션해야 하는 경우 문서에서 [ASP.NET Core 영역을 구성 하는 방법을 지정](/aspnet/core/mvc/controllers/areas)합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-329">If your app does need to migrate areas, the [docs specify how to configure areas in ASP.NET Core](/aspnet/core/mvc/controllers/areas).</span></span>

<span data-ttu-id="8dd62-330">전역 필터를 등록 하는 호출은 `FilterConfig` 응용 프로그램의 *App_Start* 폴더에 있는 클래스에 대 한 도우미를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-330">The call to register global filters invokes a helper on the `FilterConfig` class in the app's *App_Start* folder:</span></span>

```csharp
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new HandleErrorAttribute());
}
```

<span data-ttu-id="8dd62-331">앱에 추가 되는 유일한 특성은 ASP.NET MVC 필터입니다 `HandleErrorAttribute` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-331">The only attribute added to the app is the ASP.NET MVC filter, `HandleErrorAttribute`.</span></span> <span data-ttu-id="8dd62-332">이 필터는 예외가 요청의 일부로 발생 하는 경우 예외 정보가 아닌 기본 작업 및 뷰가 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-332">This filter ensures that when an exception occurs as part of a request, a default action and view are displayed, rather than the exception details.</span></span> <span data-ttu-id="8dd62-333">ASP.NET Core에서는 미들웨어를 통해 동일한 기능을 수행 `UseExceptionHandler` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-333">In ASP.NET Core, this same functionality is performed by the `UseExceptionHandler` middleware.</span></span> <span data-ttu-id="8dd62-334">자세한 오류 메시지는 기본적으로 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-334">The detailed error messages aren't enabled by default.</span></span> <span data-ttu-id="8dd62-335">미들웨어를 사용 하 여 구성 해야 합니다 `UseDeveloperExceptionPage` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-335">They must be configured using the `UseDeveloperExceptionPage` middleware.</span></span> <span data-ttu-id="8dd62-336">원래 앱과 일치 하도록이 동작을 구성 하려면 Startup.cs에서 다음 코드를 메서드의 시작 부분에 추가 해야 합니다 `Configure` . </span><span class="sxs-lookup"><span data-stu-id="8dd62-336">To configure this behavior to match the original app, the following code must be added to the start of the `Configure` method in *Startup.cs*:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
    }
    // ...
}
```

<span data-ttu-id="8dd62-337">이는 eShop 앱에서 사용 하는 유일한 필터를 담당 하며,이 경우 기본 제공 미들웨어를 사용 하 여 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-337">This takes care of the only filter used by the eShop app, and in this case it was done by using built-in middleware.</span></span> <span data-ttu-id="8dd62-338">앱에서 구성 해야 하는 전역 필터가 있는 경우이 작업은 `ConfigureServices` 이 챕터의 뒷부분에 나오는 메서드에 MVC가 추가 될 때 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-338">If you have global filters that must be configured in your app, this is done when MVC is added in the `ConfigureServices` method, which is shown later in this chapter.</span></span>

<span data-ttu-id="8dd62-339">마이그레이션해야 하는 MVC 관련 논리의 마지막 부분은 앱의 기본 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-339">The last piece of MVC-related logic that needs to be migrated are the app's default routes.</span></span> <span data-ttu-id="8dd62-340">에 대 한 호출은 `RouteConfig.RegisterRoutes(RouteTable.Routes)` MVC 경로 테이블을 `RegisterRoutes` 도우미 메서드에 전달 합니다. 그러면 앱이 시작 될 때 다음 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-340">The call to `RouteConfig.RegisterRoutes(RouteTable.Routes)` passes the MVC route table to the `RegisterRoutes` helper method, where the following code is executed when the app starts up:</span></span>

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.MapMvcAttributeRoutes();
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

    routes.MapRoute(
        name: "Default",
        url: "{controller}/{action}/{id}",
        defaults: new { controller = "Catalog", action = "Index", id = UrlParameter.Optional }
    );
}
```

<span data-ttu-id="8dd62-341">이 코드를 한 줄씩 수행 하면 첫 번째 줄에서 특성 경로에 대 한 지원을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-341">Taking this code line-by-line, the first line sets up support for attribute routes.</span></span> <span data-ttu-id="8dd62-342">이는 ASP.NET Core에 기본 제공 되므로 별도로 구성 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-342">This is built into ASP.NET Core, so it's unnecessary to configure it separately.</span></span> <span data-ttu-id="8dd62-343">마찬가지로 *{resource}.* s a s 파일은 ASP.NET Core에서 사용 되지 않으므로 이러한 경로를 무시할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-343">Likewise, *{resource}.axd* files aren't used with ASP.NET Core, so there's no need to ignore such routes.</span></span> <span data-ttu-id="8dd62-344">`MapRoute`메서드는 일반적인 경로 템플릿을 사용 하는 MVC에 대 한 기본값을 구성 합니다 `{controller}/{action}/{id}` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-344">The `MapRoute` method configures the default for MVC, which uses the typical `{controller}/{action}/{id}` route template.</span></span> <span data-ttu-id="8dd62-345">또한이 템플릿에 대 한 기본값을 지정 합니다 .이는 `CatalogController` 가 사용 되는 기본 컨트롤러이 `Index` 고 메서드는 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-345">It also specifies the defaults for this template, such that the `CatalogController` is the default controller used and the `Index` method is the default action.</span></span> <span data-ttu-id="8dd62-346">더 큰 앱은 `MapRoute` 추가 경로를 설정 하기 위해에 대 한 추가 호출을 포함 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-346">Larger apps will frequently include more calls to `MapRoute` to set up additional routes.</span></span>

<span data-ttu-id="8dd62-347">ASP.NET Core MVC는 [기존 라우팅 및 특성 라우팅을](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2)지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-347">ASP.NET Core MVC supports [conventional routing and attribute routing](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2).</span></span> <span data-ttu-id="8dd62-348">기존 라우팅은 앞에 나열 된 메서드에서 경로 테이블을 구성 하는 방법과 유사 `RegisterRoutes` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-348">Conventional routing is analogous to how the route table is configured in the `RegisterRoutes` method listed previously.</span></span> <span data-ttu-id="8dd62-349">*EShop* 앱에서 사용 되는 것과 같은 기본 경로를 사용 하 여 기존 라우팅을 설정 하려면 `Configure` *Startup.cs* 에서 메서드의 맨 아래에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-349">To set up conventional routing with a default route like the one used in the *eShop* app, add the following code to the bottom of the `Configure` method in *Startup.cs*:</span></span>

```csharp
app.UseMvc(routes =>
{
   routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
});
```

> [!NOTE]
> <span data-ttu-id="8dd62-350">ASP.NET Core 3.0 이상에서는 끝점을 사용 하도록 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-350">With ASP.NET Core 3.0 and later, this is changed to use endpoints.</span></span> <span data-ttu-id="8dd62-351">2.2 ASP.NET Core 초기 포트의 경우이는 기존 경로를 매핑하기 위한 적절 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-351">For the initial port to ASP.NET Core 2.2, this is the proper syntax for mapping conventional routes.</span></span>

<span data-ttu-id="8dd62-352">이러한 변경 내용을 적용 하면 `Configure` 메서드가 거의 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-352">With these changes in place, the `Configure` method is almost done.</span></span> <span data-ttu-id="8dd62-353">`app.Run` *헬로 월드* 를 인쇄 하는 원래 템플릿의 메서드</span><span class="sxs-lookup"><span data-stu-id="8dd62-353">The original template's `app.Run` method that prints *Hello World!*</span></span> <span data-ttu-id="8dd62-354">삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-354">should be deleted.</span></span> <span data-ttu-id="8dd62-355">이 시점에서 메서드는 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-355">At this point, the method is as shown here:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }

    app.UseStaticFiles();

    app.UseMvc(routes =>
    {
        routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
    });
}
```

<span data-ttu-id="8dd62-356">이제 MVC 서비스를 구성 하 고 나머지 응용 프로그램에서 DI (종속성 주입)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-356">Now it's time to configure MVC services, followed by the rest of the app's support for dependency injection (DI).</span></span> <span data-ttu-id="8dd62-357">지금까지 *eShopPorted* 프로젝트의 메서드는 `ConfigureServices` 비어 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-357">So far, the *eShopPorted* project's `ConfigureServices` method has remained empty.</span></span> <span data-ttu-id="8dd62-358">이제 채우기를 시작할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-358">Now it's time to start populating it.</span></span>

<span data-ttu-id="8dd62-359">먼저 ASP.NET Core MVC가 정상적으로 작동 하도록 하려면 다음을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-359">First, to get ASP.NET Core MVC to work properly, it needs to be added:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
}
```

<span data-ttu-id="8dd62-360">위의 코드는 MVC 기능을 작동 하는 데 필요한 최소 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-360">The preceding code is the minimal configuration required to get MVC features working.</span></span> <span data-ttu-id="8dd62-361">이 호출에서 구성할 수 있는 추가 기능이 많이 있지만 지금은 앱을 빌드하는 데 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-361">There are many additional features that can be configured from this call, but for now this will suffice to build the app.</span></span> <span data-ttu-id="8dd62-362">이 도구를 실행 하면 기본 요청은 제대로 라우팅됩니다. 그러나 아직 DI를 구성 하지 않았기 때문에 `CatalogController` 형식 구현이 아직 제공 되지 않았기 때문에 활성화 하는 동안 오류가 발생 `ICatalogService` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-362">Running it now routes the default request properly, but since we've not yet configured DI, an error occurs while activating `CatalogController`, because no implementation of type `ICatalogService` has been provided yet.</span></span> <span data-ttu-id="8dd62-363">나중에 MVC를 구성 하기 위해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-363">We'll return to configure MVC further in a moment.</span></span> <span data-ttu-id="8dd62-364">지금은 응용 프로그램의 종속성 주입을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-364">For now, let's migrate the app's dependency injection.</span></span>

#### <a name="migrate-dependency-injection-configuration"></a><span data-ttu-id="8dd62-365">종속성 주입 구성 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-365">Migrate dependency injection configuration</span></span>

<span data-ttu-id="8dd62-366">원래 앱의 *global.asax* 파일은 앱이 시작 될 때 호출 되는 다음 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-366">The original app's *Global.asax* file defines the following method, called when the app starts up:</span></span>

```csharp
protected IContainer RegisterContainer()
{
  var builder = new ContainerBuilder();

  builder.RegisterControllers(typeof(MvcApplication).Assembly);

  var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
  builder.RegisterModule(new ApplicationModule(mockData));

  var container = builder.Build();
  DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

  return container;
}
```

<span data-ttu-id="8dd62-367">이 코드는 [autofac](https://autofac.org/) 컨테이너를 구성 하 고, 구성 설정을 읽고, 실제 또는 모의 데이터를 사용할지 여부를 결정 하 고,이 설정을 autofac 모듈 (앱의 */모듈* 디렉터리에 있음)에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-367">This code configures an [Autofac](https://autofac.org/) container, reads a config setting to determine whether real or mock data should be used, and passes this setting into an Autofac module (found in the app's */Modules* directory).</span></span> <span data-ttu-id="8dd62-368">다행히 Autofac는 .NET Core를 지원 하므로 모듈을 직접 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-368">Fortunately, Autofac supports .NET Core, so the module can be migrated directly.</span></span> <span data-ttu-id="8dd62-369">새 프로젝트에 폴더를 복사 하 고 클래스의 네임 스페이스를 업데이트 하 고 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-369">Copy the folder into the new project and updates the class's namespace and it should compile.</span></span>

<span data-ttu-id="8dd62-370">ASP.NET Core는 종속성 주입을 기본적으로 지원 하지만 필요한 경우 Autofac와 같은 타사 컨테이너를 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-370">ASP.NET Core has built-in support for dependency injection, but you can wire up a third-party container such as Autofac easily if necessary.</span></span> <span data-ttu-id="8dd62-371">이 경우 앱은 이미 Autofac를 사용 하도록 구성 되었으므로 가장 간단한 방법은 사용을 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-371">In this case, since the app is already configured to use Autofac, the simplest solution is to maintain its usage.</span></span> <span data-ttu-id="8dd62-372">이렇게 하려면를 `ConfigureServices` 반환 하도록 메서드 시그니처를 수정 하 `IServiceProvider` 고, Autofac 컨테이너 인스턴스를 구성 하 여 메서드에서 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-372">To do so, the `ConfigureServices` method signature must be modified to return an `IServiceProvider`, and the Autofac container instance must be configured and returned from the method.</span></span>

<span data-ttu-id="8dd62-373">**참고:** .NET Core 3.0 이상에서 타사 DI 컨테이너를 통합 하는 프로세스가 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-373">**Note:** In .NET Core 3.0 and later, the process for integrating a third-party DI container has changed.</span></span>

<span data-ttu-id="8dd62-374">Autofac를 구성 하는 과정에는를 호출 해야 `builder.Populate(services)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-374">Part of configuring Autofac requires a call to `builder.Populate(services)`.</span></span> <span data-ttu-id="8dd62-375">이 확장은 NuGet 패키지에서 찾을 수 `Autofac.Extensions.DependencyInjection` 있습니다 .이 패키지는 코드를 컴파일하기 전에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-375">This extension is found in the `Autofac.Extensions.DependencyInjection` NuGet package, which must be installed before the code will compile.</span></span>

<span data-ttu-id="8dd62-376">`ConfigureServices`Autofac 컨테이너를 구성 하도록 수정 하 고 나면 다음과 같이 새 메서드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-376">After modifying `ConfigureServices` to configure an Autofac container, the new method is as shown here:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    bool useMockData = true; // TODO: read from config
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

<span data-ttu-id="8dd62-377">지금은의 설정이 `useMockData` 로 설정 됩니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-377">For now, the setting for `useMockData` is set to `true`.</span></span> <span data-ttu-id="8dd62-378">이 설정은 잠시 후에 구성에서 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-378">This setting will be read from configuration in a moment.</span></span> <span data-ttu-id="8dd62-379">이 시점에서 그림 4-12에 표시 된 것 처럼 앱이 컴파일되고 실행 될 때 성공적으로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-379">At this point, the app compiles and should load successfully when run, as shown in Figure 4-12.</span></span>

![그림 4-12](media/Figure4-12.png)

<span data-ttu-id="8dd62-381">**그림 4-12.**</span><span class="sxs-lookup"><span data-stu-id="8dd62-381">**Figure 4-12.**</span></span> <span data-ttu-id="8dd62-382">모의 데이터를 사용 하 여 로컬로 실행 되는 이식 된 *eShop* 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-382">Ported *eShop* app running locally with mock data.</span></span>

#### <a name="migrate-app-settings"></a><span data-ttu-id="8dd62-383">앱 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-383">Migrate app settings</span></span>

<span data-ttu-id="8dd62-384">ASP.NET Core은 기본적으로 파일 *의appsettings.js* 를 활용 하는 새 [구성 시스템](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-384">ASP.NET Core uses a new [configuration system](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2), which by default leverages an *appsettings.json* file.</span></span> <span data-ttu-id="8dd62-385">`CreateDefaultBuilder` *Program.cs* 에서를 사용 하 여 기본 구성이 이미 앱에 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-385">By using `CreateDefaultBuilder` in *Program.cs*, the default configuration is already set up in the app.</span></span> <span data-ttu-id="8dd62-386">구성에 액세스 하기 위해 클래스는 생성자에서 요청 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-386">To access configuration, classes just need to request it in their constructor.</span></span> <span data-ttu-id="8dd62-387">`Startup`클래스는 예외가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-387">The `Startup` class is no exception.</span></span> <span data-ttu-id="8dd62-388">의 구성과 나머지 앱에 대 한 액세스를 시작 하려면 `Startup` 해당 생성자에서의 인스턴스를 요청 합니다 `IConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-388">To start accessing configuration in `Startup` and the rest of the app, request an instance of `IConfiguration` from its constructor:</span></span>

```csharp
public Startup(IConfiguration configuration)
{
    Configuration = configuration;
}

public IConfiguration Configuration { get; }
```

<span data-ttu-id="8dd62-389">원래 앱은를 사용 하 여 해당 설정을 참조 `ConfigurationManager.AppSettings` 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-389">The original app referenced its settings using `ConfigurationManager.AppSettings`.</span></span> <span data-ttu-id="8dd62-390">이 용어의 모든 참조를 빠르게 검색 하면 새 앱에 필요한 설정 집합이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-390">A quick search for all references of this term yields the set of settings the new app needs.</span></span> <span data-ttu-id="8dd62-391">다음 두 가지 유형만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-391">There are only two:</span></span>

- `UseMockData`
- `UseCustomizationData`

<span data-ttu-id="8dd62-392">앱에 더 복잡 한 구성이 있는 경우, 특히 사용자 지정 구성 섹션을 사용 하는 경우에는 응용 프로그램 구성의 다른 부분에 개체를 만들고 바인딩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-392">If your app has more complex configuration, especially if it's using custom configuration sections, you'll probably want to create and bind objects to different parts of your app's configuration.</span></span> <span data-ttu-id="8dd62-393">이러한 형식은 [옵션 패턴](../../core/extensions/options.md)을 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-393">These types can then be accessed using the [options pattern](../../core/extensions/options.md).</span></span> <span data-ttu-id="8dd62-394">그러나 참조 된 문서에서 설명한 대로이 패턴은에서 사용 하지 않아야 `ConfigureServices` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-394">However, as noted in the referenced doc, this pattern shouldn't be used in `ConfigureServices`.</span></span> <span data-ttu-id="8dd62-395">대신, 이식 된 앱은 `UseMockData` 구성 값을 직접 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-395">Instead the ported app will reference the `UseMockData` configuration value directly.</span></span>

<span data-ttu-id="8dd62-396">먼저, 이식 된 앱의 파일을 수정 `appsettings.json` 하 고 루트에 두 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-396">First, modify the ported app's `appsettings.json` file and add the two settings in the root:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "true",
  "UseCustomizationData" :  "true"
}
```

<span data-ttu-id="8dd62-397">이제를 수정 `ConfigureServices` 하 여 `UseMockData` 속성에서 설정에 액세스 합니다 `Configuration` (이전에 값을로 설정한 경우 `true` ).</span><span class="sxs-lookup"><span data-stu-id="8dd62-397">Now, modify `ConfigureServices` to access the `UseMockData` setting from the `Configuration` property (where previously we set the value to `true`):</span></span>

```csharp
  bool useMockData = Configuration.GetValue<bool>("UseMockData");
```

<span data-ttu-id="8dd62-398">이 시점에서 설정은 구성에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-398">At this point, the setting is pulled from configuration.</span></span> <span data-ttu-id="8dd62-399">다른 설정인는 `UseCustomizationData` 클래스에서 사용 됩니다 `CatalogDBInitializer` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-399">The other setting, `UseCustomizationData`, is used by the `CatalogDBInitializer` class.</span></span> <span data-ttu-id="8dd62-400">이 클래스를 처음 이식 하는 경우에 대 한 액세스를 주석으로 처리 `ConfigurationManager.AppSettings["UseCustomizationData"]` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-400">When you first ported this class, you commented out the access to `ConfigurationManager.AppSettings["UseCustomizationData"]`.</span></span> <span data-ttu-id="8dd62-401">이제 ASP.NET Core 구성을 사용 하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-401">Now it's time to modify it to use ASP.NET Core configuration.</span></span> <span data-ttu-id="8dd62-402">다음과 같이의 생성자를 수정 합니다 `CatalogDBInitializer` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-402">Modify the constructor of `CatalogDBInitializer` as follows:</span></span>

```csharp
  // add using Microsoft.Extensions.Configuration
  public CatalogDBInitializer(CatalogItemHiLoGenerator indexGenerator,
      IConfiguration configuration)
  {
      this.indexGenerator = indexGenerator;
      useCustomizationData = configuration.GetValue<bool>("UseCustomizationData");
  }
```

<span data-ttu-id="8dd62-403">새 형식을 사용 하려면 웹 앱 내의 모든 구성에 대 한 액세스를 이러한 방식으로 수정 해야 합니다 `IConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-403">All access to configuration within the web app should be modified in this manner to use the new `IConfiguration` type.</span></span> <span data-ttu-id="8dd62-404">.NET Framework 구성에 액세스 해야 하는 종속성에는 웹 프로젝트에 추가 된 *app.config* 파일의 이러한 설정이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-404">Dependencies that require access to .NET Framework configuration can include such settings in an *app.config* file added to the web project.</span></span> <span data-ttu-id="8dd62-405">종속 프로젝트는와 함께 작동 `ConfigurationManager` 하 여 설정에 액세스할 수 있으며,이 방법을 이미 사용 하는 경우에는 변경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-405">The dependent projects can work with `ConfigurationManager` to access settings, and shouldn't require any changes if they already use this approach.</span></span> <span data-ttu-id="8dd62-406">그러나 ASP.NET Core 앱은 자신의 실행 파일로 실행 되기 때문에 *web.config* 를 참조 하지 않고 *app.config* 됩니다. 레거시 앱의 *web.config* 파일에서 ASP.NET Core 앱의 새 *app.config* 파일로 설정을 마이그레이션하면에서 해당 설정에 액세스 하는 데 사용 하는 구성 요소는 `ConfigurationManager` 계속 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-406">However, since ASP.NET Core apps run as their own executable, they don't reference *web.config* but rather *app.config*. By migrating settings from the legacy app's *web.config* file to a new *app.config* file in the ASP.NET Core app, components that use `ConfigurationManager` to access their settings will continue to function properly.</span></span>

<span data-ttu-id="8dd62-407">앱의 마이그레이션이 거의 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-407">The app's migration is nearly complete.</span></span> <span data-ttu-id="8dd62-408">유일 하 게 남은 태스크는 데이터 액세스 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-408">The only remaining task is data access configuration.</span></span>
  
## <a name="data-access-considerations"></a><span data-ttu-id="8dd62-409">데이터 액세스 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8dd62-409">Data access considerations</span></span>

<span data-ttu-id="8dd62-410">.NET Framework에서 실행 되는 ASP.NET Core 앱은 EF (Entity Framework)를 계속 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-410">ASP.NET Core apps running on .NET Framework can continue to leverage Entity Framework (EF).</span></span> <span data-ttu-id="8dd62-411">증분 마이그레이션을 수행 하는 경우 EF Core 사용 하기 위해 데이터 액세스를 수신 하기 전에 EF 6을 사용 하 여 앱이 작동 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-411">If performing an incremental migration, getting the app working with EF 6 before trying to port its data access to use EF Core may be worthwhile.</span></span> <span data-ttu-id="8dd62-412">이러한 방식으로 다른 마이그레이션 작업을 시작 하기 전에 앱의 마이그레이션 문제를 식별 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-412">In this way, any problems with the app's migration can be identified and addressed before another block of migration effort is begun.</span></span>

<span data-ttu-id="8dd62-413">이러한 작업을 수행 하는 동안에는이 작업이 Autofac에서 수행 되었으므로 eShop 샘플 마이그레이션에서 EF 6을 구성 하는 것은 특별 한 작업이 필요 하지 않습니다 `ApplicationModule` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-413">As it happens, configuring EF 6 in the eShop sample migration doesn't require any special work, since this work was performed in the Autofac `ApplicationModule`.</span></span> <span data-ttu-id="8dd62-414">유일한 문제는 현재 `CatalogDBContext` 클래스가 *web.config* 에서 연결 문자열을 읽으려고 시도 하는 것입니다. 이를 해결 하려면 연결 정보를 *appsettings.js* 에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-414">The only problem is that currently the `CatalogDBContext` class tries to read its connection string from *web.config*. To address this, the connection details need to be added to *appsettings.json*.</span></span> <span data-ttu-id="8dd62-415">그런 다음 생성 될 때 연결 문자열을에 전달 해야 합니다 `CatalogDBContext` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-415">Then the connection string must be passed into `CatalogDBContext` when it's created.</span></span>

<span data-ttu-id="8dd62-416">연결 문자열을 포함 하도록 *appsettings.js* 를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-416">Update the *appsettings.json* to include the connection string.</span></span> <span data-ttu-id="8dd62-417">전체 파일은 다음 위치에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-417">The full file is listed here:</span></span>

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=eShopPorted;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "false",
  "UseCustomizationData": "true"
}
```

<span data-ttu-id="8dd62-418">연결 문자열은가 만들어질 때 생성자에 전달 되어야 합니다 `DbContext` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-418">The connection string must be passed into the constructor when the `DbContext` is created.</span></span> <span data-ttu-id="8dd62-419">인스턴스는 Autofac에서 만들어지기 때문에에서 변경 해야 `ApplicationModule` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-419">Since the instances are created by Autofac, the change needs to be made in `ApplicationModule`.</span></span> <span data-ttu-id="8dd62-420">생성자의를 사용 하 여 모듈을 수정 하 `connectionString` 고 필드에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-420">Modify the module to take in a `connectionString` in its constructor and assign it to a field.</span></span> <span data-ttu-id="8dd62-421">그런 다음에 대 한 등록을 수정 `CatalogDBContext` 하 여 연결 문자열을 매개 변수로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-421">Then modify the registration for `CatalogDBContext` to add connection string as a parameter:</span></span>

```csharp
builder.RegisterType<CatalogDBContext>()
  .WithParameter("connectionString", _connectionString)
  .InstancePerLifetimeScope();
```

<span data-ttu-id="8dd62-422">매개 변수도 새 생성자 오버 로드에 추가 해야 합니다 `CatalogDBContext` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-422">The parameter must also be added to a new constructor overload in `CatalogDBContext` itself:</span></span>

```csharp
public CatalogDBContext(string connectionString) : base(connectionString)
{
}
```

<span data-ttu-id="8dd62-423">마지막으로, `ConfigureServices` 에서 연결 문자열을 읽고이를 `Config` 인스턴스화할 때에 전달 해야 합니다 `ApplicationModule` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-423">Finally, `ConfigureServices` must read the connection string from `Config` and pass it into the `ApplicationModule` when it instantiates it:</span></span>

```csharp
bool useMockData = Configuration.GetValue<bool>("UseMockData");
string connectionString = Configuration.GetConnectionString("DefaultConnection");
builder.RegisterModule(new ApplicationModule(useMockData, connectionString));
```

<span data-ttu-id="8dd62-424">이 코드를 사용 하는 경우 앱은 이전과 마찬가지로 실행 되어가 일 때 SQL Server 데이터베이스에 연결 `UseMockData` 합니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-424">With this code in place, the app runs as it did before, connecting to a SQL Server database when `UseMockData` is `false`.</span></span>

<span data-ttu-id="8dd62-425">이 시점에서 앱을 배포 하 고 프로덕션 환경에서 실행할 수 있습니다 .이 시점에서 ASP.NET Core로 변환 되지만 .NET Framework 및 EF 6에서 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-425">The app can be deployed and run in production at this point, converted to ASP.NET Core but still running on .NET Framework and EF 6.</span></span> <span data-ttu-id="8dd62-426">원하는 경우 앱을 마이그레이션하여 .NET Core에서 실행 하 고 Entity Framework Core 수 있습니다. 그러면 이전 장에 설명 된 추가 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-426">If desired, the app can be migrated to run on .NET Core and Entity Framework Core, which will bring additional advantages described in earlier chapters.</span></span> <span data-ttu-id="8dd62-427">Entity Framework와 관련 하 여 [이 설명서는 EF Core와 EF 6을 비교](/ef/efcore-and-ef6/) 하 고 각 수십 개의 개별 기능을 지 원하는 라이브러리를 보여 주는 표를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-427">Specific to Entity Framework, [this documentation compares EF Core and EF 6](/ef/efcore-and-ef6/) and includes a grid showing which library supports each of dozens of individual features.</span></span>

### <a name="migrate-to-entity-framework-core"></a><span data-ttu-id="8dd62-428">Entity Framework Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8dd62-428">Migrate to Entity Framework Core</span></span>

<span data-ttu-id="8dd62-429">EF Core로 마이그레이션하도록 결정 하는 것으로 가정 하면 특히 원래 앱에서 코드 기반 모델 접근 방법을 사용 하는 경우 단계가 매우 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-429">Assuming a decision is made to migrate to EF Core, the steps can be fairly straightforward, especially if the original app used a code-based model approach.</span></span> <span data-ttu-id="8dd62-430">[EF 6에서 EF Core로 포트를 준비할](/ef/efcore-and-ef6/porting/)때 사용할 EF Core 대상 버전의 기능 가용성을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-430">When [preparing to port from EF 6 to EF Core](/ef/efcore-and-ef6/porting/), review the availability of features in the destination version of EF Core you'll be using.</span></span> <span data-ttu-id="8dd62-431">[및 EDMX 기반 모델과](/ef/efcore-and-ef6/porting/port-edmx) [코드 기반 모델의](/ef/efcore-and-ef6/porting/port-code)포팅 포팅에 대 한 설명서를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-431">Review the documentation on [porting from and EDMX-based model](/ef/efcore-and-ef6/porting/port-edmx) versus [porting from a code-based model](/ef/efcore-and-ef6/porting/port-code).</span></span>

<span data-ttu-id="8dd62-432">EF Core 2.2으로 업그레이드 하려면 적절 한 NuGet 패키지를 추가 하 고 네임 스페이스를 업데이트 하는 것이 관련 된 기본 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-432">To upgrade to EF Core 2.2, the basic steps involved are to add the appropriate NuGet package(s) and update namespaces.</span></span> <span data-ttu-id="8dd62-433">그런 다음 연결 문자열을 형식으로 전달 하는 방법 및 종속성 주입을 위해 연결 문자열을 연결 하는 `DbContext` 방법을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-433">Then adjust how the connection string is passed to the `DbContext` type and how they're wired up for dependency injection.</span></span>

<span data-ttu-id="8dd62-434">EF Core는 프로젝트에 대 한 패키지 참조로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-434">EF Core is added as a package reference to the project:</span></span>

```xml
<PackageReference Include="Microsoft.EntityFrameworkCore" Version="2.2.6" />
```

<span data-ttu-id="8dd62-435">EF 6에 대 한 참조가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-435">The reference to EF 6 is removed:</span></span>

```xml
<PackageReference Include="EntityFramework" Version="6.2.0" />
```

<span data-ttu-id="8dd62-436">컴파일러는 및에서 오류를 보고 합니다 `CatalogDBContext` `CatalogDBInitializer` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-436">The compiler will report errors in `CatalogDBContext` and `CatalogDBInitializer`.</span></span> <span data-ttu-id="8dd62-437">`CatalogDbContext` 이전 네임 스페이스가 제거 되 고로 대체 되어야 `Microsoft.EntityFrameworkCore` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-437">`CatalogDbContext` needs to have the old namespaces removed and replaced with `Microsoft.EntityFrameworkCore`.</span></span> <span data-ttu-id="8dd62-438">해당 생성자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-438">Its constructors can be removed.</span></span> <span data-ttu-id="8dd62-439">`DbModelBuilder` 는로 바꾸어야 합니다 `ModelBuilder` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-439">`DbModelBuilder` should be replaced with `ModelBuilder`.</span></span> <span data-ttu-id="8dd62-440">형식을 구성 하기 위한 도우미 메서드는를 구현 하는 별도의 클래스로 이동 됩니다 `IEntityTypeConfiguration<T>` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-440">The helper methods for configuring types are moved to separate classes implementing `IEntityTypeConfiguration<T>`.</span></span> <span data-ttu-id="8dd62-441">그런 다음 `CatalogDBContext` 클래스의 `OnModelCreating` 메서드는 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-441">Then the `CatalogDBContext` class's `OnModelCreating` method simply becomes:</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder builder)
{
    builder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());

    base.OnModelCreating(builder);
}
```

<span data-ttu-id="8dd62-442">관련 된 다른 변경 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-442">Other changes involved include:</span></span>

- <span data-ttu-id="8dd62-443">`HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` 로 바뀜 `ValueGeneratedNever()`</span><span class="sxs-lookup"><span data-stu-id="8dd62-443">`HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` replaced with `ValueGeneratedNever()`</span></span>
- <span data-ttu-id="8dd62-444">`HasRequired<T>` 로 바뀜 `HasOne<T>`</span><span class="sxs-lookup"><span data-stu-id="8dd62-444">`HasRequired<T>` replaced with `HasOne<T>`</span></span>
- <span data-ttu-id="8dd62-445">설치 된 `Microsoft.EntityFrameworkCore.Relational` 패키지</span><span class="sxs-lookup"><span data-stu-id="8dd62-445">Installed `Microsoft.EntityFrameworkCore.Relational` package</span></span>
- <span data-ttu-id="8dd62-446">생성자를 추가 하 `CatalogDBContext` 여 `DbContextOptions` 기본 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-446">Add a constructor to `CatalogDBContext` taking `DbContextOptions` and passing it to the base constructor</span></span>

<span data-ttu-id="8dd62-447">에 대 한 예제 구성 클래스 `CatalogType` 는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-447">An example configuration class for `CatalogType` is shown here:</span></span>

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

namespace eShopPorted.Models.Config
{
    public class CatalogTypeConfig : IEntityTypeConfiguration<CatalogType>
    {
        public void Configure(EntityTypeBuilder<CatalogType> builder)
        {
            builder.ToTable(nameof(CatalogType));

            builder.HasKey(ci => ci.Id);

            builder.Property(ci => ci.Id)
               .IsRequired();

            builder.Property(cb => cb.Type)
                .IsRequired()
                .HasMaxLength(100);
        }
    }
}
```

<span data-ttu-id="8dd62-448">`CatalogDBInitializer`및 해당 기본 클래스는 `CreateDatabaseIfNotExists<T>` EF Core와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-448">The `CatalogDBInitializer` and its base class, `CreateDatabaseIfNotExists<T>`, are incompatible with EF Core.</span></span> <span data-ttu-id="8dd62-449">이 클래스의 목적은 데이터베이스를 만들고 시드 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-449">The purpose of this class is to create and seed the database.</span></span> <span data-ttu-id="8dd62-450">EF Core를 사용 하면 다음 메서드를 사용 하 여 [에 `DbContext` 대 한 연결 된 데이터베이스를 만들고 삭제할](/ef/core/managing-schemas/ensure-created) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-450">Using EF Core will [create and drop the associated database for a `DbContext`](/ef/core/managing-schemas/ensure-created) using these methods:</span></span>

```csharp
dbContext.Database.EnsureDeleted();
dbContext.Database.EnsureCreated();
```

<span data-ttu-id="8dd62-451">EF Core에서 데이터 시드는 수동 스크립트를 사용 하거나 유형 구성의 일부로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-451">Seeding data in EF Core can be done with manual scripts, or as part of the type configuration.</span></span> <span data-ttu-id="8dd62-452">다른 엔터티 속성과 함께를 사용 하 여 클래스에서 초기값 데이터를 구성할 수 있습니다 `IEntityTypeConfiguration` `builder.HasData()` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-452">Along with other entity properties, seed data can be configured in `IEntityTypeConfiguration` classes by using `builder.HasData()`.</span></span> <span data-ttu-id="8dd62-453">원래 앱이 *설치* 디렉터리의 CSV 파일에서 초기값 데이터를 로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-453">The original app loaded seed data from CSV files in the *Setup* directory.</span></span> <span data-ttu-id="8dd62-454">항목의 수가 적은 경우에는 이러한 데이터 레코드를 엔터티 구성의 일부로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-454">Given that there are only a handful of items, these data records can instead be added as part of the entity configuration.</span></span> <span data-ttu-id="8dd62-455">이 방법은 자주 변경 되지 않는 테이블의 조회 데이터에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-455">This approach works well for lookup data in tables that change infrequently.</span></span> <span data-ttu-id="8dd62-456">다음을 `CatalogTypeConfig` 의 메서드에 추가 하면 `Configure` 데이터베이스를 만들 때 연결 된 행이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-456">Adding the following to `CatalogTypeConfig`'s `Configure` method ensures the associated rows are present when the database is created:</span></span>

```csharp
builder.HasData(
    new CatalogType { Id = 1, Type = "Mug" },
    new CatalogType { Id = 2, Type = "T-Shirt" },
    new CatalogType { Id = 3, Type = "Sheet" },
    new CatalogType { Id = 4, Type = "USB Memory Stick" }
);
```

<span data-ttu-id="8dd62-457">초기 앱에는 `PreconfiguredData` 및에 대 한 데이터를 포함 하는 클래스가 포함 되어 `CatalogBrand` `CatalogType` 있으므로이 메서드를 사용 하 여 `HasData` 호출은 다음과 같이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-457">The initial app includes a `PreconfiguredData` class, which includes data for `CatalogBrand` and `CatalogType`, so using this method the `HasData` call reduces to:</span></span>

```csharp
builder.HasData(
    PreconfiguredData.GetPreconfiguredCatalogBrands()
);
```

<span data-ttu-id="8dd62-458">`CatalogItem`또한에서 데이터를 끌어올 수 `PreconfiguredData` 있으며, 연결 된 이미지가 소스 제어에 유지 되는 것으로 가정 합니다. 즉, 앱이 작동 하는 데 필요한 마지막 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-458">The `CatalogItem` data can also be pulled from `PreconfiguredData`, and assuming the associated images are kept in source control, that is the last table needed for the app to function.</span></span> <span data-ttu-id="8dd62-459">`CatalogDBInitializer`클래스에 대 한 모든 참조와 함께 클래스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-459">The `CatalogDBInitializer` class can be removed, along with any references to it.</span></span> <span data-ttu-id="8dd62-460">`CatalogItemHiLoGenerator`디렉터리의 클래스와 SQL 파일도 `Infrastructure` 제거 됩니다 (의) .이 파일에 대 한 참조도 함께 제거 `CatalogService` 됩니다 `ApplicationModule` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-460">The `CatalogItemHiLoGenerator` class and the SQL files in the `Infrastructure` directory are also removed, along with any references to them (in `CatalogService`, `ApplicationModule`).</span></span>

<span data-ttu-id="8dd62-461">에 대 한 특수 키 생성기 클래스를 제거 하면 `CatalogItem` 이제에서이 코드가 제거 됩니다 `CatalogItemConfig` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-461">With the elimination of the special key generator classes for `CatalogItem`, this code now is removed from `CatalogItemConfig`:</span></span>

```csharp
builder.Property(ci => ci.Id)
    .ValueGeneratedNever()
    .IsRequired();
```

<span data-ttu-id="8dd62-462">이러한 수정 작업을 수행 하면 ASP.NET Core 앱은 빌드되고 아직 종속성 주입을 위해 구성 해야 하는 EF Core에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-462">With these modifications, the ASP.NET Core app builds, but it doesn't yet work with EF Core, which must still be configured for dependency injection.</span></span> <span data-ttu-id="8dd62-463">EF Core를 사용 하 여 구성 하는 가장 간단한 방법은 `ConfigureServices` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-463">With EF Core, the simplest way to configure it is in `ConfigureServices`:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    bool useMockData = Configuration.GetValue<bool>("UseMockData");
    if (!useMockData)
    {
        string connectionString = Configuration.GetConnectionString("DefaultConnection");

        services.AddDbContext<CatalogDBContext>(options =>
            options.UseSqlServer(connectionString)
        );
    }

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

<span data-ttu-id="8dd62-464">Autofac의 최종 버전은 `ApplicationModule` 앱이 모의 데이터를 사용 하도록 구성 되었는지 여부에 따라 한 가지 유형만 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-464">The final version of Autofac's `ApplicationModule` only configures one type, depending on whether the app is configured to use mock data:</span></span>

```csharp
public class ApplicationModule : Module
{
    private bool _useMockData;

    public ApplicationModule(bool useMockData)
    {
        _useMockData = useMockData;
    }

    protected override void Load(ContainerBuilder builder)
    {
        if (_useMockData)
        {
            builder.RegisterType<CatalogServiceMock>()
                .As<ICatalogService>()
                .SingleInstance();
        }
        else
        {
            builder.RegisterType<CatalogService>()
                .As<ICatalogService>()
                .InstancePerLifetimeScope();
        }
    }
}
```

<span data-ttu-id="8dd62-465">이식 된 앱은 실행 되지만 비 모의 데이터를 사용 하도록 구성 된 경우에는 데이터를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-465">The ported app runs, but doesn't display any data if configured to use non-mock data.</span></span> <span data-ttu-id="8dd62-466">를 통해 추가 된 초기값 데이터는 `HasData` 마이그레이션이 적용 될 때만 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-466">The seed data added through `HasData` is only inserted when migrations are applied.</span></span> <span data-ttu-id="8dd62-467">원본 앱은 마이그레이션을 사용 하지 않았으며, 있는 경우에는 그대로 마이그레이션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-467">The source app didn't use migrations, and if it had, they wouldn't migrate as-is.</span></span> <span data-ttu-id="8dd62-468">가장 좋은 방법은 새 마이그레이션 스크립트를 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-468">The best approach is to start with a new migration script.</span></span> <span data-ttu-id="8dd62-469">이렇게 하려면에 대 한 패키지 참조를 추가 하 `Microsoft.EntityFrameworkCore.Design` 고 프로젝트 루트에서 터미널 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-469">To do this, add a package reference for `Microsoft.EntityFrameworkCore.Design` and open a terminal window in the project root.</span></span> <span data-ttu-id="8dd62-470">다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-470">Then run:</span></span>

```dotnetcli
dotnet ef migrations add Initial
```

<span data-ttu-id="8dd62-471">기존 *eShopPorted* 데이터베이스 (있는 경우)를 삭제 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-471">Drop the existing *eShopPorted* database if it exists, then run:</span></span>

```dotnetcli
dotnet ef database update
```

<span data-ttu-id="8dd62-472">이렇게 하면 데이터베이스가 만들어지고 시드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-472">This creates and seeds the database.</span></span> <span data-ttu-id="8dd62-473">이제 몇 개의 작은 업데이트를 처리할 수 있는 몇 개의 작은 업데이트가 실행 될 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-473">It's now ready to run, with a few small updates left to address.</span></span>

## <a name="fix-all-todo-tasks"></a><span data-ttu-id="8dd62-474">모든 TODO 작업 수정</span><span class="sxs-lookup"><span data-stu-id="8dd62-474">Fix all TODO tasks</span></span>

<span data-ttu-id="8dd62-475">이 시점에서 이식 된 앱을 실행 하면 페이지에 표시 되는 그림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-475">Running the ported app at this point reveals that no pictures are shown on the page.</span></span> <span data-ttu-id="8dd62-476">`PictureUri`의 속성이 설정 되지 않기 때문입니다 `CatalogItem` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-476">This is because the `PictureUri` property of `CatalogItem` is never set.</span></span> <span data-ttu-id="8dd62-477">`TODO`Visual Studio의 **작업 목록** 을 사용 하 여 만든 항목의 목록을 보면 그대로 남아 있는 항목은 `CatalogController` "Wwwroot에서 pic를 참조 하십시오."에 대 한 참고 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-477">Looking at the list of `TODO` items we created using Visual Studio's **Task List**, the only one that remains is in `CatalogController`, with a note to "Reference pic from wwwroot."</span></span> <span data-ttu-id="8dd62-478">문제의 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-478">The code in question is:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    //TODO: Reference pic from wwwroot
    //item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

<span data-ttu-id="8dd62-479">가장 간단한 픽스는 사이트의 공용 *wwwroot/Pics* 디렉터리에서 공용 이미지 파일을 참조 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-479">The simplest fix is to reference the public image files in the site's public *wwwroot/Pics* directory.</span></span> <span data-ttu-id="8dd62-480">이 작업을 수행 하려면 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-480">This task can be accomplished by replacing the method with the following code:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = $"/Pics/{item.Id}.png";
}
```

<span data-ttu-id="8dd62-481">이러한 변경으로 응용 프로그램을 실행 하면 이미지가 이전 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-481">With this change, running the app reveals the images work as before.</span></span>

## <a name="additional-mvc-customizations"></a><span data-ttu-id="8dd62-482">추가 MVC 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8dd62-482">Additional MVC customizations</span></span>

<span data-ttu-id="8dd62-483">*EShopLegacyMVC* 앱은 매우 간단 하므로 기본 MVC 동작을 기준으로 구성 하는 것이 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-483">The *eShopLegacyMVC* app is fairly simple, so there isn't much to configure in terms of default MVC behavior.</span></span> <span data-ttu-id="8dd62-484">그러나 CORS, 필터 및 경로 제약 조건과 같은 추가 MVC 구성 요소를 구성 해야 하는 경우 일반적으로가 호출 되는에서이 정보를 제공 `Startup.ConfigureServices` `UseMvc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-484">However, if you do need to configure additional MVC components, such as CORS, filters, and route constraints, you generally provide this information in `Startup.ConfigureServices`, where `UseMvc` is called.</span></span> <span data-ttu-id="8dd62-485">예를 들어 다음 코드 목록에서는 [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) 를 구성 하 고 전역 작업 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-485">For example, the following code listing configures [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) and sets up a global action filter:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddCors(options =>
    {
        options.AddPolicy(MyAllowSpecificOrigins,
            builder =>
                builder.WithOrigins("http://example.com", "http://www.contoso.com")
                    .AllowAnyHeader()
                    .AllowAnyMethod());
    });

    services.AddMvc(options =>
    {
      options.Filters.Add(new SampleGlobalActionFilter());
    }).SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```

> [!Note]
> <span data-ttu-id="8dd62-486">CORS 구성을 완료 하려면에서도 호출 해야 합니다 `app.UseCors()` `Configure` .</span><span class="sxs-lookup"><span data-stu-id="8dd62-486">To finish configuring CORS, you must also call `app.UseCors()` in `Configure`.</span></span>

<span data-ttu-id="8dd62-487">[사용자 지정 모델 바인더](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), 포맷터 등을 추가 하는 등의 기타 고급 시나리오는 자세한 ASP.NET Core 문서에 설명 되어 있습니다. 일반적으로 개별 컨트롤러 또는 작업에 적용 되거나 이전 코드 목록에 표시 된 것과 동일한 옵션 방법을 사용 하 여 전역적으로 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-487">Other advanced scenarios, like adding [custom model binders](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), formatters, and more are covered in the detailed ASP.NET Core docs. Generally these can be applied on an individual controller or action basis, or globally using the same options approach shown in the previous code listing.</span></span>

## <a name="other-dependencies"></a><span data-ttu-id="8dd62-488">기타 종속성</span><span class="sxs-lookup"><span data-stu-id="8dd62-488">Other dependencies</span></span>

<span data-ttu-id="8dd62-489">WCF 클라이언트 형식 및 추적 코드와 같이 레거시 구성 모델에 대 한 종속성이 있는 .NET Framework 기능을 사용 하는 종속성은 이식 될 때 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-489">Dependencies that use .NET Framework features that had a dependency on the legacy configuration model, such as the WCF client type and tracing code, must be modified when ported.</span></span> <span data-ttu-id="8dd62-490">이러한 형식이 구성 정보를 직접 가져오도록 하는 대신 코드에서 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-490">Rather than having these types pull in their configuration information directly, they should be configured in code.</span></span> <span data-ttu-id="8dd62-491">예를 들어 ASP.NET 앱의 *web.config* 에 구성 된 WCF 서비스에 대 한 연결은 `basicHttpBinding` 대신 다음 코드를 사용 하 여 프로그래밍 방식으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-491">For example, a connection to a WCF service that was configured in an ASP.NET app's *web.config* to use `basicHttpBinding` could instead be configured programmatically with the following code:</span></span>

```csharp
var binding = new BasicHttpBinding();
binding.MaxReceivedMessageSize = 2_000_000;

var endpointAddress = new EndpointAddress("http://localhost:9200/ExampleService");

var myClient = new MyServiceClient(binding, endpointAddress);
```

<span data-ttu-id="8dd62-492">WCF 클라이언트와 기타 .NET Framework 형식에는 설정에 대 한 구성 파일을 의존 하는 대신 해당 설정이 코드에 지정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-492">Rather than relying on config files for its settings, WCF clients and other .NET Framework types should have their settings specified in code.</span></span> <span data-ttu-id="8dd62-493">이러한 방식으로 구성 된 이러한 형식은 ASP.NET Core 2.2 앱에서 계속 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-493">Configured in this manner, these types can continue to work in ASP.NET Core 2.2 apps.</span></span>

## <a name="references"></a><span data-ttu-id="8dd62-494">참조</span><span class="sxs-lookup"><span data-stu-id="8dd62-494">References</span></span>

- [<span data-ttu-id="8dd62-495">eShopModernizing GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="8dd62-495">eShopModernizing GitHub repository</span></span>](https://github.com/dotnet-architecture/eShopModernizing)
- [<span data-ttu-id="8dd62-496">.NET 업그레이드 도우미 도구</span><span class="sxs-lookup"><span data-stu-id="8dd62-496">.NET Upgrade Assistant tool</span></span>](https://aka.ms/dotnet-upgrade-assistant)
- [<span data-ttu-id="8dd62-497">API 및 ViewModels 도메인 모델을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8dd62-497">Your API and ViewModels Should Not Reference Domain Models</span></span>](https://ardalis.com/your-api-and-view-models-should-not-reference-domain-models/)
- [<span data-ttu-id="8dd62-498">개발자 예외 페이지 미들웨어</span><span class="sxs-lookup"><span data-stu-id="8dd62-498">Developer Exception Page Middleware</span></span>](/aspnet/core/fundamentals/error-handling#developer-exception-page)
- [<span data-ttu-id="8dd62-499">EF Core HasData 심층 살펴보기</span><span class="sxs-lookup"><span data-stu-id="8dd62-499">Deep Dive into EF Core HasData</span></span>](/archive/msdn-magazine/2018/august/data-points-deep-dive-into-ef-core-hasdata-seeding)

>[!div class="step-by-step"]
><span data-ttu-id="8dd62-500">[이전](more-migration-scenarios.md)
>[다음](deployment-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="8dd62-500">[Previous](more-migration-scenarios.md)
[Next](deployment-scenarios.md)</span></span>
