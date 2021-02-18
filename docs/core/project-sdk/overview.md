---
title: .NET 프로젝트 SDK 개요
titleSuffix: ''
description: .NET 프로젝트 SDK에 대해 알아봅니다.
ms.date: 09/17/2020
ms.topic: conceptual
no-loc:
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: e5a6d0a1c988818e507936b567fa0188675cedc3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432649"
---
# <a name="net-project-sdks"></a><span data-ttu-id="a4b11-103">.NET 프로젝트 SDK</span><span class="sxs-lookup"><span data-stu-id="a4b11-103">.NET project SDKs</span></span>

<span data-ttu-id="a4b11-104">.NET Core 및 .NET 5.0 이상 프로젝트는 SDK(소프트웨어 개발 키트)와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-104">.NET Core and .NET 5.0 and later projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="a4b11-105">각 ‘프로젝트 SDK’는 코드를 컴파일, 압축 및 게시해야 하는 MSBuild [대상](/visualstudio/msbuild/msbuild-targets) 및 관련 [작업](/visualstudio/msbuild/msbuild-tasks) 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="a4b11-106">프로젝트 SDK를 참조하는 프로젝트를 ‘SDK 스타일 프로젝트’라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="a4b11-107">사용 가능한 SDK</span><span class="sxs-lookup"><span data-stu-id="a4b11-107">Available SDKs</span></span>

<span data-ttu-id="a4b11-108">다음 SDK를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-108">The following SDKs are available:</span></span>

| <span data-ttu-id="a4b11-109">ID</span><span class="sxs-lookup"><span data-stu-id="a4b11-109">ID</span></span> | <span data-ttu-id="a4b11-110">설명</span><span class="sxs-lookup"><span data-stu-id="a4b11-110">Description</span></span> | <span data-ttu-id="a4b11-111">리포지토리</span><span class="sxs-lookup"><span data-stu-id="a4b11-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="a4b11-112">.NET SDK</span><span class="sxs-lookup"><span data-stu-id="a4b11-112">The .NET SDK</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="a4b11-113">.NET [웹 SDK](/aspnet/core/razor-pages/web-sdk)</span><span class="sxs-lookup"><span data-stu-id="a4b11-113">The .NET [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | <https://github.com/dotnet/sdk> |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="a4b11-114">.NET [Razor SDK](/aspnet/core/razor-pages/sdk)</span><span class="sxs-lookup"><span data-stu-id="a4b11-114">The .NET [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="a4b11-115">.NET 작업자 서비스 SDK</span><span class="sxs-lookup"><span data-stu-id="a4b11-115">The .NET Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="a4b11-116">WinForms(Windows Forms) 및 WPF(Windows Presentation Foundation)가 포함된 .NET [데스크톱 SDK](msbuild-props-desktop.md)\*</span><span class="sxs-lookup"><span data-stu-id="a4b11-116">The .NET [Desktop SDK](msbuild-props-desktop.md), which includes Windows Forms (WinForms) and Windows Presentation Foundation (WPF).\*</span></span> | <span data-ttu-id="a4b11-117"><https://github.com/dotnet/winforms> 및 <https://github.com/dotnet/wpf></span><span class="sxs-lookup"><span data-stu-id="a4b11-117"><https://github.com/dotnet/winforms> and <https://github.com/dotnet/wpf></span></span> |

<span data-ttu-id="a4b11-118">.NET SDK는 .NET용 기본 SDK입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-118">The .NET SDK is the base SDK for .NET.</span></span> <span data-ttu-id="a4b11-119">다른 SDK는 .NET SDK를 참조하며 다른 SDK와 연결된 프로젝트는 모든 .NET SDK 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-119">The other SDKs reference the .NET SDK, and projects that are associated with the other SDKs have all the .NET SDK properties available to them.</span></span> <span data-ttu-id="a4b11-120">예를 들어 웹 SDK는 .NET SDK 및 Razor SDK에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-120">The Web SDK, for example, depends on both the .NET SDK and the Razor SDK.</span></span>

<span data-ttu-id="a4b11-121">NuGet을 통해 배포할 수 있는 고유한 SDK를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-121">You can also author your own SDK that can be distributed via NuGet.</span></span>

