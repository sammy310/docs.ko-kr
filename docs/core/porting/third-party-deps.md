---
title: 코드를 포팅하기 위해 종속성 분석
description: .NET Framework에서 .NET으로 프로젝트를 포팅하기 위해 외부 종속성을 분석하는 방법을 알아봅니다.
author: cartermp
ms.date: 03/04/2021
ms.openlocfilehash: 4619243cf300e248be45e4b2a4d5541c3b3e1cb5
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604920"
---
# <a name="analyze-your-dependencies-to-port-code-from-net-framework-to-net"></a><span data-ttu-id="97ced-103">.NET Framework에서 .NET으로 코드를 포팅하기 위한 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="97ced-103">Analyze your dependencies to port code from .NET Framework to .NET</span></span>

<span data-ttu-id="97ced-104">코드를 .NET 또는 .NET Standard로 포팅하려면 종속성을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-104">To port your code to .NET or .NET Standard, you must understand your dependencies.</span></span> <span data-ttu-id="97ced-105">외부 종속성은 프로젝트에서 참조하지만 직접 빌드하지 않는 NuGet 패키지 또는 `.dll` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-105">External dependencies are the NuGet packages or `.dll` files you reference in your project, but that you don't build yourself.</span></span>

<span data-ttu-id="97ced-106">코드를 .NET Standard 2.0 이하로 포팅하면 .NET Framework 및 .NET 모두에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-106">Porting your code to .NET Standard 2.0 or below ensures that it can be used with both .NET Framework and .NET.</span></span> <span data-ttu-id="97ced-107">그러나 .NET Framework에서 라이브러리를 사용할 필요가 없는 경우 최신 버전의 .NET을 대상으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-107">However, if you don't need to use the library with .NET Framework, consider targeting the latest version of .NET.</span></span>

## <a name="migrate-your-nuget-packages-to-packagereference"></a><span data-ttu-id="97ced-108">NuGet 패키지를 `PackageReference`로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="97ced-108">Migrate your NuGet packages to `PackageReference`</span></span>

<span data-ttu-id="97ced-109">.NET에서는 NuGet 참조에 [_packages.config_](/nuget/reference/packages-config) 파일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-109">.NET can't use the [_packages.config_](/nuget/reference/packages-config) file for NuGet references.</span></span> <span data-ttu-id="97ced-110">.NET 및 .NET Framework는 모두 [PackageReference](/nuget/consume-packages/package-references-in-project-files)를 사용하여 패키지 종속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-110">Both .NET and .NET Framework can use [PackageReference](/nuget/consume-packages/package-references-in-project-files) to specify package dependencies.</span></span> <span data-ttu-id="97ced-111">_packages.config_ 를 사용하여 프로젝트의 패키지를 지정하는 경우 `PackageReference` 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-111">If you're using _packages.config_ to specify your packages in your project, convert it to the `PackageReference` format.</span></span>

<span data-ttu-id="97ced-112">마이그레이션 방법에 대한 자세한 내용은 [packages.config에서 PackageReference로 마이그레이션](/nuget/reference/migrate-packages-config-to-package-reference) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97ced-112">To learn how to migrate, see the [Migrate from packages.config to PackageReference](/nuget/reference/migrate-packages-config-to-package-reference) article.</span></span>

## <a name="upgrade-your-nuget-packages"></a><span data-ttu-id="97ced-113">NuGet 패키지 업그레이드</span><span class="sxs-lookup"><span data-stu-id="97ced-113">Upgrade your NuGet packages</span></span>

<span data-ttu-id="97ced-114">프로젝트를 `PackageReference` 형식으로 마이그레이션한 후 패키지가 .NET과 호환되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-114">After you migrate your project to the `PackageReference` format, verify if your packages are compatible with .NET.</span></span>

<span data-ttu-id="97ced-115">먼저 패키지를 가능한 최신 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-115">First, upgrade your packages to the latest version that you can.</span></span> <span data-ttu-id="97ced-116">Visual Studio의 NuGet 패키지 관리자 UI를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-116">This can be done with the NuGet Package Manager UI in Visual Studio.</span></span> <span data-ttu-id="97ced-117">최신 버전의 패키지 종속성은 .NET Core와 이미 호환될 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-117">It's likely that newer versions of your package dependencies are already compatible with .NET Core.</span></span>

## <a name="analyze-your-package-dependencies"></a><span data-ttu-id="97ced-118">패키지 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="97ced-118">Analyze your package dependencies</span></span>

