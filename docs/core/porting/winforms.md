---
title: .NET Core에 Windows Forms 앱 포팅
description: Windows용 .NET Core에 .NET Framework Windows Forms 애플리케이션을 포팅하는 방법을 설명합니다.
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.openlocfilehash: dbd522851faa0a4fe435199914a034ee230d3455
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116028"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a><span data-ttu-id="2997d-103">.NET Core에 Windows Forms 데스크톱 앱을 포팅하는 방법</span><span class="sxs-lookup"><span data-stu-id="2997d-103">How to port a Windows Forms desktop app to .NET Core</span></span>

<span data-ttu-id="2997d-104">이 문서에서는 .NET Framework에서 .NET Core 3.0 이상으로 Windows Forms 기반 데스크톱 앱을 포팅하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-104">This article describes how to port your Windows Forms-based desktop app from .NET Framework to .NET Core 3.0 or later.</span></span> <span data-ttu-id="2997d-105">.NET Core 3.0 SDK는 Windows Forms 애플리케이션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-105">The .NET Core 3.0 SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="2997d-106">Windows Forms는 Windows 전용 프레임워크이고 Windows에서만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span> <span data-ttu-id="2997d-107">이 예제에서는 .NET Core SDK CLI를 사용하여 프로젝트를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-107">This example uses the .NET Core SDK CLI to create and manage your project.</span></span>

<span data-ttu-id="2997d-108">이 문서에서는 마이그레이션에 사용되는 파일의 유형을 식별하기 위해 다양한 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-108">In this article, various names are used to identify types of files used for migration.</span></span> <span data-ttu-id="2997d-109">프로젝트를 마이그레이션할 때 파일 이름이 다르게 지정되므로 파일을 아래 나열된 파일과 대조합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-109">When migrating your project, your files will be named differently, so mentally match them to the ones listed below:</span></span>

| <span data-ttu-id="2997d-110">파일</span><span class="sxs-lookup"><span data-stu-id="2997d-110">File</span></span> | <span data-ttu-id="2997d-111">설명</span><span class="sxs-lookup"><span data-stu-id="2997d-111">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="2997d-112">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="2997d-112">**MyApps.sln**</span></span> | <span data-ttu-id="2997d-113">솔루션 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-113">The name of the solution file.</span></span> |
| <span data-ttu-id="2997d-114">**MyForms.csproj**</span><span class="sxs-lookup"><span data-stu-id="2997d-114">**MyForms.csproj**</span></span> | <span data-ttu-id="2997d-115">포팅할 .NET Framework Windows Forms 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-115">The name of the .NET Framework Windows Forms project to port.</span></span> |
| <span data-ttu-id="2997d-116">**MyFormsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="2997d-116">**MyFormsCore.csproj**</span></span> | <span data-ttu-id="2997d-117">만들 새 .NET Core 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-117">The name of the new .NET Core project you create.</span></span> |
| <span data-ttu-id="2997d-118">**MyAppCore.exe**</span><span class="sxs-lookup"><span data-stu-id="2997d-118">**MyAppCore.exe**</span></span> | <span data-ttu-id="2997d-119">.NET Core Windows Forms 앱 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-119">The .NET Core Windows Forms app executable.</span></span> |

## <a name="prerequisites"></a><span data-ttu-id="2997d-120">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2997d-120">Prerequisites</span></span>

- <span data-ttu-id="2997d-121">수행할 디자이너 작업용 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="2997d-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for any designer work you want to do.</span></span>

  <span data-ttu-id="2997d-122">다음 Visual Studio 워크로드를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-122">Install the following Visual Studio workloads:</span></span>
  - <span data-ttu-id="2997d-123">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="2997d-123">.NET desktop development</span></span>
  - <span data-ttu-id="2997d-124">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="2997d-124">.NET Core cross-platform development</span></span>

