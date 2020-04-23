---
title: .NET Core 프로젝트 SDK 개요
description: .NET Core 프로젝트 SDK에 대해 알아봅니다.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: d0ac01dca31dffea482745126e00c34b1da20774
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389665"
---
# <a name="net-core-project-sdks"></a><span data-ttu-id="88d4c-103">.NET Core 프로젝트 SDK</span><span class="sxs-lookup"><span data-stu-id="88d4c-103">.NET Core project SDKs</span></span>

<span data-ttu-id="88d4c-104">.NET Core 프로젝트는 SDK(소프트웨어 개발 키트)와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-104">.NET Core projects are associated with a software development kit (SDK).</span></span> <span data-ttu-id="88d4c-105">각 ‘프로젝트 SDK’는 코드를 컴파일, 압축 및 게시해야 하는 MSBuild [대상](/visualstudio/msbuild/msbuild-targets) 및 관련 [작업](/visualstudio/msbuild/msbuild-tasks) 집합입니다. </span><span class="sxs-lookup"><span data-stu-id="88d4c-105">Each *project SDK* is a set of MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and associated [tasks](/visualstudio/msbuild/msbuild-tasks) that are responsible for compiling, packing, and publishing code.</span></span> <span data-ttu-id="88d4c-106">프로젝트 SDK를 참조하는 프로젝트를 ‘SDK 스타일 프로젝트’라고도 합니다. </span><span class="sxs-lookup"><span data-stu-id="88d4c-106">A project that references a project SDK is sometimes referred to as an *SDK-style project*.</span></span>

## <a name="available-sdks"></a><span data-ttu-id="88d4c-107">사용 가능한 SDK</span><span class="sxs-lookup"><span data-stu-id="88d4c-107">Available SDKs</span></span>

<span data-ttu-id="88d4c-108">.NET Core에 사용할 수 있는 SDK는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-108">The following SDKs are available for .NET Core:</span></span>

| <span data-ttu-id="88d4c-109">ID</span><span class="sxs-lookup"><span data-stu-id="88d4c-109">ID</span></span> | <span data-ttu-id="88d4c-110">설명</span><span class="sxs-lookup"><span data-stu-id="88d4c-110">Description</span></span> | <span data-ttu-id="88d4c-111">리포지토리</span><span class="sxs-lookup"><span data-stu-id="88d4c-111">Repo</span></span>|
| - | - | - |
| `Microsoft.NET.Sdk` | <span data-ttu-id="88d4c-112">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="88d4c-112">The .NET Core SDK</span></span> | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | <span data-ttu-id="88d4c-113">.NET Core [웹 SDK](/aspnet/core/razor-pages/web-sdk)</span><span class="sxs-lookup"><span data-stu-id="88d4c-113">The .NET Core [Web SDK](/aspnet/core/razor-pages/web-sdk)</span></span> | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | <span data-ttu-id="88d4c-114">.NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span><span class="sxs-lookup"><span data-stu-id="88d4c-114">The .NET Core [Razor SDK](/aspnet/core/razor-pages/sdk)</span></span> |
| `Microsoft.NET.Sdk.Worker` | <span data-ttu-id="88d4c-115">.NET Core 작업자 서비스 SDK</span><span class="sxs-lookup"><span data-stu-id="88d4c-115">The .NET Core Worker Service SDK</span></span> |
| `Microsoft.NET.Sdk.WindowsDesktop` | <span data-ttu-id="88d4c-116">.NET Core WinForms 및 WPF SDK</span><span class="sxs-lookup"><span data-stu-id="88d4c-116">The .NET Core WinForms and WPF SDK</span></span> |

<span data-ttu-id="88d4c-117">.NET Core SDK는 .NET Core의 기본 SDK입니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-117">The .NET Core SDK is the base SDK for .NET Core.</span></span> <span data-ttu-id="88d4c-118">다른 SDK는 .NET Core SDK를 참조하며 다른 SDK와 연결된 프로젝트는 모든 .NET Core SDK 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-118">The other SDKs reference the .NET Core SDK, and projects that are associated with the other SDKs have all the .NET Core SDK properties available to them.</span></span> <span data-ttu-id="88d4c-119">예를 들어 웹 SDK는 .NET Core SDK 및 Razor SDK에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-119">The Web SDK, for example, depends on both the .NET Core SDK and the Razor SDK.</span></span>