<span data-ttu-id="a4b11-122">\* .NET 5.0부터 Windows Forms 및 WPF(Windows Presentation Foundation) 프로젝트는 `Microsoft.NET.Sdk.WindowsDesktop`대신 .NET SDK(`Microsoft.NET.Sdk`)를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-122">\* Starting in .NET 5.0, Windows Forms and Windows Presentation Foundation (WPF) projects should specify the .NET SDK (`Microsoft.NET.Sdk`) instead of `Microsoft.NET.Sdk.WindowsDesktop`.</span></span> <span data-ttu-id="a4b11-123">이러한 프로젝트의 경우 `TargetFramework`를 `net5.0-windows`로 설정하고 `UseWPF` 또는 `UseWindowsForms`를 `true`로 설정하면 Windows 데스크톱 SDK를 자동으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-123">For these projects, setting `TargetFramework` to `net5.0-windows` and `UseWPF` or `UseWindowsForms` to `true` will automatically import the Windows desktop SDK.</span></span> <span data-ttu-id="a4b11-124">프로젝트가 .NET 5.0 이상을 대상으로 하고 `Microsoft.NET.Sdk.WindowsDesktop` SDK를 지정하는 경우 빌드 경고 NETSDK1137이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-124">If your project targets .NET 5.0 or later and specifies the `Microsoft.NET.Sdk.WindowsDesktop` SDK, you'll get build warning NETSDK1137.</span></span>

## <a name="project-files"></a><span data-ttu-id="a4b11-125">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="a4b11-125">Project files</span></span>

