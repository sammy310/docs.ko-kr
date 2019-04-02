---
title: WPF 앱을 .NET Core 3.0으로 포트
description: Windows용 .NET Core 3.0에 .NET Framework Windows Presentation Foundation 애플리케이션을 포팅하는 방법을 설명합니다.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 29ea308ee5147cfb18df312887e933615e349803
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2019
ms.locfileid: "58677557"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a><span data-ttu-id="11694-103">방법: WPF 데스크톱 앱을 .NET Core로 포트</span><span class="sxs-lookup"><span data-stu-id="11694-103">How to: Port a WPF desktop app to .NET Core</span></span>

<span data-ttu-id="11694-104">이 문서에서는 .NET Framework에서 .NET Core 3.0으로 WPF(Windows Presentation Foundation) 기반 데스크톱 앱을 포팅하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-104">This article describes how to port your Windows Presentation Foundation-based (WPF) desktop app from .NET Framework to .NET Core 3.0.</span></span> <span data-ttu-id="11694-105">.NET Core 3.0 SDK는 WPF 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-105">The .NET Core 3.0 SDK includes support for WPF applications.</span></span> <span data-ttu-id="11694-106">WPF는 Windows 전용 프레임워크이고 Windows에서만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-106">WPF is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="11694-107">이 예제에서는 .NET Core SDK CLI를 사용하여 프로젝트를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="11694-108">이 문서에서는 마이그레이션에 사용되는 파일의 유형을 식별하기 위해 다양한 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="11694-109">프로젝트를 마이그레이션할 때 파일 이름이 다르게 지정되므로 파일을 아래 나열된 파일과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="11694-110">파일</span><span class="sxs-lookup"><span data-stu-id="11694-110">File</span></span> | <span data-ttu-id="11694-111">설명</span><span class="sxs-lookup"><span data-stu-id="11694-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="11694-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="11694-112">**MyApps.sln**</span></span> | <span data-ttu-id="11694-113">솔루션 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-113">The name of the solution file.</span></span> |
| <span data-ttu-id="11694-114">**MyWPF.csproj**</span><span class="sxs-lookup"><span data-stu-id="11694-114">**MyWPF.csproj**</span></span> | <span data-ttu-id="11694-115">포팅할 .NET Framework WPF 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-115">The name of the .NET Framework WPF project to port.</span></span> |
| <span data-ttu-id="11694-116">**MyWPFCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="11694-116">**MyWPFCore.csproj**</span></span> | <span data-ttu-id="11694-117">만들 새 .NET Core 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="11694-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="11694-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="11694-119">.NET Core WPF 앱은 실행 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-119">The .NET Core WPF app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="11694-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="11694-120">Prerequisites</span></span>

- <span data-ttu-id="11694-121">수행할 디자이너 작업용 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core)</span><span class="sxs-lookup"><span data-stu-id="11694-121">[Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=wpf+core) for any designer work you want to do.</span></span>

  <span data-ttu-id="11694-122">다음 Visual Studio 워크로드를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="11694-123">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="11694-123">.NET desktop development</span></span>
  - <span data-ttu-id="11694-124">.NET 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="11694-124">.NET cross-platform development</span></span>