<span data-ttu-id="88d4c-120">NuGet을 통해 배포할 수 있는 고유한 SDK를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-120">You can also author your own SDK that can be distributed via NuGet.</span></span>

## <a name="project-files"></a><span data-ttu-id="88d4c-121">프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="88d4c-121">Project files</span></span>

<span data-ttu-id="88d4c-122">.NET Core 프로젝트는 [MSBuild](/visualstudio/msbuild/msbuild) 형식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-122">.NET Core projects are based on the [MSBuild](/visualstudio/msbuild/msbuild) format.</span></span> <span data-ttu-id="88d4c-123">*.csproj*(C# 프로젝트) 및 *.fsproj*(F# 프로젝트) 같은 확장명을 가진 프로젝트 파일은 XML 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-123">Project files, which have extensions like *.csproj* for C# projects and *.fsproj* for F# projects, are in XML format.</span></span> <span data-ttu-id="88d4c-124">MSBuild 프로젝트 파일의 루트 요소는 [Project](/visualstudio/msbuild/project-element-msbuild) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-124">The root element of an MSBuild project file is the [Project](/visualstudio/msbuild/project-element-msbuild) element.</span></span> <span data-ttu-id="88d4c-125">`Project` 요소에는 사용할 SDK(및 버전)를 지정하는 선택적 `Sdk` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-125">The `Project` element has an optional `Sdk` attribute that specifies which SDK (and version) to use.</span></span> <span data-ttu-id="88d4c-126">.NET Core 도구를 사용하고 코드를 빌드하려면 `Sdk` 특성을 [사용 가능한 SDK](#available-sdks) 표의 ID 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-126">To use the .NET Core tools and build your code, set the `Sdk` attribute to one of the IDs in the [Available SDKs](#available-sdks) table.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

<span data-ttu-id="88d4c-127">NuGet에서 제공되는 SDK를 지정하려면 이름 끝에 버전을 포함하거나 *global.json* 파일에서 이름 및 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-127">To specify an SDK that comes from NuGet, include the version at the end of the name, or specify the name and version in the *global.json* file.</span></span>

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

<span data-ttu-id="88d4c-128">SDK를 지정하는 또 다른 방법은 최상위 [Sdk](/visualstudio/msbuild/sdk-element-msbuild) 요소를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-128">Another way to specify the SDK is with the top-level [Sdk](/visualstudio/msbuild/sdk-element-msbuild) element:</span></span>

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

<span data-ttu-id="88d4c-129">해당 방법 중 하나에서 SDK를 참조하면 .NET Core용 프로젝트 파일이 크게 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-129">Referencing an SDK in one of these ways greatly simplifies project files for .NET Core.</span></span> <span data-ttu-id="88d4c-130">프로젝트를 평가하는 동안 MSBuild는 프로젝트 파일 맨 위에 `Sdk.props`의 암시적 가져오기를 추가하고 맨 아래에 `Sdk.targets`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-130">While evaluating the project, MSBuild adds implicit imports for `Sdk.props` at the top of the project file and `Sdk.targets` at the bottom.</span></span>

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
> <span data-ttu-id="88d4c-131">Windows 머신에서 *Sdk.props* 및 *Sdk.targets* 파일은 *%ProgramFiles%\dotnet\sdk\\[버전]\Sdks\Microsoft.NET.Sdk\Sdk* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-131">On a Windows machine, the *Sdk.props* and *Sdk.targets* files can be found in the *%ProgramFiles%\dotnet\sdk\\[version]\Sdks\Microsoft.NET.Sdk\Sdk* folder.</span></span>

### <a name="preprocess-the-project-file"></a><span data-ttu-id="88d4c-132">프로젝트 파일 전처리</span><span class="sxs-lookup"><span data-stu-id="88d4c-132">Preprocess the project file</span></span>

<span data-ttu-id="88d4c-133">`dotnet msbuild -preprocess` 명령을 사용하여 SDK 및 해당 대상이 포함된 후 MSBuild에서 보는 것처럼 완전히 확장된 프로젝트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-133">You can see the fully expanded project as MSBuild sees it after the SDK and its targets are included by using the `dotnet msbuild -preprocess` command.</span></span> <span data-ttu-id="88d4c-134">[`dotnet msbuild`](../tools/dotnet-msbuild.md) 명령의 [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) 스위치는 가져온 파일, 해당 소스 및 실제로 프로젝트를 빌드하지 않는 빌드에 대한 기여를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-134">The [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) switch of the [`dotnet msbuild`](../tools/dotnet-msbuild.md) command shows which files are imported, their sources, and their contributions to the build without actually building the project.</span></span>