- <span data-ttu-id="2997d-125">문제없이 빌드 및 실행되는 솔루션의 작업 Windows Forms 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="2997d-125">A working Windows Forms project in a solution that builds and runs without issue.</span></span>
- <span data-ttu-id="2997d-126">C#로 코딩된 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-126">A project coded in C#.</span></span>
- <span data-ttu-id="2997d-127">[.NET Core](https://dotnet.microsoft.com/download/dotnet-core) 3.0 이상.</span><span class="sxs-lookup"><span data-stu-id="2997d-127">[.NET Core](https://dotnet.microsoft.com/download/dotnet-core) 3.0 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="2997d-128">**Visual Studio 2017**은 .NET Core 3.0 프로젝트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-128">**Visual Studio 2017** doesn't support .NET Core 3.0 projects.</span></span> <span data-ttu-id="2997d-129">**Visual Studio 2019**는 .NET Core 3.0 프로젝트를 지원하지만, .NET Core 3.0 Windows Forms 프로젝트의 비주얼 디자이너는 아직 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-129">**Visual Studio 2019** supports .NET Core 3.0 projects but doesn't yet support the visual designer for .NET Core 3.0 Windows Forms projects.</span></span> <span data-ttu-id="2997d-130">비주얼 디자이너를 사용하려면 .NET Core 프로젝트와 양식 파일을 공유하는 .NET Windows Forms 프로젝트가 솔루션에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-130">To use the visual designer, you must have a .NET Windows Forms project in a solution that shares the forms files with the .NET Core project.</span></span>

### <a name="consider"></a><span data-ttu-id="2997d-131">Consider</span><span class="sxs-lookup"><span data-stu-id="2997d-131">Consider</span></span>

<span data-ttu-id="2997d-132">.NET Framework Windows Forms 애플리케이션을 포팅할 때 몇 가지 항목을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-132">When porting a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="2997d-133">애플리케이션이 마이그레이션에 적합한 후보인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-133">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="2997d-134">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 사용하여 프로젝트가 .NET Core 3.0으로 마이그레이션되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-134">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to determine if your project will migrate to .NET Core 3.0.</span></span> <span data-ttu-id="2997d-135">프로젝트에 .NET Core 3.0 관련 문제가 있는 경우 분석기는 해당 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-135">If your project has issues with .NET Core 3.0, the analyzer helps you identify those problems.</span></span>

01. <span data-ttu-id="2997d-136">다른 버전의 Windows Forms를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-136">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="2997d-137">.NET Core 3.0 미리 보기 1이 릴리스될 때 Windows Forms가 GitHub에서 오픈 소스로 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-137">When .NET Core 3.0 Preview 1 was released, Windows Forms went open source on GitHub.</span></span> <span data-ttu-id="2997d-138">.NET Core Windows Forms의 코드는 .NET Framework Windows Forms 코드베이스의 포크입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-138">The code for .NET Core Windows Forms is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="2997d-139">몇 가지 차이가 있을 수 있고 앱은 포팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-139">It's possible some differences exist and your app won't port.</span></span>

01. <span data-ttu-id="2997d-140">[Windows 호환성 팩][compat-pack]이 마이그레이션하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-140">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="2997d-141">.NET Framework에서 사용할 수 있는 일부 API는 .NET Core 3.0에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-141">Some APIs that are available in .NET Framework aren't available in .NET Core 3.0.</span></span> <span data-ttu-id="2997d-142">[Windows 호환성 팩][compat-pack]은 이와 같은 다양한 API를 추가하며, Windows Forms 앱이 .NET Core와 호환되도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-142">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET Core.</span></span>

01. <span data-ttu-id="2997d-143">프로젝트에서 사용되는 NuGet 패키지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-143">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="2997d-144">마이그레이션하기 전에 항상 NuGet 패키지의 최신 버전을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-144">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="2997d-145">애플리케이션이 NuGet 패키지를 참조하는 경우 최신 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-145">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="2997d-146">애플리케이션이 성공적으로 빌드되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-146">Ensure your application builds successfully.</span></span> <span data-ttu-id="2997d-147">업그레이드한 후 패키지 오류가 있는 경우에는 코드를 중단하지 않는 최신 버전으로 패키지를 다운그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-147">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

01. <span data-ttu-id="2997d-148">Visual Studio 2019는 .NET Core 3.0용 Forms 디자이너를 아직 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-148">Visual Studio 2019 doesn't yet support the Forms Designer for .NET Core 3.0</span></span>

    <span data-ttu-id="2997d-149">현재 Visual Studio에서 Forms 디자이너를 사용하려면 기존 .NET Framework Windows Forms 프로젝트 파일을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-149">Currently, you need to keep your existing .NET Framework Windows Forms project file if you want to use the Forms Designer from Visual Studio.</span></span>

## <a name="create-a-new-sdk-project"></a><span data-ttu-id="2997d-150">새 SDK 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2997d-150">Create a new SDK project</span></span>

<span data-ttu-id="2997d-151">만들려는 새 .NET Core 3.0 프로젝트는 .NET Framework 프로젝트와 다른 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-151">The new .NET Core 3.0 project you create must be in a different directory from your .NET Framework project.</span></span> <span data-ttu-id="2997d-152">둘 다 동일한 디렉터리에 있는 경우 **obj** 디렉터리에서 생성된 파일과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-152">If they're both in the same directory, you may run into conflicts with the files that are generated in the **obj** directory.</span></span> <span data-ttu-id="2997d-153">이 예제에서는 **SolutionFolder** 디렉터리에 **MyFormsAppCore**라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-153">In this example, we'll create a directory named **MyFormsAppCore** in the **SolutionFolder** directory:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

<span data-ttu-id="2997d-154">그런 다음, **MyFormsAppCore** 디렉터리에 **MyFormsCore.csproj** 프로젝트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-154">Next, you need to create the **MyFormsCore.csproj** project in the **MyFormsAppCore** directory.</span></span> <span data-ttu-id="2997d-155">선택한 텍스트 편집기를 사용하여 이 파일을 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-155">You can create this file manually by using the text editor of choice.</span></span> <span data-ttu-id="2997d-156">다음 XML에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-156">Paste in the following XML:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2997d-157">프로젝트 파일을 수동으로 만들지 않으려면 Visual Studio 또는 .NET Core SDK를 사용하여 프로젝트를 생성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-157">If you don't want to create the project file manually, you can use Visual Studio or the .NET Core SDK to generate the project.</span></span> <span data-ttu-id="2997d-158">그러나 프로젝트 파일을 제외하고 프로젝트 템플릿에서 생성된 다른 모든 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-158">However, you must delete all other files generated by the project template except for the project file.</span></span> <span data-ttu-id="2997d-159">SDK를 사용하려면 **SolutionFolder** 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-159">To use the SDK, run the following command from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

<span data-ttu-id="2997d-160">**MyFormsCore.csproj**를 만든 후 디렉터리 구조는 다음과 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-160">After you create the **MyFormsCore.csproj**, your directory structure should look like the following:</span></span>

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

<span data-ttu-id="2997d-161">**SolutionFolder** 디렉터리에서 Visual Studio 또는 .NET Core CLI를 사용하여 **MyFormsCore.csproj** 프로젝트를 **MyApps.sln**에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-161">Add the **MyFormsCore.csproj** project to **MyApps.sln** with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a><span data-ttu-id="2997d-162">어셈블리 정보 생성 수정</span><span class="sxs-lookup"><span data-stu-id="2997d-162">Fix assembly info generation</span></span>

<span data-ttu-id="2997d-163">.NET Framework로 만든 Windows Forms 프로젝트에는 생성할 어셈블리 버전과 같은 어셈블리 특성을 포함하는 `AssemblyInfo.cs` 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-163">Windows Forms projects that were created with .NET Framework include an `AssemblyInfo.cs` file, which contains assembly attributes such as the version of the assembly to be generated.</span></span> <span data-ttu-id="2997d-164">SDK 스타일 프로젝트는 SDK 프로젝트 파일을 기반으로 이 정보를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-164">SDK-style projects automatically generate this information for you based on the SDK project file.</span></span> <span data-ttu-id="2997d-165">두 유형의 “어셈블리 정보”가 모두 있으면 충돌이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-165">Having both types of "assembly info" creates a conflict.</span></span> <span data-ttu-id="2997d-166">자동 생성을 비활성화하여 이 문제를 해결합니다. 그러면 프로젝트가 기존 `AssemblyInfo.cs` 파일을 강제로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-166">Resolve this problem by disabling automatic generation, which forces the project to use your existing `AssemblyInfo.cs` file.</span></span>

<span data-ttu-id="2997d-167">기본 `<PropertyGroup>` 노드에 추가할 세 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-167">There are three settings to add to the main `<PropertyGroup>` node.</span></span>

- <span data-ttu-id="2997d-168">**GenerateAssemblyInfo**</span><span class="sxs-lookup"><span data-stu-id="2997d-168">**GenerateAssemblyInfo**</span></span>\
<span data-ttu-id="2997d-169">이 속성을 `false`로 설정하면 어셈블리 특성이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-169">When you set this property to `false`, it won't generate the assembly attributes.</span></span> <span data-ttu-id="2997d-170">따라서 .NET Framework 프로젝트의 기존 `AssemblyInfo.cs` 파일과 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-170">This avoids the conflict with the existing `AssemblyInfo.cs` file from the .NET Framework project.</span></span>

- <span data-ttu-id="2997d-171">**AssemblyName**</span><span class="sxs-lookup"><span data-stu-id="2997d-171">**AssemblyName**</span></span>\
<span data-ttu-id="2997d-172">이 속성 값은 컴파일할 때 생성되는 출력 이진입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-172">The value of this property is the output binary created when you compile.</span></span> <span data-ttu-id="2997d-173">이름에 확장명을 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-173">The name doesn't need an extension added to it.</span></span> <span data-ttu-id="2997d-174">예를 들어 `MyCoreApp`을 사용하면 `MyCoreApp.exe`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-174">For example, using `MyCoreApp` produces `MyCoreApp.exe`.</span></span>

- <span data-ttu-id="2997d-175">**RootNamespace**</span><span class="sxs-lookup"><span data-stu-id="2997d-175">**RootNamespace**</span></span>\
<span data-ttu-id="2997d-176">프로젝트에서 사용되는 기본 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-176">The default namespace used by your project.</span></span> <span data-ttu-id="2997d-177">이 네임스페이스는 .NET Framework 프로젝트의 기본 네임스페이스와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-177">This should match the default namespace of the .NET Framework project.</span></span>

<span data-ttu-id="2997d-178">`MyFormsCore.csproj` 파일의 `<PropertyGroup>` 노드에 다음 세 개의 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-178">Add these three elements to the `<PropertyGroup>` node in the `MyFormsCore.csproj` file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a><span data-ttu-id="2997d-179">소스 코드 추가</span><span class="sxs-lookup"><span data-stu-id="2997d-179">Add source code</span></span>

<span data-ttu-id="2997d-180">현재는 **MyFormsCore.csproj** 프로젝트가 코드를 컴파일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-180">Right now, the **MyFormsCore.csproj** project doesn't compile any code.</span></span> <span data-ttu-id="2997d-181">기본적으로 .NET Core 프로젝트는 현재 디렉터리 및 자식 디렉터리에 있는 모든 소스 코드를 자동으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-181">By default, .NET Core projects automatically include all source code in the current directory and any child directories.</span></span> <span data-ttu-id="2997d-182">상대 경로를 사용하여 .NET Framework 프로젝트의 코드를 포함하도록 프로젝트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-182">You must configure the project to include code from the .NET Framework project using a relative path.</span></span> <span data-ttu-id="2997d-183">.NET Framework 프로젝트가 양식의 아이콘과 리소스에 **.resx** 파일을 사용한 경우 해당 파일도 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-183">If your .NET Framework project used **.resx** files for icons and resources for your forms, you'll need to include those too.</span></span>

<span data-ttu-id="2997d-184">다음 `<ItemGroup>` 노드를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-184">Add the following `<ItemGroup>` node to your project.</span></span> <span data-ttu-id="2997d-185">각 문에는 자식 디렉터리를 포함하는 파일 GLOB 패턴이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-185">Each statement includes a file glob pattern that includes child directories.</span></span>

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

<span data-ttu-id="2997d-186">또는 .NET Framework 프로젝트의 각 파일에 대해 `<Compile>` 또는 `<EmbeddedResource>` 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-186">Alternatively, you can create a `<Compile>` or `<EmbeddedResource>` entry for each file in your .NET Framework project.</span></span>

## <a name="add-nuget-packages"></a><span data-ttu-id="2997d-187">NuGet 패키지 추가</span><span class="sxs-lookup"><span data-stu-id="2997d-187">Add NuGet packages</span></span>

<span data-ttu-id="2997d-188">.NET Framework 프로젝트에서 참조하는 각 NuGet 패키지를 .NET Core 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-188">Add each NuGet package referenced by the .NET Framework project to the .NET Core project.</span></span>

<span data-ttu-id="2997d-189">대부분의 경우 .NET Framework Windows Forms 앱에는 프로젝트에서 참조하는 모든 NuGet 패키지의 목록을 포함하는 **packages.config** 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-189">Most likely your .NET Framework Windows Forms app has a **packages.config** file that contains a list of all of the NuGet packages that are referenced by your project.</span></span> <span data-ttu-id="2997d-190">이 목록을 보고 .NET Core 프로젝트에 추가할 NuGet 패키지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-190">You can look at this list to determine which NuGet packages to add to the .NET Core project.</span></span> <span data-ttu-id="2997d-191">예를 들어 .NET Framework 프로젝트가 `MetroFramework`, `MetroFramework.Design` 및 `MetroFramework.Fonts` NuGet 패키지를 참조한 경우 Visual Studio를 사용하거나 **SolutionFolder** 디렉터리에서 .NET Core CLI를 사용하여 프로젝트에 각 NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-191">For example, if the .NET Framework project referenced the `MetroFramework`, `MetroFramework.Design`, and `MetroFramework.Fonts` NuGet packages, add each to the project with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

<span data-ttu-id="2997d-192">이전 명령은 **MyFormsCore.csproj** 프로젝트에 다음 NuGet 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-192">The previous commands would add the following NuGet references to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a><span data-ttu-id="2997d-193">컨트롤 라이브러리 포팅</span><span class="sxs-lookup"><span data-stu-id="2997d-193">Port control libraries</span></span>

<span data-ttu-id="2997d-194">포팅할 Windows Forms 컨트롤 라이브러리 프로젝트가 있는 경우 일부 설정을 제외하고 지침은 .NET Framework Windows Forms 앱 프로젝트를 포팅하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-194">If you have a Windows Forms Controls library project to port, the directions are the same as porting a .NET Framework Windows Forms app project, except for a few settings.</span></span> <span data-ttu-id="2997d-195">또한 실행 파일로 컴파일하는 대신 라이브러리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-195">And instead of compiling to an executable, you compile to a library.</span></span> <span data-ttu-id="2997d-196">소스 코드를 포함하는 파일 GLOB 경로 외에 실행 가능 프로젝트와 라이브러리 프로젝트 간 차이는 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-196">The difference between the executable project and the library project, besides paths for the file globs that include your source code, is minimal.</span></span>

<span data-ttu-id="2997d-197">이전 단계의 예제를 사용하여 작업 중인 프로젝트 및 파일을 확장해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-197">Using the previous step's example, lets expand what projects and files we're working with.</span></span>

| <span data-ttu-id="2997d-198">파일</span><span class="sxs-lookup"><span data-stu-id="2997d-198">File</span></span> | <span data-ttu-id="2997d-199">설명</span><span class="sxs-lookup"><span data-stu-id="2997d-199">Description</span></span> |
| ---- | ----------- |
| <span data-ttu-id="2997d-200">**MyApps.sln**</span><span class="sxs-lookup"><span data-stu-id="2997d-200">**MyApps.sln**</span></span> | <span data-ttu-id="2997d-201">솔루션 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-201">The name of the solution file.</span></span> |
| <span data-ttu-id="2997d-202">**MyControls.csproj**</span><span class="sxs-lookup"><span data-stu-id="2997d-202">**MyControls.csproj**</span></span> | <span data-ttu-id="2997d-203">포팅할 .NET Framework Windows Forms 컨트롤 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-203">The name of the .NET Framework Windows Forms Controls project to port.</span></span> |
| <span data-ttu-id="2997d-204">**MyControlsCore.csproj**</span><span class="sxs-lookup"><span data-stu-id="2997d-204">**MyControlsCore.csproj**</span></span> | <span data-ttu-id="2997d-205">만들려는 새 .NET Core 라이브러리 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-205">The name of the new .NET Core library project you create.</span></span> |
| <span data-ttu-id="2997d-206">**MyCoreControls.dll**</span><span class="sxs-lookup"><span data-stu-id="2997d-206">**MyCoreControls.dll**</span></span> | <span data-ttu-id="2997d-207">.NET Core Windows Forms 컨트롤 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-207">The .NET Core Windows Forms Controls library.</span></span> |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

<span data-ttu-id="2997d-208">`MyControlsCore.csproj` 프로젝트와 이전에 만든 `MyFormsCore.csproj` 프로젝트 간 차이를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-208">Consider the differences between the `MyControlsCore.csproj` project and the previously created `MyFormsCore.csproj` project.</span></span>

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

<span data-ttu-id="2997d-209">.NET Core Windows Forms 컨트롤 라이브러리 프로젝트 파일이 표시되는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-209">Here is an example of what the .NET Core Windows Forms Controls library project file would look like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>

    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="2997d-210">확인한 것처럼 `<OutputType>` 노드가 제거되어 기본적으로 컴파일러가 실행 파일 대신 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-210">As you can see, the `<OutputType>` node was removed, which defaults the compiler to produce a library instead of an executable.</span></span> <span data-ttu-id="2997d-211">`<AssemblyName>` 및 `<RootNamespace>`가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-211">The `<AssemblyName>` and `<RootNamespace>` were changed.</span></span> <span data-ttu-id="2997d-212">특히 `<RootNamespace>`는 포팅할 Windows Forms 컨트롤 라이브러리의 네임스페이스와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-212">Specifically the `<RootNamespace>` should match the namespace of the Windows Forms Controls library you are porting.</span></span> <span data-ttu-id="2997d-213">마지막으로 `<Compile>` 및 `<EmbeddedResource>` 노드는 포팅할 Windows Forms 컨트롤 라이브러리의 폴더를 가리키도록 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-213">And finally, the `<Compile>` and `<EmbeddedResource>` nodes were adjusted to point to the folder of the Windows Forms Controls library you are porting.</span></span>

<span data-ttu-id="2997d-214">다음으로, 기본 .NET Core **MyFormsCore.csproj** 프로젝트에서 새 .NET Core Windows Forms 컨트롤 라이브러리에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-214">Next, in the main .NET Core **MyFormsCore.csproj** project, add a reference to the new .NET Core Windows Forms Control library.</span></span> <span data-ttu-id="2997d-215">Visual Studio를 사용하거나 **SolutionFolder** 디렉터리에서 .NET Core CLI를 사용하여 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-215">Add a reference with either Visual Studio or the .NET Core CLI from the **SolutionFolder** directory:</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

<span data-ttu-id="2997d-216">이전 명령은 **MyFormsCore.csproj** 프로젝트에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-216">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="compilation-problems"></a><span data-ttu-id="2997d-217">컴파일 문제</span><span class="sxs-lookup"><span data-stu-id="2997d-217">Compilation problems</span></span>

<span data-ttu-id="2997d-218">프로젝트를 컴파일하는 데 문제가 있는 경우 .NET Framework에서 사용할 수 있지만 .NET Core에서는 사용할 수 없는 일부 Windows 전용 API를 사용하고 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-218">If you have problems compiling your projects, you may be using some Windows-only APIs that are available in .NET Framework but not available in .NET Core.</span></span> <span data-ttu-id="2997d-219">[Windows 호환성 팩][compat-pack] NuGet 패키지를 프로젝트에 추가해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-219">You can try adding the [Windows Compatibility Pack][compat-pack] NuGet package to your project.</span></span> <span data-ttu-id="2997d-220">이 패키지는 Windows에서만 실행되고 .NET Core 및 .NET Standard 프로젝트에 20,000개 정도의 Windows API를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-220">This package only runs on Windows and adds about 20,000 Windows APIs to .NET Core and .NET Standard projects.</span></span>

```dotnetcli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

<span data-ttu-id="2997d-221">이전 명령은 **MyFormsCore.csproj** 프로젝트에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-221">The previous command adds the following to the **MyFormsCore.csproj** project:</span></span>

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="3.1.0" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a><span data-ttu-id="2997d-222">Windows Forms 디자이너</span><span class="sxs-lookup"><span data-stu-id="2997d-222">Windows Forms Designer</span></span>

<span data-ttu-id="2997d-223">이 문서에 설명된 대로, Visual Studio 2019만 .NET Framework 프로젝트의 Forms 디자이너를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-223">As detailed in this article, Visual Studio 2019 only supports the Forms Designer in .NET Framework projects.</span></span> <span data-ttu-id="2997d-224">동시에 .NET Core 프로젝트를 만들면 .NET Framework 프로젝트를 사용하여 양식을 디자인하는 동안 .NET Core를 사용하여 프로젝트를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-224">By creating a side-by-side .NET Core project, you can test your project with .NET Core while you use the .NET Framework project to design forms.</span></span> <span data-ttu-id="2997d-225">솔루션 파일에는 .NET Framework 및 .NET Core 프로젝트가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-225">Your solution file includes both the .NET Framework and .NET Core projects.</span></span> <span data-ttu-id="2997d-226">.NET Framework 프로젝트에서 양식과 컨트롤을 추가 및 디자인합니다. 그러면 .NET Core 프로젝트에 추가한 파일 GLOB 패턴을 기반으로 새 파일이나 변경된 파일이 자동으로 .NET Core 프로젝트에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-226">Add and design your forms and controls in the .NET Framework project, and based on the file glob patterns we added to the .NET Core projects, any new or changed files will automatically be included in the .NET Core projects.</span></span>

<span data-ttu-id="2997d-227">Visual Studio 2019가 Windows Forms 디자이너를 지원하면 .NET Core 프로젝트 파일의 콘텐츠를 .NET Framework 프로젝트 파일로 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-227">Once Visual Studio 2019 supports the Windows Forms Designer, you can copy/paste the content of your .NET Core project file into the .NET Framework project file.</span></span> <span data-ttu-id="2997d-228">그런 다음, `<Source>` 및 `<EmbeddedResource>` 항목과 함께 추가된 파일 GLOB 패턴을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-228">Then delete the file glob patterns added with the `<Source>` and `<EmbeddedResource>` items.</span></span> <span data-ttu-id="2997d-229">앱에서 사용하는 프로젝트 참조의 경로를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-229">Fix the paths to any project reference used by your app.</span></span> <span data-ttu-id="2997d-230">이렇게 하면 .NET Framework 프로젝트가 .NET Core 프로젝트로 효과적으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-230">This effectively upgrades the .NET Framework project to a .NET Core project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2997d-231">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2997d-231">Next steps</span></span>

- <span data-ttu-id="2997d-232">[.NET Framework에서 .NET Core로의 주요 변경 사항](../compatibility/fx-core.md)을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2997d-232">Learn about [breaking changes from .NET Framework to .NET Core](../compatibility/fx-core.md).</span></span>
- <span data-ttu-id="2997d-233">[Windows 호환성 팩][compat-pack]에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-233">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>
- <span data-ttu-id="2997d-234">.NET Framework Windows Forms 프로젝트를 .NET Core에 [포팅하는 방법에 관한 동영상](https://www.youtube.com/watch?v=upVQEUc_KwU)을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2997d-234">Watch a [video on porting](https://www.youtube.com/watch?v=upVQEUc_KwU) your .NET Framework Windows Forms project to .NET Core.</span></span>

[compat-pack]: windows-compat-pack.md