- <span data-ttu-id="11694-125">문제 없이 빌드하고 실행하는 솔루션에서 작동하는 WPF 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-125">A working WPF project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="11694-126">프로젝트는 C#으로 코딩되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-126">Your project must be coded in C#.</span></span> 
- <span data-ttu-id="11694-127">최신 [.NET Core 3.0](https://aka.ms/netcore3download) 미리 보기를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-127">Install the latest [.NET Core 3.0](https://aka.ms/netcore3download) preview.</span></span>


>[!NOTE]
><span data-ttu-id="11694-128">**Visual Studio 2017**은 .NET Core 3.0 프로젝트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="11694-129">**Visual Studio 2019 미리 보기/RC**는 .NET Core 3.0 프로젝트를 지원하지만 .NET Core 3.0 WPF 프로젝트의 시각적 디자이너는 아직 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-129">**Visual Studio 2019 Preview/RC** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 WPF projects.</span></span> <span data-ttu-id="11694-130">시각적 디자이너를 사용하려면 .NET Core 프로젝트와 해당 파일을 공유하는 .NET WPF 프로젝트가 솔루션에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-130">To use the visual designer, you must have a .NET WPF project in your solution that shares its files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="11694-131">Consider</span><span class="sxs-lookup"><span data-stu-id="11694-131">Consider</span></span>

<span data-ttu-id="11694-132">.NET Framework WPF 애플리케이션을 포팅할 때 고려해야 할 몇 가지 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-132">When porting a .NET Framework WPF application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="11694-133">애플리케이션이 마이그레이션에 적합한 후보인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="11694-134">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 사용하여 프로젝트가 .NET Core 3.0으로 마이그레이션되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="11694-135">프로젝트에 .NET Core 3.0 관련 문제가 있는 경우 분석기는 해당 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="11694-136">다른 버전의 WPF를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-136">You're using a different version of WPF.</span></span>

    <span data-ttu-id="11694-137">.NET Core 3.0 미리 보기 1이 릴리스될 때 WPF는 GitHub에서 오픈 소스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-137">When .NET Core 3.0 Preview 1 was released, WPF went open-source on GitHub.</span></span> <span data-ttu-id="11694-138">.NET Core WPF의 코드는 .NET Framework WPF 코드베이스의 포크입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-138">The code for .NET Core WPF is a fork of the .NET Framework WPF code base.</span></span> <span data-ttu-id="11694-139">몇 가지 차이가 있을 수 있고 앱은 포팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="11694-140">[Windows 호환성 팩][compat-pack]이 마이그레이션하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="11694-141">.NET Framework에서 사용할 수 있는 일부 API는 .NET Core 3.0에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="11694-142">[Windows 호환성 팩][compat-pack]은 이와 같은 다양한 API를 추가하며, WPF 앱이 .NET Core와 호환되도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="11694-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your WPF app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="11694-143">프로젝트에서 사용되는 NuGet 패키지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="11694-144">마이그레이션하기 전에 항상 NuGet 패키지의 최신 버전을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="11694-145">애플리케이션이 NuGet 패키지를 참조하는 경우 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="11694-146">애플리케이션이 성공적으로 빌드되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="11694-147">업그레이드한 후 패키지 오류가 있는 경우에는 코드를 중단하지 않는 최신 버전으로 패키지를 다운그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="11694-148">Visual Studio 2019 미리 보기/RC는 .NET Core 3.0용 WPF 디자이너를 아직 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-148">Visual Studio 2019 Preview/RC doesn't yet support the WPF Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="11694-149">현재 Visual Studio에서 WPF 디자이너를 사용하려면 기존 .NET Framework WPF 프로젝트 파일을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-149">Currently, you need to keep your existing .NET Framework WPF project file if you want to use the WPF Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="11694-150">새 SDK 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="11694-150">Create a new SDK project</span></span>

<span data-ttu-id="11694-151">만들려는 새 .NET Core 3.0 프로젝트는 .NET Framework 프로젝트와 다른 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="11694-152">둘 다 동일한 디렉터리에 있는 경우 **obj** 디렉터리에서 생성된 파일과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="11694-153">이 예제에서는 **SolutionFolder** 디렉터리에 **MyWPFAppCore**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11694-153">In this example, you'll create a directory named **MyWPFAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

<span data-ttu-id="11694-154">다음으로, **MyWPFAppCore** 디렉터리에 **MyWPFCore.csproj** 프로젝트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-154">Next, you need to create the **MyWPFCore.csproj** project in the **MyWPFAppCore** directory.</span></span> <span data-ttu-id="11694-155">선택한 텍스트 편집기를 사용하여 이 파일을 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="11694-156">다음 XML에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="11694-157">프로젝트 파일을 수동으로 만들지 않으려면 Visual Studio 또는 .NET Core SDK를 사용하여 프로젝트를 생성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="11694-158">그러나 프로젝트 파일을 제외하고 프로젝트 템플릿에서 생성된 다른 모든 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="11694-159">SDK를 사용하려면 **SolutionFolder** 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

<span data-ttu-id="11694-160">**MyWPFCore.csproj**를 만든 후에 디렉터리 구조체는 다음과 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-160">After you create the **MyWPFCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

<span data-ttu-id="11694-161">**SolutionFolder** 디렉터리에서 Visual Studio 또는 .NET Core CLI를 사용하여 **MyWPFCore.csproj** 프로젝트를 **MyApps.sln**에 추가하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-161">You'll want to add the **MyWPFCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="11694-162">어셈블리 정보 생성 수정</span><span class="sxs-lookup"><span data-stu-id="11694-162">Fix assembly info generation</span></span>

<span data-ttu-id="11694-163">.NET Framework로 만든 Windows Presentation Foundation 프로젝트에는 생성할 어셈블리 버전과 같은 어셈블리 특성을 포함하는 `AssemblyInfo.cs` 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-163">Windows Presentation Foundation projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="11694-164">SDK 스타일 프로젝트는 SDK 프로젝트 파일을 기반으로 이 정보를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="11694-165">두 유형의 “어셈블리 정보”가 모두 있으면 충돌이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="11694-166">자동 생성을 비활성화하여 이 문제를 해결합니다. 그러면 프로젝트가 기존 `AssemblyInfo.cs` 파일을 강제로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="11694-167">기본 `<PropertyGroup>` 노드에 추가할 세 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span> 

- <span data-ttu-id="11694-168">**GenerateAssemblyInfo**\\</span><span class="sxs-lookup"><span data-stu-id="11694-168">**GenerateAssemblyInfo**\\</span></span>
<span data-ttu-id="11694-169">이 속성을 `false`로 설정하면 어셈블리 특성이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="11694-170">따라서 .NET Framework 프로젝트의 기존 `AssemblyInfo.cs` 파일과 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="11694-171">**AssemblyName**\\</span><span class="sxs-lookup"><span data-stu-id="11694-171">**AssemblyName**\\</span></span>
<span data-ttu-id="11694-172">이 속성 값은 컴파일할 때 생성되는 출력 이진입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="11694-173">이름에 확장명을 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="11694-174">예를 들어 `MyCoreApp`을 사용하면 `MyCoreApp.exe`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="11694-175">**RootNamespace**\\</span><span class="sxs-lookup"><span data-stu-id="11694-175">**RootNamespace**\\</span></span>
<span data-ttu-id="11694-176">프로젝트에서 사용되는 기본 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="11694-176">The default namespace used by your project.</span></span> <span data-ttu-id="11694-177">이 네임스페이스는 .NET Framework 프로젝트의 기본 네임스페이스와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="11694-178">`MyWPFCore.csproj` 파일의 `<PropertyGroup>` 노드에 다음 세 개의 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-178">Add these three elements to the `<PropertyGroup>` node in the `MyWPFCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="11694-179">소스 코드 추가</span><span class="sxs-lookup"><span data-stu-id="11694-179">Add source code</span></span>
<span data-ttu-id="11694-180">현재는 **MyWPFCore.csproj** 프로젝트가 코드를 컴파일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-180">Right now, the **MyWPFCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="11694-181">기본적으로 .NET Core 프로젝트는 현재 디렉터리 및 자식 디렉터리에 있는 모든 소스 코드를 자동으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="11694-182">상대 경로를 사용하여 .NET Framework 프로젝트의 코드를 포함하도록 프로젝트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="11694-183">.NET Framework 프로젝트가 창 및 제어의 아이콘과 리소스에 **.resx** 파일을 사용한 경우 해당 파일도 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-183">If your .NET Framework project used **.resx** files for icons and resources for your windows and controls, you'll need to include those too.</span></span> 

<span data-ttu-id="11694-184">프로젝트에 추가해야 하는 첫 번째 `<ItemGroup>` 노드에는 앱이 사용하는 시작 구성 및 리소스를 나타내는 **App.xaml** 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-184">The first `<ItemGroup>` node you need to add to your project includes the **App.xaml** file that represents the startup config and resources your app uses.</span></span> <span data-ttu-id="11694-185">**App.xaml** 파일은 해당하는 **App.xaml.cs** 파일도 포함하지만 다른 `<ItemGroup>`에도 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-185">The **App.xaml** file also has an accompanying **App.xaml.cs** file, but it will be automatically included in a different `<ItemGroup>`.</span></span>

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

<span data-ttu-id="11694-186">다음으로, 다음과 같은 `<ItemGroup>` 노드를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-186">Next, add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="11694-187">각 문에는 자식 디렉터리를 포함하는 파일 GLOB 패턴이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-187">Each statement includes a file glob pattern that includes child directories.</span></span> <span data-ttu-id="11694-188">프로젝트, 설정 파일 및 리소스에 대한 소스 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-188">It includes the source code for your project, any settings files, and any resources.</span></span> <span data-ttu-id="11694-189">**obj** 디렉터리는 명시적으로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-189">The **obj** directory is explicitly excluded.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="11694-190">다음으로, **App.xaml**을 제외한 프로젝트의 **xaml** 파일마다 `<Page>` 항목을 포함하는 다른 `<ItemGroup>` 노드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-190">Next, include another `<ItemGroup>` node that contains a `<Page>` entry for every **xaml** file in your project except the **App.xaml** file.</span></span> <span data-ttu-id="11694-191">**xaml** 형식인 창, 페이지 및 리소스를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-191">These contain all of the windows, pages, and resources that are in **xaml** format.</span></span> <span data-ttu-id="11694-192">여기에서 glob 패턴을 사용할 수 없고, 파일마다 항목을 추가하고 사용된 `<Generator>`를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-192">You cannot use a glob pattern here and must add an entry for every file and indicate the `<Generator>` used.</span></span>

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a><span data-ttu-id="11694-193">NuGet 패키지 추가</span><span class="sxs-lookup"><span data-stu-id="11694-193">Add NuGet packages</span></span>

<span data-ttu-id="11694-194">.NET Framework 프로젝트에서 참조하는 각 NuGet 패키지를 .NET Core 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-194">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span> 

<span data-ttu-id="11694-195">대부분의 경우 .NET Framework WPF 앱에는 프로젝트에서 참조하는 모든 NuGet 패키지의 목록을 포함하는 **packages.config** 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-195">Most likely your .NET Framework WPF app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="11694-196">이 목록을 보고 .NET Core 프로젝트에 추가할 NuGet 패키지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-196">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="11694-197">예를 들어, .NET Framework 프로젝트가 `MahApps.Metro` NuGet 패키지를 참조하는 경우 Visual Studio를 사용하여 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-197">For example, if the .NET Framework project references the `MahApps.Metro` NuGet package, add it to the project with Visual Studio.</span></span> <span data-ttu-id="11694-198">**SolutionFolder** 디렉터리에서 .NET Core CLI를 사용하여 패키지 참조를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-198">You can also add the package reference with the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

<span data-ttu-id="11694-199">이전 명령은 **MyWPFCore.csproj** 프로젝트에 다음 NuGet 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-199">The previous command would add the following NuGet reference to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a><span data-ttu-id="11694-200">컴파일 문제</span><span class="sxs-lookup"><span data-stu-id="11694-200">Problems compiling</span></span>

<span data-ttu-id="11694-201">프로젝트를 컴파일하는 데 문제가 있는 경우 .NET Framework에서 사용할 수 있지만 .NET Core에서는 사용할 수 없는 일부 Windows 전용 API를 사용하고 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-201">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="11694-202">[Windows 호환성 팩][compat-pack] NuGet 패키지를 프로젝트에 추가해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-202">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="11694-203">이 패키지는 Windows에서만 실행되고 .NET Core 및 .NET Standard 프로젝트에 20,000개 정도의 Windows API를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-203">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="11694-204">이전 명령은 **MyWPFCore.csproj** 프로젝트에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-204">The previous command adds the following to the **MyWPFCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a><span data-ttu-id="11694-205">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="11694-205">WPF Designer</span></span>

<span data-ttu-id="11694-206">이 문서에 설명된 대로, Visual Studio 2019 미리 보기/RC는 .NET Framework 프로젝트의 WPF 디자이너만을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-206">As detailed in this article, Visual Studio 2019 Preview/RC only supports the WPF Designer in .NET Framework projects.</span></span> <span data-ttu-id="11694-207">동시에 .NET Core 프로젝트를 만들면 .NET Framework 프로젝트를 사용하여 양식을 디자인하는 동안 .NET Core를 사용하여 프로젝트를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-207">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="11694-208">솔루션 파일에는 .NET Framework 및 .NET Core 프로젝트가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-208">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="11694-209">.NET Framework 프로젝트에서 양식과 컨트롤을 추가 및 디자인합니다. 그러면 .NET Core 프로젝트에 추가한 파일 GLOB 패턴을 기반으로 새 파일이나 변경된 파일이 자동으로 .NET Core 프로젝트에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-209">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="11694-210">Visual Studio 2019가 WPF 디자이너를 지원하면 .NET Core 프로젝트 파일의 콘텐츠를 .NET Framework 프로젝트 파일로 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11694-210">Once Visual Studio 2019 supports the WPF Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="11694-211">그런 다음, `<Source>` 및 `<EmbeddedResource>` 항목과 함께 추가된 파일 GLOB 패턴을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-211">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="11694-212">앱에서 사용하는 프로젝트 참조의 경로를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="11694-212">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="11694-213">이렇게 하면 .NET Framework 프로젝트가 .NET Core 프로젝트로 효과적으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="11694-213">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="11694-214">다음 단계</span><span class="sxs-lookup"><span data-stu-id="11694-214">Next steps</span></span>

* <span data-ttu-id="11694-215">[Windows 호환성 팩][compat-pack]에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="11694-215">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
* <span data-ttu-id="11694-216">.NET Framework WPF 프로젝트를 .NET Core에 [포팅하는 방법에 대한 비디오](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt)을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="11694-216">Watch a [video on porting](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) your .NET Framework WPF project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