<span data-ttu-id="88d4c-135">프로젝트에 대상 프레임워크가 여러 개 있는 경우 명령의 결과는 대상을 MSBuild 속성으로 지정하여 프레임워크 하나에만 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-135">If the project has multiple target frameworks, focus the results of the command on only one framework by specifying it as an MSBuild property.</span></span> <span data-ttu-id="88d4c-136">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="88d4c-136">For example:</span></span>

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a><span data-ttu-id="88d4c-137">기본 컴파일 포함</span><span class="sxs-lookup"><span data-stu-id="88d4c-137">Default compilation includes</span></span>

<span data-ttu-id="88d4c-138">컴파일 항목 및 포함된 리소스의 기본 포함 및 제외는 SDK에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-138">The default includes and excludes for compile items and embedded resources are defined in the SDK.</span></span> <span data-ttu-id="88d4c-139">SDK가 아닌 .NET Framework 프로젝트와 달리 기본값은 대부분의 일반적인 사용 사례를 처리하므로 프로젝트 파일에서 해당 항목을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-139">Unlike non-SDK .NET Framework projects, you don't need to specify these items in your project file, because the defaults cover most common use cases.</span></span> <span data-ttu-id="88d4c-140">결과적으로 프로젝트 파일 수가 줄어 쉽게 이해하고 편집(필요한 경우)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-140">This leads to smaller project files that are easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="88d4c-141">다음 표에는 .NET Core SDK에 포함되거나 제외되는 요소 및 [GLOB](https://en.wikipedia.org/wiki/Glob_(programming))가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-141">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are included and excluded in the .NET Core SDK:</span></span>

| <span data-ttu-id="88d4c-142">요소</span><span class="sxs-lookup"><span data-stu-id="88d4c-142">Element</span></span>           | <span data-ttu-id="88d4c-143">GLOB 포함</span><span class="sxs-lookup"><span data-stu-id="88d4c-143">Include glob</span></span>                              | <span data-ttu-id="88d4c-144">GLOB 제외</span><span class="sxs-lookup"><span data-stu-id="88d4c-144">Exclude glob</span></span>                                                  | <span data-ttu-id="88d4c-145">GLOB 제거</span><span class="sxs-lookup"><span data-stu-id="88d4c-145">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| <span data-ttu-id="88d4c-146">Compile</span><span class="sxs-lookup"><span data-stu-id="88d4c-146">Compile</span></span>           | <span data-ttu-id="88d4c-147">\*\*/\*.cs(또는 기타 언어 확장)</span><span class="sxs-lookup"><span data-stu-id="88d4c-147">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="88d4c-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="88d4c-148">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="88d4c-149">N/A</span><span class="sxs-lookup"><span data-stu-id="88d4c-149">N/A</span></span>                      |
| <span data-ttu-id="88d4c-150">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="88d4c-150">EmbeddedResource</span></span>  | <span data-ttu-id="88d4c-151">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="88d4c-151">\*\*/\*.resx</span></span>                              | <span data-ttu-id="88d4c-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="88d4c-152">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="88d4c-153">N/A</span><span class="sxs-lookup"><span data-stu-id="88d4c-153">N/A</span></span>                      |
| <span data-ttu-id="88d4c-154">없음</span><span class="sxs-lookup"><span data-stu-id="88d4c-154">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="88d4c-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="88d4c-155">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="88d4c-156">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="88d4c-156">\*\*/\*.cs; \*\*/\*.resx</span></span> |

