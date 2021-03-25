---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET SDK에서 이해하는 MSBuild 속성 및 항목에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 18f2be734fa10e2fd4977166ab4334332b120a91
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604764"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="2170a-103">.NET SDK 프로젝트용 MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="2170a-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="2170a-104">이 페이지는 .NET 프로젝트를 구성하는 데 사용할 수 있는 MSBuild 속성 및 항목에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="2170a-105">이 페이지는 진행 중인 작업이며 .NET SDK의 유용한 MSBuild 속성이 모두 나열된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="2170a-106">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="2170a-107">프레임워크 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-107">Framework properties</span></span>

- [<span data-ttu-id="2170a-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="2170a-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="2170a-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="2170a-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="2170a-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="2170a-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="2170a-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="2170a-111">TargetFramework</span></span>

<span data-ttu-id="2170a-112">`TargetFramework` 속성은 앱의 대상 프레임워크 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="2170a-113">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="2170a-114">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="2170a-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="2170a-115">TargetFrameworks</span></span>

<span data-ttu-id="2170a-116">앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="2170a-117">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="2170a-118">`TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="2170a-119">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="2170a-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="2170a-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="2170a-121">이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="2170a-122">`netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="2170a-123">메타패키지 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="2170a-124">다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="2170a-125">패키지 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-125">Package properties</span></span>

<span data-ttu-id="2170a-126">`PackageId`, `PackageVersion`, `PackageIcon`, `Title`, `Description`과 같은 속성을 지정하여 프로젝트에서 생성되는 패키지를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="2170a-127">이러한 속성 및 다른 속성에 대한 자세한 내용은 [팩 대상](/nuget/reference/msbuild-targets#pack-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-items-and-metadata"></a><span data-ttu-id="2170a-128">속성, 항목 및 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="2170a-128">Publish properties, items, and metadata</span></span>

- [<span data-ttu-id="2170a-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="2170a-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="2170a-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="2170a-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="2170a-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="2170a-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="2170a-132">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="2170a-132">CopyToPublishDirectory</span></span>](#copytopublishdirectory)
- [<span data-ttu-id="2170a-133">LinkBase</span><span class="sxs-lookup"><span data-stu-id="2170a-133">LinkBase</span></span>](#linkbase)
- [<span data-ttu-id="2170a-134">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="2170a-134">PreserveCompilationContext</span></span>](#preservecompilationcontext)
- [<span data-ttu-id="2170a-135">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="2170a-135">PreserveCompilationReferences</span></span>](#preservecompilationreferences)
- [<span data-ttu-id="2170a-136">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="2170a-136">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="2170a-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2170a-137">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="2170a-138">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="2170a-138">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="2170a-139">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="2170a-139">UseAppHost</span></span>](#useapphost)

### <a name="copytopublishdirectory"></a><span data-ttu-id="2170a-140">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="2170a-140">CopyToPublishDirectory</span></span>

<span data-ttu-id="2170a-141">MSBuild 항목의 `CopyToPublishDirectory` 메타데이터는 항목이 게시 디렉터리에 복사되는 시기를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-141">The `CopyToPublishDirectory` metadata on an MSBuild item controls when the item is copied to the publish directory.</span></span> <span data-ttu-id="2170a-142">허용되는 값은 항목이 변경된 경우에만 항목을 복사하는 `PreserveNewest`, 항목을 항상 복사하는 `Always`, 항목을 복사하지 않는 `Never`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-142">Allowable values are `PreserveNewest`, which only copies the item if it has changed, `Always`, which always copies the item, and `Never`, which never copies the item.</span></span> <span data-ttu-id="2170a-143">성능 관점에서 증분 빌드를 사용하기 때문에 `PreserveNewest`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-143">From a performance standpoint, `PreserveNewest` is preferable because it enables an incremental build.</span></span>

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a><span data-ttu-id="2170a-144">LinkBase</span><span class="sxs-lookup"><span data-stu-id="2170a-144">LinkBase</span></span>

<span data-ttu-id="2170a-145">프로젝트 디렉터리와 해당 하위 디렉터리의 외부에 있는 항목의 경우 게시 대상은 항목의 [Link 메타데이터](/visualstudio/msbuild/common-msbuild-item-metadata)를 사용하여 항목을 복사할 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-145">For an item that's outside of the project directory and its subdirectories, the publish target uses the item's [Link metadata](/visualstudio/msbuild/common-msbuild-item-metadata) to determine where to copy the item to.</span></span> <span data-ttu-id="2170a-146">`Link`는 프로젝트 트리 외부의 항목이 Visual Studio의 솔루션 탐색기 창에 표시되는 방식도 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-146">`Link` also determines how items outside of the project tree are displayed in the Solution Explorer window of Visual Studio.</span></span>

<span data-ttu-id="2170a-147">프로젝트 범위 밖에 있는 항목에 대해 `Link`를 지정하지 않으면 기본적으로 `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-147">If `Link` is not specified for an item that's outside of the project cone, it defaults to `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)`.</span></span> <span data-ttu-id="2170a-148">`LinkBase`를 사용하여 프로젝트 범위 밖에 있는 항목의 적절한 기본 폴더를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-148">`LinkBase` lets you specify a sensible base folder for items outside of the project cone.</span></span> <span data-ttu-id="2170a-149">기본 폴더 아래의 폴더 계층 구조는 `RecursiveDir`을 통해 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-149">The folder hierarchy under the base folder is preserved via `RecursiveDir`.</span></span> <span data-ttu-id="2170a-150">`LinkBase`를 지정하지 않으면 `Link` 경로에서 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-150">If `LinkBase` is not specified, it's omitted from the `Link` path.</span></span>

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

<span data-ttu-id="2170a-151">다음 이미지는 이전 항목 `Include` GLOB를 통해 포함되는 파일이 솔루션 탐색기에 표시되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-151">The following image shows how a file that's included via the previous item `Include` glob displays in Solution Explorer.</span></span>

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="LinkBase 메타데이터가 있는 항목을 보여 주는 솔루션 탐색기":::

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="2170a-153">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="2170a-153">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="2170a-154">`AppendTargetFrameworkToOutputPath` 속성은 [TFM(대상 프레임워크 모니커)](../../standard/frameworks.md)을 출력 경로([OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)에 정의)에 추가할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-154">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="2170a-155">.NET SDK는 대상 프레임워크와 런타임 식별자(있는 경우)를 출력 경로에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-155">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="2170a-156">`AppendTargetFrameworkToOutputPath`를 `false`로 설정하면 TFM이 출력 경로에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-156">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="2170a-157">그러나 출력 경로에 TFM이 없으면 여러 빌드 아티팩트가 서로 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-157">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="2170a-158">예를 들어 .NET 5.0 앱에서 다음과 같이 설정하면 출력 경로가 `bin\Debug\net5.0`에서 `bin\Debug`로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-158">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="2170a-159">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="2170a-159">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="2170a-160">`AppendRuntimeIdentifierToOutputPath` 속성은 [RID(런타임 식별자)](../rid-catalog.md)를 출력 경로에 추가할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-160">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="2170a-161">.NET SDK는 대상 프레임워크와 런타임 식별자(있는 경우)를 출력 경로에 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-161">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="2170a-162">`AppendRuntimeIdentifierToOutputPath`를 `false`로 설정하면 RID가 출력 경로에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-162">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="2170a-163">예를 들어 .NET 5.0 앱에서 RID가 `win10-x64`인 경우 다음과 같이 설정하면 출력 경로가 `bin\Debug\net5.0\win10-x64`에서 `bin\Debug\net5.0`으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-163">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="2170a-164">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="2170a-164">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="2170a-165">`CopyLocalLockFileAssemblies` 속성은 다른 라이브러리에 대한 종속성이 있는 플러그 인 프로젝트에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-165">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="2170a-166">이 속성을 `true`로 설정하면 NuGet 패키지 종속성이 출력 디렉터리에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-166">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="2170a-167">즉, `dotnet build`의 출력을 사용하여 모든 머신에서 플러그 인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-167">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="2170a-168">또는 `dotnet publish`를 사용하여 클래스 라이브러리를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-168">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="2170a-169">자세한 내용은 [dotnet publish](../tools/dotnet-publish.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-169">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="preservecompilationcontext"></a><span data-ttu-id="2170a-170">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="2170a-170">PreserveCompilationContext</span></span>

<span data-ttu-id="2170a-171">`PreserveCompilationContext` 속성을 사용하면 빌드되거나 게시된 애플리케이션이 빌드 타임에 사용된 것과 같은 설정을 사용하여 런타임에 더 많은 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-171">The `PreserveCompilationContext` property allows a built or published application to compile more code at run time using the same settings that were used at build time.</span></span> <span data-ttu-id="2170a-172">빌드 타임에 참조된 어셈블리는 출력 디렉터리의 *ref* 하위 디렉터리에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-172">The assemblies referenced at build time will be copied into the *ref* subdirectory of the output directory.</span></span> <span data-ttu-id="2170a-173">참조 어셈블리의 이름은 컴파일러에 전달된 옵션과 함께 애플리케이션의 *.deps.json* 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-173">The names of the reference assemblies are stored in the application's *.deps.json* file along with the options passed to the compiler.</span></span> <span data-ttu-id="2170a-174"><xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> 및 <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType> 속성을 사용하여 이 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-174">You can retrieve this information using the <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> and <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType> properties.</span></span>

<span data-ttu-id="2170a-175">이 기능은 주로 Razor 파일의 런타임 컴파일을 지원하기 위해 ASP.NET Core MVC 및 Razor Pages에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-175">This functionality is mostly used internally by ASP.NET Core MVC and Razor pages to support run-time compilation of Razor files.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationContext>true</PreserveCompilationContext>
</PropertyGroup>
```

### <a name="preservecompilationreferences"></a><span data-ttu-id="2170a-176">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="2170a-176">PreserveCompilationReferences</span></span>

<span data-ttu-id="2170a-177">`PreserveCompilationReferences` 속성은 [PreserveCompilationContext](#preservecompilationcontext) 속성과 유사합니다. 단, 참조된 어셈블리를 게시 디렉터리에만 복사하고 *.deps.json* 파일에는 복사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-177">The `PreserveCompilationReferences` property is similar to the [PreserveCompilationContext](#preservecompilationcontext) property, except that it only copies the referenced assemblies to the publish directory, and not the *.deps.json* file.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationReferences>true</PreserveCompilationReferences>
</PropertyGroup>
```

<span data-ttu-id="2170a-178">자세한 내용은 [Razor SDK 속성](/aspnet/core/razor-pages/sdk#properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-178">For more information, see [Razor SDK properties](/aspnet/core/razor-pages/sdk#properties).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="2170a-179">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="2170a-179">RuntimeIdentifier</span></span>

<span data-ttu-id="2170a-180">`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-180">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="2170a-181">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-181">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="2170a-182">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2170a-182">RuntimeIdentifiers</span></span>

<span data-ttu-id="2170a-183">`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-183">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="2170a-184">여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-184">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="2170a-185">`RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-185">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="2170a-186">단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-186">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="2170a-187">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="2170a-187">TrimmerRootAssembly</span></span>

<span data-ttu-id="2170a-188">`TrimmerRootAssembly` 항목을 사용하면 [‘트리밍’](../deploying/trim-self-contained.md)에서 어셈블리를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-188">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="2170a-189">트리밍은 패키지된 애플리케이션에서 런타임의 사용되지 않은 부분을 제거하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-189">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="2170a-190">일부 경우에는 트리밍이 필요한 참조를 잘못 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-190">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="2170a-191">다음 XML은 트리밍에서 `System.Security` 어셈블리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-191">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="2170a-192">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="2170a-192">UseAppHost</span></span>

<span data-ttu-id="2170a-193">`UseAppHost` 속성은 배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-193">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="2170a-194">자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-194">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="2170a-195">.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-195">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="2170a-196">`UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-196">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="2170a-197">배포에 대한 자세한 내용은 [.NET 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-197">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="2170a-198">컴파일 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-198">Compile properties</span></span>

- [<span data-ttu-id="2170a-199">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="2170a-199">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="2170a-200">LangVersion</span><span class="sxs-lookup"><span data-stu-id="2170a-200">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="2170a-201">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="2170a-201">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="2170a-202">`EmbeddedResourceUseDependentUponConvention` 속성은 리소스 파일과 공동 배치된 소스 파일의 형식 정보에서 리소스 매니페스트 파일 이름을 생성할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-202">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="2170a-203">예를 들어 *Form1.resx* 가 *Form1.cs* 와 동일한 폴더에 있고 `EmbeddedResourceUseDependentUponConvention`가 `true`로 설정된 경우 생성된 *.resources* 파일은 *Form1.cs* 에 정의된 첫 번째 형식에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-203">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="2170a-204">예를 들어 `MyNamespace.Form1`이 *Form1.cs* 에 정의된 첫 번째 형식이면 생성된 파일 이름은 *MyNamespace.Form1.resources* 입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-204">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="2170a-205">`LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 `EmbeddedResource` 항목에 대해 지정된 경우 해당 리소스 파일에 대해 생성된 매니페스트 파일 이름은 이러한 메타데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-205">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="2170a-206">기본적으로 새 .NET 프로젝트에서 이 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-206">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="2170a-207">이 속성이 `false`로 설정되고 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 *.resx* 파일의 상대 파일 경로를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-207">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="2170a-208">자세한 내용은 [리소스 매니페스트 파일 이름이 지정되는 방식](../resources/manifest-file-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-208">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="2170a-209">LangVersion</span><span class="sxs-lookup"><span data-stu-id="2170a-209">LangVersion</span></span>

<span data-ttu-id="2170a-210">`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-210">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="2170a-211">예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-211">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="2170a-212">자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-212">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="2170a-213">기본 항목 포함 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-213">Default item inclusion properties</span></span>

- [<span data-ttu-id="2170a-214">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="2170a-214">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="2170a-215">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="2170a-215">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="2170a-216">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="2170a-216">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="2170a-217">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="2170a-217">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="2170a-218">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="2170a-218">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="2170a-219">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="2170a-219">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="2170a-220">자세한 내용은 [기본 포함 및 제외](overview.md#default-includes-and-excludes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-220">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="2170a-221">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="2170a-221">DefaultItemExcludes</span></span>

<span data-ttu-id="2170a-222">`DefaultItemExcludes` 속성을 사용하면 GLOB 포함, 제외 및 제거에서 제외할 파일과 폴더의 GLOB 패턴을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-222">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="2170a-223">기본적으로 *./bin* 및 *./obj* 폴더는 GLOB 패턴에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-223">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="2170a-224">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="2170a-224">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="2170a-225">`DefaultExcludesInProjectFolder` 속성을 사용하면 GLOB 포함, 제외, 제거에서 제외할 프로젝트 폴더에 있는 파일과 폴더의 GLOB 패턴을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-225">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="2170a-226">기본적으로 *.git*, *.vs* 등과 같이 마침표(`.`)로 시작하는 폴더는 GLOB 패턴에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-226">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="2170a-227">이 속성은 `DefaultItemExcludes` 속성과 매우 유사하지만 프로젝트 폴더의 파일과 폴더만 고려한다는 점만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-227">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="2170a-228">의도치 않게 GLOB 패턴이 상대 경로를 사용하는 프로젝트 폴더 외부의 항목과 일치되는 경우에는 `DefaultItemExcludes` 속성 대신 `DefaultExcludesInProjectFolder` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-228">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="2170a-229">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="2170a-229">EnableDefaultItems</span></span>

<span data-ttu-id="2170a-230">`EnableDefaultItems` 속성은 컴파일 항목, 포함 리소스 항목, `None` 항목을 프로젝트에 암시적으로 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-230">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="2170a-231">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-231">The default value is `true`.</span></span> <span data-ttu-id="2170a-232">모든 암시적 파일 포함을 사용하지 않으려면 `EnableDefaultItems` 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-232">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="2170a-233">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="2170a-233">EnableDefaultCompileItems</span></span>

<span data-ttu-id="2170a-234">`EnableDefaultCompileItems` 속성은 컴파일 항목을 프로젝트에 암시적으로 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-234">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="2170a-235">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-235">The default value is `true`.</span></span> <span data-ttu-id="2170a-236">\*.cs 및 기타 언어 확장 파일의 암시적 포함을 사용하지 않으려면 `EnableDefaultCompileItems` 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-236">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="2170a-237">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="2170a-237">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="2170a-238">`EnableDefaultEmbeddedResourceItems` 속성은 포함 리소스 항목을 프로젝트에 암시적으로 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-238">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="2170a-239">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-239">The default value is `true`.</span></span> <span data-ttu-id="2170a-240">포함 리소스 파일의 암시적 포함을 사용하지 않으려면 `EnableDefaultEmbeddedResourceItems` 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-240">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="2170a-241">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="2170a-241">EnableDefaultNoneItems</span></span>

<span data-ttu-id="2170a-242">`EnableDefaultNoneItems` 속성은 `None` 항목(빌드 프로세스에서 아무 역할이 없는 파일)을 프로젝트에 암시적으로 포함할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-242">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="2170a-243">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-243">The default value is `true`.</span></span> <span data-ttu-id="2170a-244">`None` 항목의 암시적 포함을 사용하지 않으려면 `EnableDefaultNoneItems` 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-244">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="2170a-245">코드 분석 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-245">Code analysis properties</span></span>

- [<span data-ttu-id="2170a-246">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="2170a-246">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="2170a-247">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="2170a-247">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="2170a-248">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="2170a-248">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="2170a-249">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="2170a-249">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="2170a-250">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="2170a-250">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="2170a-251">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="2170a-251">AnalysisLevel</span></span>

<span data-ttu-id="2170a-252">`AnalysisLevel` 속성을 사용하여 코드 분석 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-252">The `AnalysisLevel` property lets you specify a code-analysis level.</span></span> <span data-ttu-id="2170a-253">예를 들어 코드 분석기를 미리 보기 위해 액세스하려면 `AnalysisLevel`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-253">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span>

<span data-ttu-id="2170a-254">기본값:</span><span class="sxs-lookup"><span data-stu-id="2170a-254">Default value:</span></span>

- <span data-ttu-id="2170a-255">프로젝트가 .NET 5.0 이상을 대상으로 하거나 [AnalysisMode](#analysismode) 속성을 추가한 경우 기본값은 `latest`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-255">If your project targets .NET 5.0 or later, or if you've added the [AnalysisMode](#analysismode) property, the default value is `latest`.</span></span>
- <span data-ttu-id="2170a-256">그렇지 않으면 프로젝트 파일에 명시적으로 추가하지 않는 한 이 속성이 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-256">Otherwise, this property is omitted unless you explicitly add it to the project file.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="2170a-257">다음 표에 사용 가능한 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-257">The following table shows the available options.</span></span>

| <span data-ttu-id="2170a-258">값</span><span class="sxs-lookup"><span data-stu-id="2170a-258">Value</span></span> | <span data-ttu-id="2170a-259">의미</span><span class="sxs-lookup"><span data-stu-id="2170a-259">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="2170a-260">릴리스된 최신 코드 분석기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-260">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="2170a-261">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-261">This is the default.</span></span> |
| `preview` | <span data-ttu-id="2170a-262">최신 코드 분석기는 미리 보기로 제공되는 경우에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-262">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="2170a-263">최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-263">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="2170a-264">최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-264">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

> [!NOTE]
> <span data-ttu-id="2170a-265">이 속성은 [프로젝트 SDK](overview.md)를 참조하지 않는 프로젝트의 코드 분석에 영향을 주지 않습니다(예: Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지를 참조하는 레거시 .NET Framework 프로젝트).</span><span class="sxs-lookup"><span data-stu-id="2170a-265">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="analysismode"></a><span data-ttu-id="2170a-266">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="2170a-266">AnalysisMode</span></span>

<span data-ttu-id="2170a-267">.NET 5.0부터 .NET SDK에는 모든 [“CA” 모드 품질 규칙](../../fundamentals/code-analysis/quality-rules/index.md)이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-267">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="2170a-268">기본적으로 [일부 규칙만 빌드 경고로 사용 설정](../../fundamentals/code-analysis/overview.md#enabled-rules)됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-268">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="2170a-269">`AnalysisMode` 속성을 사용하면 기본적으로 사용하도록 설정되는 규칙 집합을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-269">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="2170a-270">더욱 적극적인(옵트아웃) 분석 모드나 더욱 보수적인(옵트인) 분석 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-270">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="2170a-271">예를 들어 기본적으로 모든 규칙을 빌드 경고로 사용하도록 설정하려는 경우 값을 `AllEnabledByDefault`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-271">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="2170a-272">다음 표에 사용 가능한 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-272">The following table shows the available options.</span></span>

| <span data-ttu-id="2170a-273">값</span><span class="sxs-lookup"><span data-stu-id="2170a-273">Value</span></span> | <span data-ttu-id="2170a-274">의미</span><span class="sxs-lookup"><span data-stu-id="2170a-274">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="2170a-275">특정 규칙이 빌드 경고로 사용되고, 다른 특정 규칙이 Visual Studio IDE 추천으로 사용되며, 나머지는 사용하지 않도록 설정되는 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-275">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="2170a-276">모든 규칙이 기본적으로 빌드 경고로 사용되는 적극적인(또는 옵트아웃) 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-276">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="2170a-277">개별 규칙을 선택적으로 [옵트아웃](../../fundamentals/code-analysis/configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-277">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="2170a-278">모든 규칙이 기본적으로 사용하지 않도록 설정되는 보수적인(또는 옵트인) 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-278">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="2170a-279">개별 규칙을 선택적으로 [옵트인](../../fundamentals/code-analysis/configuration-options.md)하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-279">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

> [!NOTE]
> <span data-ttu-id="2170a-280">이 속성은 [프로젝트 SDK](overview.md)를 참조하지 않는 프로젝트의 코드 분석에 영향을 주지 않습니다(예: Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지를 참조하는 레거시 .NET Framework 프로젝트).</span><span class="sxs-lookup"><span data-stu-id="2170a-280">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="2170a-281">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="2170a-281">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="2170a-282">`CodeAnalysisTreatWarningsAsErrors` 속성을 사용하면 코드 품질 분석 경고(CAxxxx)를 경고로 처리할지 여부를 구성하고 빌드를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-282">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="2170a-283">프로젝트를 빌드할 때 `-warnaserror` 플래그를 사용하면 [.NET 코드 품질 분석](../../fundamentals/code-analysis/overview.md#code-quality-analysis) 경고도 오류로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-283">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="2170a-284">코드 품질 분석 경고를 오류로 처리하지 않으려는 경우 프로젝트 파일에서 `CodeAnalysisTreatWarningsAsErrors` MSBuild 속성을 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-284">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="2170a-285">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="2170a-285">EnableNETAnalyzers</span></span>

<span data-ttu-id="2170a-286">.NET 5.0 이상을 대상으로 하는 프로젝트의 경우 기본적으로 [.NET 코드 품질 분석](../../fundamentals/code-analysis/overview.md#code-quality-analysis)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-286">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="2170a-287">`EnableNETAnalyzers` 속성을 `true`로 설정하여 이전 버전의 .NET을 대상으로 하는 SDK 스타일 프로젝트에서 .NET 코드 분석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-287">You can enable .NET code analysis for SDK-style projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="2170a-288">모든 프로젝트에서 코드 분석을 사용하지 않으려면 해당 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-288">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="2170a-289">이 속성은 특히 .NET 5+ SDK의 기본 제공 분석기에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-289">This property applies specifically to the built-in analyzers in the .NET 5+ SDK.</span></span> <span data-ttu-id="2170a-290">NuGet 코드 분석 패키지를 설치할 때 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-290">It should not be used when you install a NuGet code analysis package.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="2170a-291">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="2170a-291">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="2170a-292">이 기능은 현재 시험용으로 제공되며 .NET 5 릴리스와 .NET 6 릴리스 사이에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-292">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="2170a-293">[.NET 코드 스타일 분석](../../fundamentals/code-analysis/overview.md#code-style-analysis)은 모든 .NET 프로젝트에 대해 빌드 시 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-293">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="2170a-294">`EnforceCodeStyleInBuild` 속성을 `true`로 설정하여 .NET 프로젝트에 대해 코드 스타일 분석을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-294">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="2170a-295">경고 또는 오류로 [구성된](../../fundamentals/code-analysis/overview.md#code-style-analysis) 모든 코드 스타일 규칙은 빌드 및 보고 위반 시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-295">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="2170a-296">런타임 구성 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-296">Run-time configuration properties</span></span>

<span data-ttu-id="2170a-297">앱의 프로젝트 파일에서 MSBuild 속성을 지정하여 몇 가지 런타임 동작을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-297">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="2170a-298">런타임 동작을 구성하는 다른 방법에 관한 내용은 [런타임 구성 설정](../run-time-config/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-298">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="2170a-299">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-299">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="2170a-300">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="2170a-300">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="2170a-301">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-301">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="2170a-302">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-302">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="2170a-303">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2170a-303">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="2170a-304">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="2170a-304">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="2170a-305">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="2170a-305">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="2170a-306">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="2170a-306">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="2170a-307">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="2170a-307">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="2170a-308">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-308">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="2170a-309">`ConcurrentGarbageCollection` 속성은 [백그라운드(동시) 가비지 수집](../../standard/garbage-collection/background-gc.md)이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-309">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="2170a-310">백그라운드 가비지 수집을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-310">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="2170a-311">자세한 내용은 [백그라운드 GC](../run-time-config/garbage-collector.md#background-gc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-311">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="2170a-312">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="2170a-312">InvariantGlobalization</span></span>

<span data-ttu-id="2170a-313">`InvariantGlobalization` 속성은 앱이 문화권별 데이터에 액세스할 수 없는 ‘세계화 고정’ 모드에서 실행되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-313">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="2170a-314">세계화 고정 모드에서 실행하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-314">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="2170a-315">자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-315">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="2170a-316">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-316">RetainVMGarbageCollection</span></span>

<span data-ttu-id="2170a-317">`RetainVMGarbageCollection` 속성은 삭제된 메모리 세그먼트를 나중에 사용하기 위해 대기 목록에 넣거나 릴리스하도록 가비지 수집기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-317">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="2170a-318">값을 `true`로 설정하여 가비지 수집기가 대기 목록에 세그먼트를 넣도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-318">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="2170a-319">자세한 내용은 [VM 유지](../run-time-config/garbage-collector.md#retain-vm)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-319">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="2170a-320">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="2170a-320">ServerGarbageCollection</span></span>

<span data-ttu-id="2170a-321">`ServerGarbageCollection` 속성은 애플리케이션이 [워크스테이션 가비지 수집 또는 서버 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-321">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="2170a-322">서버 가비지 수집을 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-322">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="2170a-323">자세한 내용은 [워크스테이션과 서버 비교](../run-time-config/garbage-collector.md#workstation-vs-server)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-323">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="2170a-324">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2170a-324">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="2170a-325">`ThreadPoolMaxThreads` 속성은 작업자 스레드 풀의 최대 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-325">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="2170a-326">자세한 내용은 [최대 스레드](../run-time-config/threading.md#maximum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-326">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="2170a-327">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="2170a-327">ThreadPoolMinThreads</span></span>

<span data-ttu-id="2170a-328">`ThreadPoolMinThreads` 속성은 작업자 스레드 풀의 최소 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-328">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="2170a-329">자세한 내용은 [최소 스레드](../run-time-config/threading.md#minimum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-329">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="2170a-330">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="2170a-330">TieredCompilation</span></span>

<span data-ttu-id="2170a-331">`TieredCompilation` 속성은 JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-331">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="2170a-332">계층화된 컴파일을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-332">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="2170a-333">자세한 내용은 [계층화된 컴파일](../run-time-config/compilation.md#tiered-compilation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-333">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="2170a-334">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="2170a-334">TieredCompilationQuickJit</span></span>

<span data-ttu-id="2170a-335">`TieredCompilationQuickJit` 속성은 JIT 컴파일러가 빠른 JIT를 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-335">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="2170a-336">빠른 JIT를 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-336">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="2170a-337">자세한 내용은 [빠른 JIT](../run-time-config/compilation.md#quick-jit)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-337">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="2170a-338">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="2170a-338">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="2170a-339">`TieredCompilationQuickJitForLoops` 속성은 JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-339">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="2170a-340">루프를 포함하는 메서드에서 빠른 JIT를 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-340">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="2170a-341">자세한 내용은 [루프에 대한 빠른 JIT](../run-time-config/compilation.md#quick-jit-for-loops)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-341">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="2170a-342">참조 속성 및 항목</span><span class="sxs-lookup"><span data-stu-id="2170a-342">Reference properties and items</span></span>

- [<span data-ttu-id="2170a-343">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="2170a-343">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="2170a-344">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="2170a-344">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="2170a-345">PackageReference</span><span class="sxs-lookup"><span data-stu-id="2170a-345">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="2170a-346">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="2170a-346">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="2170a-347">참조</span><span class="sxs-lookup"><span data-stu-id="2170a-347">Reference</span></span>](#reference)
- [<span data-ttu-id="2170a-348">복원 관련 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-348">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="2170a-349">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="2170a-349">AssetTargetFallback</span></span>

<span data-ttu-id="2170a-350">`AssetTargetFallback` 속성을 사용하여 프로젝트 참조 및 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-350">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="2170a-351">예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-351">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="2170a-352">참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-352">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span> <span data-ttu-id="2170a-353">해당 속성은 사용되지 않는 속성 `PackageTargetFallback`을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-353">This property replaces the deprecated property `PackageTargetFallback`.</span></span>

<span data-ttu-id="2170a-354">`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-frameworks)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-354">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="2170a-355">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="2170a-355">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="2170a-356">`DisableImplicitFrameworkReferences` 속성은 .NET Core 3.0 이상 버전을 대상으로 하는 경우 암시적 `FrameworkReference` 항목을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-356">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="2170a-357">.NET Core 2.1 또는 .NET Standard 2.0 이전 버전을 대상으로 하는 경우에는 메타패키지의 패키지에 대한 암시적 [PackageReference](#packagereference) 항목을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-357">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="2170a-358">(메타패키지는 다른 패키지에 대한 종속성으로만 구성된 프레임워크 기반 패키지입니다.) 또한 이 속성은 .NET Framework를 대상으로 하는 경우 `System`, `System.Core` 등과 같은 암시적 참조도 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-358">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="2170a-359">암시적 `FrameworkReference` 또는 [PackageReference](#packagereference) 항목을 사용하지 않도록 설정하려면 이 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-359">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="2170a-360">이 속성을 `true`로 설정하면 필요한 프레임워크나 패키지에만 명시적 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-360">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="2170a-361">PackageReference</span><span class="sxs-lookup"><span data-stu-id="2170a-361">PackageReference</span></span>

<span data-ttu-id="2170a-362">`PackageReference` 항목은 NuGet 패키지에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-362">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="2170a-363">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-363">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="2170a-364">`Version` 특성은 버전 또는 버전 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-364">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="2170a-365">최소 버전, 최대 버전, 범위 또는 정확한 일치를 지정하는 방법에 대한 자세한 내용은 [버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-365">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="2170a-366">[자산 특성](#asset-attributes)을 패키지 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-366">You can also add [asset attributes](#asset-attributes) to a package reference.</span></span>

<span data-ttu-id="2170a-367">다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-367">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="2170a-368">자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-368">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

#### <a name="asset-attributes"></a><span data-ttu-id="2170a-369">자산 특성</span><span class="sxs-lookup"><span data-stu-id="2170a-369">Asset attributes</span></span>

<span data-ttu-id="2170a-370">`IncludeAssets`, `ExcludeAssets` 및 `PrivateAssets` 메타데이터를 패키지 참조에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-370">The `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets` metadata can be added to a package reference.</span></span>

| <span data-ttu-id="2170a-371">attribute</span><span class="sxs-lookup"><span data-stu-id="2170a-371">Attribute</span></span> | <span data-ttu-id="2170a-372">설명</span><span class="sxs-lookup"><span data-stu-id="2170a-372">Description</span></span> |
| - | - |
| `IncludeAssets` | <span data-ttu-id="2170a-373">`<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-373">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="2170a-374">기본적으로 모든 패키지 자산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-374">By default, all package assets are included.</span></span> |
| `ExcludeAssets`| <span data-ttu-id="2170a-375">`<PackageReference>`에서 지정한 패키지에 속하여 사용하면 안 되는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-375">Specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span> |
| `PrivateAssets` | <span data-ttu-id="2170a-376">`<PackageReference>`에서 지정한 패키지에 속하여 사용하지만 다음 프로젝트로 전달하지 않아야 하는 자산을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-376">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="2170a-377">해당 특성이 없으면 `Analyzers`, `Build` 및 `ContentFiles` 자산이 기본적으로 프라이빗이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-377">The `Analyzers`, `Build`, and `ContentFiles` assets are private by default when this attribute is not present.</span></span> |

<span data-ttu-id="2170a-378">해당 특성은 다음 항목 중 하나 이상을 포함할 수 있습니다. 둘 이상이 나열되는 경우 세미콜론 `;`으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-378">These attributes can contain one or more of the following items, separated by a semicolon `;` if more than one is listed:</span></span>

- <span data-ttu-id="2170a-379">`Compile` - *lib* 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-379">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="2170a-380">`Runtime` - *런타임* 폴더의 콘텐츠가 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-380">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="2170a-381">`ContentFiles` - *contentfiles* 폴더의 콘텐츠가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-381">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="2170a-382">`Build` - *빌드* 폴더의 속성/대상이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-382">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="2170a-383">`Native` - 런타임에 네이티브 자산의 콘텐츠가 *출력* 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-383">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="2170a-384">`Analyzers` – 분석기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-384">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="2170a-385">또는 다음 특성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-385">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="2170a-386">`None` – 자산이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-386">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="2170a-387">`All` – 모든 자산이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-387">`All` – all assets are used.</span></span>

### <a name="projectreference"></a><span data-ttu-id="2170a-388">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="2170a-388">ProjectReference</span></span>

<span data-ttu-id="2170a-389">`ProjectReference` 항목은 다른 프로젝트에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-389">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="2170a-390">참조된 프로젝트는 NuGet 패키지 종속성으로 추가됩니다. 즉, `PackageReference`와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-390">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="2170a-391">`Include` 특성은 프로젝트의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-391">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="2170a-392">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-392">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="2170a-393">다음 예제의 프로젝트 파일 코드 조각은 `Project2`라는 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-393">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="2170a-394">참고</span><span class="sxs-lookup"><span data-stu-id="2170a-394">Reference</span></span>

<span data-ttu-id="2170a-395">`Reference` 항목은 어셈블리 파일에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-395">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="2170a-396">`Include` 특성은 파일의 이름을 지정하고, `HintPath` 메타데이터는 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-396">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="2170a-397">복원 관련 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-397">Restore-related properties</span></span>

<span data-ttu-id="2170a-398">참조된 패키지를 복원하면 패키지의 직접 종속성과 해당 종속성의 종속성이 모두 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-398">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="2170a-399">`RestorePackagesPath` 및 `RestoreIgnoreFailedSources`와 같은 속성을 지정하여 패키지 복원을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-399">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="2170a-400">이러한 속성 및 다른 속성에 대한 자세한 내용은 [복원 대상](/nuget/reference/msbuild-targets#restore-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-400">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="2170a-401">실행 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-401">Run properties</span></span>

<span data-ttu-id="2170a-402">다음 속성은 [`dotnet run`](../tools/dotnet-run.md) 명령을 사용하여 앱을 시작하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-402">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="2170a-403">RunArguments</span><span class="sxs-lookup"><span data-stu-id="2170a-403">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="2170a-404">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="2170a-404">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="2170a-405">RunArguments</span><span class="sxs-lookup"><span data-stu-id="2170a-405">RunArguments</span></span>

<span data-ttu-id="2170a-406">`RunArguments` 속성은 앱이 실행될 때 앱에 전달되는 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-406">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="2170a-407">[`dotnet run`의 `--` 옵션](../tools/dotnet-run.md#options)을 사용하면 앱에 전달할 추가 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-407">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="2170a-408">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="2170a-408">RunWorkingDirectory</span></span>

<span data-ttu-id="2170a-409">`RunWorkingDirectory` 속성은 애플리케이션 프로세스를 시작할 작업 디렉터리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-409">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="2170a-410">절대 경로이거나 프로젝트 디렉터리의 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-410">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="2170a-411">디렉터리를 지정하지 않으면 `OutDir`이 작업 디렉터리로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-411">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="2170a-412">호스팅 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-412">Hosting properties</span></span>

- [<span data-ttu-id="2170a-413">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="2170a-413">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="2170a-414">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="2170a-414">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="2170a-415">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="2170a-415">EnableComHosting</span></span>

<span data-ttu-id="2170a-416">`EnableComHosting` 속성은 어셈블리가 COM 서버를 제공함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-416">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="2170a-417">`EnableComHosting`을 `true`로 설정하면 [EnableDynamicLoading](#enabledynamicloading)도 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-417">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="2170a-418">자세한 내용은 [COM에 .NET 구성 요소 공개](../native-interop/expose-components-to-com.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2170a-418">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="2170a-419">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="2170a-419">EnableDynamicLoading</span></span>

<span data-ttu-id="2170a-420">`EnableDynamicLoading` 속성은 어셈블리가 동적으로 로드된 구성 요소임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-420">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="2170a-421">구성 요소는 [네이티브 호스트에서 사용](../tutorials/netcore-hosting.md)할 수 있는 [COM 라이브러리](/windows/win32/com/the-component-object-model) 또는 비 COM 라이브러리일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-421">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="2170a-422">이 속성을 `true`로 설정하면 다음과 같은 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-422">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="2170a-423">*.runtimeconfig.json* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-423">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="2170a-424">[롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)가 `LatestMinor`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-424">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="2170a-425">NuGet 참조가 로컬로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2170a-425">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="2170a-426">참조</span><span class="sxs-lookup"><span data-stu-id="2170a-426">See also</span></span>

- [<span data-ttu-id="2170a-427">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="2170a-427">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="2170a-428">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-428">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="2170a-429">NuGet 압축의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-429">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="2170a-430">NuGet 복원의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="2170a-430">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="2170a-431">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2170a-431">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