<span data-ttu-id="97ced-119">변환 및 업그레이드된 패키지 종속성이 .NET Core에서 작동하는지 확인하지 않은 경우 다음과 같은 몇 가지 방법으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-119">If you haven't already verified that your converted and upgraded package dependencies work on .NET Core, there are a few ways that you can achieve that:</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="97ced-120">nuget.org를 사용하여 NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="97ced-120">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="97ced-121">패키지 페이지의 **종속성** 섹션 아래에 있는 [nuget.org](https://www.nuget.org/)에서 각 패키지가 지원하는 TFM(대상 프레임워크 모니커)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-121">You can see the Target Framework Monikers (TFMs) that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="97ced-122">사이트를 사용하여 호환성을 쉽게 확인할 수 있지만, 일부 패키지의 **종속성** 정보는 사이트에 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-122">Although using the site is an easier method to verify the compatibility, **Dependencies** information isn't available on the site for all packages.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="97ced-123">NuGet 패키지 탐색기를 사용하여 NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="97ced-123">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="97ced-124">NuGet 패키지 자체는 플랫폼 관련 어셈블리를 포함하는 폴더 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-124">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="97ced-125">따라서 패키지 내에 호환되는 어셈블리를 포함하는 폴더인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-125">Check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="97ced-126">NuGet 패키지 폴더를 검사하는 가장 쉬운 방법은 [NuGet 패키지 탐색기](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) 도구를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-126">The easiest way to inspect NuGet package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="97ced-127">설치한 후 다음 단계를 사용하여 폴더 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-127">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="97ced-128">NuGet 패키지 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-128">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="97ced-129">**온라인 피드에서 패키지 열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-129">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="97ced-130">패키지의 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-130">Search for the name of the package.</span></span>
4. <span data-ttu-id="97ced-131">검색 결과에서 패키지 이름을 선택하고 **열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-131">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="97ced-132">오른쪽에서 *lib* 폴더를 확장하고 폴더 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-132">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="97ced-133">`netstandardX.Y`, `netX.Y` 또는 `netcoreappX.Y` 패턴 중 하나를 사용하는 이름을 가진 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-133">Look for a folder with names using one the following patterns: `netstandardX.Y`, `netX.Y`, or `netcoreappX.Y`.</span></span>