<span data-ttu-id="a4b11-126">.NET 프로젝트는 [MSBuild](/visualstudio/msbuild/msbuild) 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-126">.NET projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="a4b11-127">*.csproj*(C# 프로젝트) 및 *.fsproj*(F# 프로젝트) 같은 확장명을 가진 프로젝트 파일은 XML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-127">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="a4b11-128">MSBuild 프로젝트 파일의 루트 요소는 [Project](/visualstudio/msbuild/project-element-msbuild) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-128">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="a4b11-129">`Project` 요소에는 사용할 SDK(및 버전)를 지정하는 선택적 `Sdk` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-129">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="a4b11-130">.NET 도구를 사용하고 코드를 빌드하려면 `Sdk` 특성을 [사용 가능한 SDK](#available-sdks) 표의 ID 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-130">To use the .NET tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="a4b11-131">NuGet에서 제공되는 SDK를 지정하려면 이름 끝에 버전을 포함하거나 *global.json* 파일에서 이름 및 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-131">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="a4b11-132">SDK를 지정하는 또 다른 방법은 최상위 [Sdk](/visualstudio/msbuild/sdk-element-msbuild) 요소를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-132">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="a4b11-133">이러한 방법 중 하나로 SDK를 참조하는 것은 .NET 프로젝트 파일이 크게 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-133">Referencing an SDK in one of these ways greatly simplifies project files for .NET.</span></span> <span data-ttu-id="a4b11-134">프로젝트를 평가하는 동안 MSBuild는 프로젝트 파일 맨 위에 `Sdk.props`의 암시적 가져오기를 추가하고 맨 아래에 `Sdk.targets`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-134">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> <span data-ttu-id="a4b11-135">Windows 머신에서 *Sdk.props* 및 *Sdk.targets* 파일은 *%ProgramFiles%\dotnet\sdk\\[버전]\Sdks\Microsoft.NET.Sdk\Sdk* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-135">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="a4b11-136">프로젝트 파일 전처리</span><span class="sxs-lookup"><span data-stu-id="a4b11-136">Preprocess the project file</span></span>

<span data-ttu-id="a4b11-137">`dotnet msbuild -preprocess` 명령을 사용하여 SDK 및 해당 대상이 포함된 후 MSBuild에서 보는 것처럼 완전히 확장된 프로젝트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-137">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="a4b11-138">[`dotnet msbuild`](../tools/dotnet-msbuild.md) 명령의 [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) 스위치는 가져온 파일, 해당 소스 및 실제로 프로젝트를 빌드하지 않는 빌드에 대한 기여를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-138">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="a4b11-139">프로젝트에 대상 프레임워크가 여러 개 있는 경우 명령의 결과는 대상을 MSBuild 속성으로 지정하여 프레임워크 하나에만 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-139">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="a4b11-140">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a4b11-140">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

## <a name="default-includes-and-excludes"></a><span data-ttu-id="a4b11-141">기본 포함 및 제외</span><span class="sxs-lookup"><span data-stu-id="a4b11-141">Default includes and excludes</span></span>

<span data-ttu-id="a4b11-142">[`Compile` 항목](/visualstudio/msbuild/common-msbuild-project-items#compile), [포함된 리소스](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource), [`None` 항목](/visualstudio/msbuild/common-msbuild-project-items#none)의 기본 포함 및 제외는 SDK에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-142">The default includes and excludes for [`Compile` items](/visualstudio/msbuild/common-msbuild-project-items#compile), [embedded resources](/visualstudio/msbuild/common-msbuild-project-items#embeddedresource), and [`None` items](/visualstudio/msbuild/common-msbuild-project-items#none) are defined in the SDK.</span></span> <span data-ttu-id="a4b11-143">SDK가 아닌 .NET Framework 프로젝트와 달리 기본값은 대부분의 일반적인 사용 사례를 처리하므로 프로젝트 파일에서 해당 항목을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-143">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="a4b11-144">따라서 프로젝트 파일이 크기가 줄어들고 이해하기가 더 쉬워지며 필요에 따라 수동으로 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-144">This behavior makes the project file smaller and easier to understand and edit by hand, if needed.</span></span>

<span data-ttu-id="a4b11-145">다음 표에는 .NET SDK에 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-145">The following table shows which elements and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET SDK:</span></span>

| <span data-ttu-id="a4b11-146">요소</span><span class="sxs-lookup"><span data-stu-id="a4b11-146">Element</span></span>           | <span data-ttu-id="a4b11-147">GLOB 포함</span><span class="sxs-lookup"><span data-stu-id="a4b11-147">Include glob</span></span>                              | <span data-ttu-id="a4b11-148">GLOB 제외</span><span class="sxs-lookup"><span data-stu-id="a4b11-148">Exclude glob</span></span>                                                  | <span data-ttu-id="a4b11-149">GLOB 제거</span><span class="sxs-lookup"><span data-stu-id="a4b11-149">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | <span data-ttu-id="a4b11-150">\*\*/\*.cs(또는 기타 언어 확장)</span><span class="sxs-lookup"><span data-stu-id="a4b11-150">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="a4b11-151">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a4b11-151">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="a4b11-152">N/A</span><span class="sxs-lookup"><span data-stu-id="a4b11-152">N/A</span></span>                      |
| EmbeddedResource  | <span data-ttu-id="a4b11-153">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a4b11-153">\*\*/\*.resx</span></span>                              | <span data-ttu-id="a4b11-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a4b11-154">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a4b11-155">N/A</span><span class="sxs-lookup"><span data-stu-id="a4b11-155">N/A</span></span>                      |
| None              | \*\*/\*                                   | <span data-ttu-id="a4b11-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a4b11-156">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a4b11-157">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a4b11-157">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="a4b11-158">`$(BaseOutputPath)` 및 `$(BaseIntermediateOutputPath)` MSBuild 속성으로 나타내는 `./bin` 및 `./obj` 폴더는 기본적으로 GLOB에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-158">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="a4b11-159">제외는 [DefaultItemExcludes 속성](msbuild-props.md#defaultitemexcludes)으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-159">Excludes are represented by the [DefaultItemExcludes property](msbuild-props.md#defaultitemexcludes).</span></span>

<span data-ttu-id="a4b11-160">.NET 데스크톱 SDK에는 WPF에 대한 더 많은 포함 및 제외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-160">The .NET Desktop SDK has more includes and excludes for WPF.</span></span> <span data-ttu-id="a4b11-161">자세한 내용은 [WPF 기본 포함 및 제외](msbuild-props-desktop.md#wpf-default-includes-and-excludes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b11-161">For more information, see [WPF default includes and excludes](msbuild-props-desktop.md#wpf-default-includes-and-excludes).</span></span>

### <a name="build-errors"></a><span data-ttu-id="a4b11-162">빌드 오류</span><span class="sxs-lookup"><span data-stu-id="a4b11-162">Build errors</span></span>

<span data-ttu-id="a4b11-163">프로젝트 파일에서 이러한 항목을 명시적으로 정의하는 경우 다음과 비슷한 "NETSDK1022" 빌드 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-163">If you explicitly define any of these items in your project file, you're likely to get a "NETSDK1022" build error similar to the following:</span></span>

> <span data-ttu-id="a4b11-164">중복 ‘Compile’ 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-164">Duplicate 'Compile' items were included.</span></span> <span data-ttu-id="a4b11-165">.NET SDK에는 기본적으로 프로젝트 디렉터리의 ‘Compile’ 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-165">The .NET SDK includes 'Compile' items from your project directory by default.</span></span> <span data-ttu-id="a4b11-166">프로젝트 파일에서 해당 항목을 제거하거나, 프로젝트 파일에서 해당 항목을 명시적으로 포함하려면 ‘EnableDefaultCompileItems’ 속성을 ‘false’로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-166">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

> <span data-ttu-id="a4b11-167">중복 ‘EmbeddedResource’ 항목이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-167">Duplicate 'EmbeddedResource' items were included.</span></span> <span data-ttu-id="a4b11-168">.NET SDK에는 기본적으로 프로젝트 디렉터리의 ‘EmbeddedResource’ 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-168">The .NET SDK includes 'EmbeddedResource' items from your project directory by default.</span></span> <span data-ttu-id="a4b11-169">프로젝트 파일에서 해당 항목을 제거하거나, 프로젝트 파일에서 해당 항목을 명시적으로 포함하려면 ‘EnableDefaultEmbeddedResourceItems’ 속성을 ‘false’로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-169">You can either remove these items from your project file, or set the 'EnableDefaultEmbeddedResourceItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="a4b11-170">오류를 해결하려면 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-170">To resolve the errors, do one of the following:</span></span>

- <span data-ttu-id="a4b11-171">앞의 표에 나열된 암시적 `Compile`, `EmbeddedResource` 또는 `None` 항목과 일치하는 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-171">Remove the explicit `Compile`, `EmbeddedResource`, or `None` items that match the implicit ones listed on the previous table.</span></span>

- <span data-ttu-id="a4b11-172">모든 암시적 파일 포함을 사용하지 않으려면 [EnableDefaultItems 속성](msbuild-props.md#enabledefaultitems)을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-172">Set the [EnableDefaultItems property](msbuild-props.md#enabledefaultitems) to `false` to disable all implicit file inclusion:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="a4b11-173">앱과 함께 게시할 파일을 지정하려는 경우 해당 항목(예: `Content` 요소)에 알려진 MSBuild 메커니즘을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-173">If you want to specify files to be published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

- <span data-ttu-id="a4b11-174">[EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems) 또는 [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) 속성을 `false`로 설정하여 `Compile`, `EmbeddedResource` 또는 `None` GLOB를 선택적으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-174">Selectively disable only `Compile`, `EmbeddedResource`, or `None` globs by setting the [EnableDefaultCompileItems](msbuild-props.md#enabledefaultcompileitems), [EnableDefaultEmbeddedResourceItems](msbuild-props.md#enabledefaultembeddedresourceitems), or [EnableDefaultNoneItems](msbuild-props.md#enabledefaultnoneitems) property to `false`:</span></span>

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  <span data-ttu-id="a4b11-175">`Compile` GLOB만 사용하지 않도록 설정하는 경우 Visual Studio의 솔루션 탐색기는 \*.cs 항목을 `None` 항목으로 포함된 프로젝트의 일부로 계속 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-175">If you only disable `Compile` globs, Solution Explorer in Visual Studio still shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="a4b11-176">암시적 `None` GLOB를 사용하지 않도록 설정하려면 `EnableDefaultNoneItems`도 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-176">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false` too.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="a4b11-177">암시적 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="a4b11-177">Implicit package references</span></span>

<span data-ttu-id="a4b11-178">.NET Core 1.0 ~ 2.2 또는 .NET Standard 1.0 ~ 2.0을 대상으로 지정하는 경우 .NET SDK는 특정 메타패키지에 대한 암시적 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-178">When targeting .NET Core 1.0 - 2.2 or .NET Standard 1.0 - 2.0, the .NET SDK adds implicit references to certain *metapackages*.</span></span> <span data-ttu-id="a4b11-179">메타패키지는 다른 패키지에 대한 종속성으로만 구성된 프레임워크 기반 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-179">A metapackage is a framework-based package that consists only of dependencies on other packages.</span></span> <span data-ttu-id="a4b11-180">메타패키지는 프로젝트 파일의 [TargetFramework](msbuild-props.md#targetframework) 또는 [TargetFrameworks](msbuild-props.md#targetframeworks) 속성에 지정된 대상 프레임워크를 기준으로 암시적으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-180">Metapackages are implicitly referenced based on the target framework(s) specified in the [TargetFramework](msbuild-props.md#targetframework) or [TargetFrameworks](msbuild-props.md#targetframeworks) property of your project file.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp2.1</TargetFramework>
</PropertyGroup>
```

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="a4b11-181">필요한 경우 [DisableImplicitFrameworkReferences](msbuild-props.md#disableimplicitframeworkreferences) 속성을 사용하여 암시적 패키지 참조를 비활성화하고 필요한 프레임워크 또는 패키지에 대해서만 명시적 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-181">If needed, you can disable implicit package references using the [DisableImplicitFrameworkReferences](msbuild-props.md#disableimplicitframeworkreferences) property, and add explicit references to just the frameworks or packages you need.</span></span>

<span data-ttu-id="a4b11-182">권장 사항:</span><span class="sxs-lookup"><span data-stu-id="a4b11-182">Recommendations:</span></span>

- <span data-ttu-id="a4b11-183">.NET Framework, .NET Core 1.0 ~ 2.2 또는 .NET Standard 1.0 ~ 2.0을 대상으로 하는 경우 프로젝트 파일의 `<PackageReference>` 항목을 통해 `Microsoft.NETCore.App` 또는 `NETStandard.Library` 메타패키지에 대한 명시적 참조를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a4b11-183">When targeting .NET Framework, .NET Core 1.0 - 2.2, or .NET Standard 1.0 - 2.0, don't add an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span> <span data-ttu-id="a4b11-184">.NET Core 1.0~2.2 및 .NET Standard 1.0~2.0 프로젝트의 경우 이러한 메타패키지를 암시적으로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-184">For .NET Core 1.0 - 2.2 and .NET Standard 1.0 - 2.0 projects, these metapackages are implicitly referenced.</span></span> <span data-ttu-id="a4b11-185">.NET Framework 프로젝트의 경우 .NET Standard 기반 NuGet 패키지를 사용할 때 모든 버전의 `NETStandard.Library`가 필요하면 NuGet은 자동으로 해당 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-185">For .NET Framework projects, if any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>
- <span data-ttu-id="a4b11-186">.NET Core 1.0 ~ 2.2을 대상으로 할 때 특정 버전의 런타임이 필요하면 메타패키지를 참조하는 대신 프로젝트의 `<RuntimeFrameworkVersion>` 속성(예: `1.0.4`)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-186">If you need a specific version of the runtime when targeting .NET Core 1.0 - 2.2, use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span> <span data-ttu-id="a4b11-187">예를 들어 [자체 포함 배포](../deploying/index.md#publish-self-contained)를 사용하는 경우 1.0.0 LTS 런타임의 특정 패치 버전이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-187">For example, you might need a specific patch version of 1.0.0 LTS runtime if you're using [self-contained deployments](../deploying/index.md#publish-self-contained).</span></span>
- <span data-ttu-id="a4b11-188">.NET Standard 1.0 ~ 2.0을 대상으로 할 때 특정 버전의 `NETStandard.Library` 메타패키지가 필요하면 `<NetStandardImplicitPackageVersion>` 속성을 사용하고 필요한 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-188">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard 1.0 - 2.0, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>

## <a name="build-events"></a><span data-ttu-id="a4b11-189">빌드 이벤트</span><span class="sxs-lookup"><span data-stu-id="a4b11-189">Build events</span></span>

<span data-ttu-id="a4b11-190">SDK 스타일 프로젝트에서 `PreBuild` 또는 `PostBuild`라는 MSBuild 대상을 사용하고 `PreBuild`에 대해 `BeforeTargets` 속성을 설정하거나 `PostBuild`에 대해 `AfterTargets` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-190">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>
> - <span data-ttu-id="a4b11-191">MSBuild 대상에는 원하는 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-191">You can use any name for the MSBuild targets.</span></span> <span data-ttu-id="a4b11-192">그러나 Visual Studio IDE는 `PreBuild` 및 `PostBuild` 대상을 인식하므로 해당 이름을 사용하여 IDE에서 명령을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-192">However, the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so by using those names, you can edit the commands in the IDE.</span></span>
> - <span data-ttu-id="a4b11-193">`$(ProjectDir)` 같은 매크로는 확인되지 않으므로 SDK 스타일 프로젝트에서는 `PreBuildEvent` 및 `PostBuildEvent` 속성을 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-193">The properties `PreBuildEvent` and `PostBuildEvent` are not recommended in SDK-style projects, because macros such as `$(ProjectDir)` aren't resolved.</span></span> <span data-ttu-id="a4b11-194">예를 들어, 다음 코드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-194">For example, the following code is not supported:</span></span>
>
> ```xml
> <PropertyGroup>
>   <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
> </PropertyGroup>
> ```

## <a name="customize-the-build"></a><span data-ttu-id="a4b11-195">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a4b11-195">Customize the build</span></span>

<span data-ttu-id="a4b11-196">다양한 방법으로 [빌드를 사용자 지정](/visualstudio/msbuild/customize-your-build)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-196">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="a4b11-197">[msbuild](/visualstudio/msbuild/msbuild-command-line-reference) 또는 [dotnet](../tools/index.md) 명령에 인수로 전달하여 속성을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-197">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="a4b11-198">또한 프로젝트 파일 또는 *Directory.Build.props* 파일에 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-198">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="a4b11-199">.NET 프로젝트의 유용한 속성 목록을 보려면 [.NET SDK 프로젝트용 MSBuild 참조](msbuild-props.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b11-199">For a list of useful properties for .NET projects, see [MSBuild reference for .NET SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="a4b11-200">사용자 지정 대상</span><span class="sxs-lookup"><span data-stu-id="a4b11-200">Custom targets</span></span>

<span data-ttu-id="a4b11-201">.NET 프로젝트는 패키지를 사용하는 프로젝트에서 사용할 사용자 지정 MSBuild 대상 및 속성을 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-201">.NET projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="a4b11-202">다음을 수행하려는 경우 이 유형의 확장성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-202">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="a4b11-203">빌드 프로세스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-203">Extend the build process.</span></span>
- <span data-ttu-id="a4b11-204">생성된 파일과 같은 빌드 프로세스의 아티팩트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-204">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="a4b11-205">빌드를 호출하는 데 사용된 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-205">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="a4b11-206">프로젝트의 *build* 폴더에 `<package_id>.targets` 또는 `<package_id>.props`(예: `Contoso.Utility.UsefulStuff.targets`) 형식의 파일을 배치하여 사용자 지정 빌드 대상 또는 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-206">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="a4b11-207">다음 XML은 [`dotnet pack`](../tools/dotnet-pack.md) 명령에 패키지할 항목을 알리는 *.csproj* 파일의 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-207">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="a4b11-208">`<ItemGroup Label="dotnet pack instructions">` 요소는 패키지 내부 *build* 폴더에 대상 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-208">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="a4b11-209">`<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` 요소는 *build* 폴더에 어셈블리 및 *.json* 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-209">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...

</Project>
```

<span data-ttu-id="a4b11-210">프로젝트에서 사용자 지정 대상을 사용하려면 패키지 및 해당 버전을 가리키는 `PackageReference` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-210">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="a4b11-211">도구와 달리 사용자 지정 대상 패키지는 사용하는 프로젝트의 종속성 종료 항목에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-211">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="a4b11-212">사용자 지정 대상을 사용하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-212">You can configure how to use the custom target.</span></span> <span data-ttu-id="a4b11-213">MSBuild 대상이므로 지정된 대상에 종속되거나, 다른 대상 이후에 실행되거나, `dotnet msbuild -t:<target-name>` 명령을 사용하여 수동으로 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-213">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="a4b11-214">그러나 더 나은 사용자 환경을 제공하려면 프로젝트별 도구 및 사용자 지정 대상을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-214">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="a4b11-215">이 시나리오에서 프로젝트별 도구는 필요한 모든 매개 변수를 허용하며 대상을 실행하는 필수 [`dotnet msbuild`](../tools/dotnet-msbuild.md) 호출로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-215">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="a4b11-216">이러한 종류의 시너지 효과는 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 프로젝트의 [MVP Summit 2016 Hackathon 샘플](https://github.com/dotnet/MVPSummitHackathon2016) 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b11-216">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b11-217">참조</span><span class="sxs-lookup"><span data-stu-id="a4b11-217">See also</span></span>

- [<span data-ttu-id="a4b11-218">.NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="a4b11-218">Install .NET Core</span></span>](../install/index.yml)
- [<span data-ttu-id="a4b11-219">MSBuild 프로젝트 SDK 사용 방법</span><span class="sxs-lookup"><span data-stu-id="a4b11-219">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="a4b11-220">NuGet을 사용하여 사용자 지정 MSBuild 대상 및 속성 패키지</span><span class="sxs-lookup"><span data-stu-id="a4b11-220">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