> [!NOTE]
> <span data-ttu-id="88d4c-157">`$(BaseOutputPath)` 및 `$(BaseIntermediateOutputPath)` MSBuild 속성으로 나타내는 `./bin` 및 `./obj` 폴더는 기본적으로 GLOB에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-157">The `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, are excluded from the globs by default.</span></span> <span data-ttu-id="88d4c-158">제외는 `$(DefaultItemExcludes)` 속성으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-158">Excludes are represented by the property `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="88d4c-159">프로젝트 파일에서 해당 항목을 명시적으로 정의하는 경우 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-159">If you explicitly define these items in your project file, you're likely to get the following error:</span></span>

<span data-ttu-id="88d4c-160">**중복된 컴파일 항목이 포함되었습니다. .NET SDK에는 기본적으로 프로젝트 디렉터리의 컴파일 항목이 포함됩니다. 프로젝트 파일에서 해당 항목을 제거하거나, 프로젝트 파일에서 해당 항목을 명시적으로 포함하려면 'EnableDefaultCompileItems' 속성을 'false'로 설정하면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="88d4c-160">**Duplicate Compile items were included. The .NET SDK includes Compile items from your project directory by default. You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.**</span></span>

<span data-ttu-id="88d4c-161">오류를 해결하려면 앞의 표에 나열된 명시적 `Compile` 항목을 제거하거나, `EnableDefaultCompileItems` 속성을 `false`로 설정하여 암시적 포함을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-161">To resolve the error, either remove the explicit `Compile` items that match the implicit ones listed on the previous table, or set the `EnableDefaultCompileItems` property to `false`, which disables implicit inclusion:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="88d4c-162">예를 들어 앱과 함께 게시할 일부 파일을 지정하려는 경우 해당 항목(예: `Content` 요소)에 알려진 MSBuild 메커니즘을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-162">If you want to specify, for example, some files to get published with your app, you can still use the known MSBuild mechanisms for that, for example, the `Content` element.</span></span>

<span data-ttu-id="88d4c-163">`EnableDefaultCompileItems`는 `Compile` GLOB를 사용하지 않도록 설정할 뿐 아니라 \*.cs 항목에도 적용되는 암시적 `None` GLOB 같은 다른 GLOB에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-163">`EnableDefaultCompileItems` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob that also applies to \*.cs items.</span></span> <span data-ttu-id="88d4c-164">이로 인해 Visual Studio의 솔루션 탐색기에는 \*.cs 항목이 `None` 항목으로 포함된 프로젝트의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-164">Because of that, Solution Explorer in Visual Studio shows \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="88d4c-165">암시적 `None` GLOB를 사용하지 않도록 설정하려면 `EnableDefaultNoneItems`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-165">To disable the implicit `None` glob, set `EnableDefaultNoneItems` to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="88d4c-166">‘모든’ 암시적 GLOB를 사용하지 않도록 설정하려면 `EnableDefaultItems` 속성을 `false`로 설정합니다. </span><span class="sxs-lookup"><span data-stu-id="88d4c-166">To disable *all* implicit globs, set the `EnableDefaultItems` property to `false`:</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="customize-the-build"></a><span data-ttu-id="88d4c-167">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="88d4c-167">Customize the build</span></span>

<span data-ttu-id="88d4c-168">다양한 방법으로 [빌드를 사용자 지정](/visualstudio/msbuild/customize-your-build)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-168">There are various ways to [customize a build](/visualstudio/msbuild/customize-your-build).</span></span> <span data-ttu-id="88d4c-169">[msbuild](/visualstudio/msbuild/msbuild-command-line-reference) 또는 [dotnet](../tools/index.md) 명령에 인수로 전달하여 속성을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-169">You may want to override a property by passing it as an argument to an [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) or [dotnet](../tools/index.md) command.</span></span> <span data-ttu-id="88d4c-170">또한 프로젝트 파일 또는 *Directory.Build.props* 파일에 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-170">You can also add the property to the project file or to a *Directory.Build.props* file.</span></span> <span data-ttu-id="88d4c-171">.NET Core 프로젝트의 유용한 속성 목록을 보려면 [.NET Core SDK 프로젝트의 MSBuild 속성](msbuild-props.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88d4c-171">For a list of useful properties for .NET Core projects, see [MSBuild properties for .NET Core SDK projects](msbuild-props.md).</span></span>

### <a name="custom-targets"></a><span data-ttu-id="88d4c-172">사용자 지정 대상</span><span class="sxs-lookup"><span data-stu-id="88d4c-172">Custom targets</span></span>

<span data-ttu-id="88d4c-173">.NET Core 프로젝트는 패키지를 사용하는 프로젝트에서 사용할 사용자 지정 MSBuild 대상 및 속성을 패키지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-173">.NET Core projects can package custom MSBuild targets and properties for use by projects that consume the package.</span></span> <span data-ttu-id="88d4c-174">다음을 수행하려는 경우 이 유형의 확장성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-174">Use this type of extensibility when you want to:</span></span>

- <span data-ttu-id="88d4c-175">빌드 프로세스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-175">Extend the build process.</span></span>
- <span data-ttu-id="88d4c-176">생성된 파일과 같은 빌드 프로세스의 아티팩트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-176">Access artifacts of the build process, such as generated files.</span></span>
- <span data-ttu-id="88d4c-177">빌드를 호출하는 데 사용된 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-177">Inspect the configuration under which the build is invoked.</span></span>

<span data-ttu-id="88d4c-178">프로젝트의 *build* 폴더에 `<package_id>.targets` 또는 `<package_id>.props`(예: `Contoso.Utility.UsefulStuff.targets`) 형식의 파일을 배치하여 사용자 지정 빌드 대상 또는 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-178">You add custom build targets or properties by placing files in the form `<package_id>.targets` or `<package_id>.props` (for example, `Contoso.Utility.UsefulStuff.targets`) in the *build* folder of the project.</span></span>

<span data-ttu-id="88d4c-179">다음 XML은 [`dotnet pack`](../tools/dotnet-pack.md) 명령에 패키지할 항목을 알리는 *.csproj* 파일의 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-179">The following XML is a snippet from a *.csproj* file that instructs the [`dotnet pack`](../tools/dotnet-pack.md) command what to package.</span></span> <span data-ttu-id="88d4c-180">`<ItemGroup Label="dotnet pack instructions">` 요소는 패키지 내부 *build* 폴더에 대상 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-180">The `<ItemGroup Label="dotnet pack instructions">` element places the targets files into the *build* folder inside the package.</span></span> <span data-ttu-id="88d4c-181">`<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` 요소는 *build* 폴더에 어셈블리 및 *.json* 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-181">The `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` element places the assemblies and *.json* files into the *build* folder.</span></span>

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

<span data-ttu-id="88d4c-182">프로젝트에서 사용자 지정 대상을 사용하려면 패키지 및 해당 버전을 가리키는 `PackageReference` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-182">To consume a custom target in your project, add a `PackageReference` element that points to the package and its version.</span></span> <span data-ttu-id="88d4c-183">도구와 달리 사용자 지정 대상 패키지는 사용하는 프로젝트의 종속성 종료 항목에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-183">Unlike the tools, the custom targets package is included in the consuming project's dependency closure.</span></span>

<span data-ttu-id="88d4c-184">사용자 지정 대상을 사용하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-184">You can configure how to use the custom target.</span></span> <span data-ttu-id="88d4c-185">MSBuild 대상이므로 지정된 대상에 종속되거나, 다른 대상 이후에 실행되거나, `dotnet msbuild -t:<target-name>` 명령을 사용하여 수동으로 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-185">Since it's an MSBuild target, it can depend on a given target, run after another target, or be manually invoked by using the `dotnet msbuild -t:<target-name>` command.</span></span> <span data-ttu-id="88d4c-186">그러나 더 나은 사용자 환경을 제공하려면 프로젝트별 도구 및 사용자 지정 대상을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-186">However, to provide a better user experience, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="88d4c-187">이 시나리오에서 프로젝트별 도구는 필요한 모든 매개 변수를 허용하며 대상을 실행하는 필수 [`dotnet msbuild`](../tools/dotnet-msbuild.md) 호출로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-187">In this scenario, the per-project tool accepts whatever parameters are needed and translates that into the required [`dotnet msbuild`](../tools/dotnet-msbuild.md) invocation that executes the target.</span></span> <span data-ttu-id="88d4c-188">이러한 종류의 시너지 효과는 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 프로젝트의 [MVP Summit 2016 Hackathon 샘플](https://github.com/dotnet/MVPSummitHackathon2016) 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d4c-188">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

## <a name="see-also"></a><span data-ttu-id="88d4c-189">참조</span><span class="sxs-lookup"><span data-stu-id="88d4c-189">See also</span></span>

- [<span data-ttu-id="88d4c-190">.NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="88d4c-190">Install .NET Core</span></span>](../install/index.md)
- [<span data-ttu-id="88d4c-191">MSBuild 프로젝트 SDK 사용 방법</span><span class="sxs-lookup"><span data-stu-id="88d4c-191">How to use MSBuild project SDKs</span></span>](/visualstudio/msbuild/how-to-use-project-sdk)
- [<span data-ttu-id="88d4c-192">NuGet을 사용하여 사용자 지정 MSBuild 대상 및 속성 패키지</span><span class="sxs-lookup"><span data-stu-id="88d4c-192">Package custom MSBuild targets and props with NuGet</span></span>](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