<span data-ttu-id="97ced-134">이러한 값은 모두 .NET과 호환되는 [.NET Standard](../../standard/net-standard.md), .NET, .NET Core의 버전에 매핑되는 [TFM(대상 프레임워크 모니커)](../../standard/frameworks.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-134">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of [.NET Standard](../../standard/net-standard.md), .NET, and .NET Core, which are all compatible with .NET.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97ced-135">패키지에서 지원하는 TFM을 확인하는 경우 `netstandard*` 이외의 TFM은 .NET 5, .NET Core, .NET Framework와 같은 특정 .NET 구현을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-135">When looking at the TFMs that a package supports, note that a TFM other than `netstandard*` targets a specific implementation of .NET, such as .NET 5, .NET Core, or .NET Framework.</span></span> <span data-ttu-id="97ced-136">.NET 5부터 `net*` TFM(운영 체제 지정 없이)은 `netstandard*`를 [이식 가능한 대상](../../standard/net-standard.md#net-5-and-net-standard)으로 효과적으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-136">Starting with .NET 5, the `net*` TFM (without an operating system designation) effectively replaces `netstandard*` as a [portable target](../../standard/net-standard.md#net-5-and-net-standard).</span></span> <span data-ttu-id="97ced-137">예를 들어 `net5.0`은 .NET 5 API 화면을 대상으로 하고 플랫폼 간 친숙하지만 `net5.0-windows`는 Windows 운영 체제에서 구현된 대로 .NET 5 API 화면을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-137">For example, `net5.0` targets the .NET 5 API surface and is cross-platform friendly, but `net5.0-windows` targets the .NET 5 API surface as implemented on the Windows operating system.</span></span>

## <a name="net-framework-compatibility-mode"></a><span data-ttu-id="97ced-138">.NET Framework 호환 모드</span><span class="sxs-lookup"><span data-stu-id="97ced-138">.NET Framework compatibility mode</span></span>

<span data-ttu-id="97ced-139">NuGet 패키지를 분석한 후 .NET Framework만 대상으로 하는 것이 확인되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-139">After analyzing the NuGet packages, you might find that they only target the .NET Framework.</span></span>

<span data-ttu-id="97ced-140">.NET Standard 2.0부터 .NET Framework 호환성 모드가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-140">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="97ced-141">이 호환 모드에서는 .NET Standard 및 .NET Core 프로젝트에서 .NET Framework 라이브러리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-141">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="97ced-142">.NET Framework 라이브러리 참조는 라이브러리가 WPF(Windows Presentation Foundation) API를 사용하는 것처럼 모든 프로젝트에 대해 작동하지 않지만 많은 이식 시나리오를 차단 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-142">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="97ced-143">프로젝트에서 .NET Framework를 대상으로 하는 NuGet 패키지(예:[`Huitian.PowerCollections`](https://www.nuget.org/packages/Huitian.PowerCollections))를 참조하는 경우 다음 예제와 유사한 패키지 대체 경고([NU1701](/nuget/reference/errors-and-warnings/nu1701))를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-143">When you reference NuGet packages that target .NET Framework in your project, such as [`Huitian.PowerCollections`](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="97ced-144">해당 경고는 패키지를 추가하고 해당 패키지를 프로젝트와 테스트하도록 빌드할 때마다 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-144">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="97ced-145">프로젝트가 예상대로 작동하는 경우 Visual Studio에서 패키지 속성을 편집하거나 즐겨 찾는 코드 편집기에서 프로젝트 파일을 수동으로 편집하여 해당 경고를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-145">If your project works as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="97ced-146">프로젝트 파일을 편집하여 경고를 제거하려면 경고를 제거하려는 패키지에 대한 `PackageReference` 항목을 찾고 `NoWarn` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-146">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="97ced-147">`NoWarn` 특성은 모든 경고 ID의 쉼표로 구분된 목록을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-147">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="97ced-148">다음 예제는 프로젝트 파일을 수동으로 편집하여 `Huitian.PowerCollections` 프로젝트에 대한 `NU1701` 경고를 제거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-148">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="97ced-149">Visual Studio에서 컴파일러 경고를 제거하는 방법에 대한 자세한 내용은 [NuGet 패키지에 대한 경고 표시 안 함](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97ced-149">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).</span></span>

## <a name="if-nuget-packages-wont-run-on-net"></a><span data-ttu-id="97ced-150">NuGet 패키지가 .NET에서 실행되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="97ced-150">If NuGet packages won't run on .NET</span></span>

<span data-ttu-id="97ced-151">종속된 NuGet 패키지가 .NET Core에서 실행되지 않을 경우 수행할 수 있는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-151">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

- <span data-ttu-id="97ced-152">프로젝트가 오픈 소스이고 GitHub 같은 곳에 호스트된 경우 개발자가 직접 참여하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-152">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
- <span data-ttu-id="97ced-153">[nuget.org](https://www.nuget.org/)에서 작성자에게 직접 문의할 수 있습니다. 패키지를 검색하고 패키지 페이지의 왼쪽에서 **연락처 소유자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-153">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
- <span data-ttu-id="97ced-154">사용하던 패키지와 동일한 작업을 수행하는 .NET Core에서 실행되는 다른 패키지를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-154">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
- <span data-ttu-id="97ced-155">패키지가 수행하고 있는 코드를 직접 작성해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-155">You can attempt to write the code the package was doing yourself.</span></span>
- <span data-ttu-id="97ced-156">적어도 패키지의 호환 버전을 사용할 수 있을 때까지는 앱의 기능을 변경하여 패키지에 대한 종속성을 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-156">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="97ced-157">오픈 소스 프로젝트 유지 관리자와 NuGet 패키지 게시자는 종종 지원자입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-157">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="97ced-158">지정된 도메인을 중요하게 여기기 때문에 참여하고, 자유롭게 수행하고, 종종 다른 주간 작업을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-158">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="97ced-159">.NET Core 지원에 대해 문의하는 경우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-159">Be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="97ced-160">이 방법으로 문제를 해결할 수 없는 경우 나중에 .NET Core로 이식해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-160">If you can't resolve your issue with any of these options, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="97ced-161">.NET 팀은 .NET Core를 지원하기 위해 어떤 라이브러리가 가장 중요한지 알고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-161">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="97ced-162">사용하고 싶은 라이브러리에 대해 dotnet@microsoft.com으로 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-162">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-non-nuget-dependencies"></a><span data-ttu-id="97ced-163">비 NuGet 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="97ced-163">Analyze non-NuGet dependencies</span></span>

<span data-ttu-id="97ced-164">파일 시스템의 DLL처럼, NuGet 패키지가 아닌 종속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-164">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="97ced-165">해당 종속성의 이식 가능성을 확인하는 유일한 방법은 [.NET 이식성 분석기](https://github.com/Microsoft/dotnet-apiport)를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-165">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="97ced-166">도구는 .NET Framework를 대상으로 하는 어셈블리를 분석하고 .NET Core와 같은 다른 .NET 플랫폼으로 이식할 수 없는 API를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-166">The tool analyzes assemblies that target the .NET Framework and identifies APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="97ced-167">콘솔 애플리케이션 또는 [Visual Studio 확장](../../standard/analyzers/portability-analyzer.md)으로 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ced-167">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="97ced-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="97ced-168">Next steps</span></span>

- [<span data-ttu-id="97ced-169">.NET Framework에서 .NET으로 포팅 개요</span><span class="sxs-lookup"><span data-stu-id="97ced-169">Overview of porting from .NET Framework to .NET</span></span>](index.md)
- [<span data-ttu-id="97ced-170">포트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="97ced-170">Port libraries</span></span>](libraries.md)
