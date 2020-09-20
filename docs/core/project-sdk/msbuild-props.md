---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET Core SDK가 이해하는 MSBuild 속성 및 항목에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: c1093a0acd5b75ae6478767d690966a30fe84a31
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656264"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="df0be-103">.NET Core SDK 프로젝트용 MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="df0be-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="df0be-104">이 페이지는 .NET Core 프로젝트를 구성하는 데 사용할 수 있는 MSBuild 속성 및 항목에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="df0be-105">이 페이지는 진행 중인 작업이며 .NET Core SDK의 일부 유용한 MSBuild 속성을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="df0be-106">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="df0be-107">프레임워크 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-107">Framework properties</span></span>

- [<span data-ttu-id="df0be-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="df0be-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="df0be-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="df0be-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="df0be-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="df0be-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="df0be-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="df0be-111">TargetFramework</span></span>

<span data-ttu-id="df0be-112">`TargetFramework` 속성은 앱의 대상 프레임워크 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="df0be-113">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="df0be-114">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="df0be-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="df0be-115">TargetFrameworks</span></span>

<span data-ttu-id="df0be-116">앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="df0be-117">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-frameworks)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="df0be-118">`TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="df0be-119">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="df0be-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="df0be-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="df0be-121">이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="df0be-122">`netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="df0be-123">메타패키지 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="df0be-124">다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="df0be-125">패키지 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-125">Package properties</span></span>

<span data-ttu-id="df0be-126">`PackageId`, `PackageVersion`, `PackageIcon`, `Title`, `Description`과 같은 속성을 지정하여 프로젝트에서 생성되는 패키지를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="df0be-127">이러한 속성 및 다른 속성에 대한 자세한 내용은 [팩 대상](/nuget/reference/msbuild-targets#pack-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="df0be-128">속성 및 항목 게시</span><span class="sxs-lookup"><span data-stu-id="df0be-128">Publish properties and items</span></span>

- [<span data-ttu-id="df0be-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="df0be-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="df0be-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="df0be-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="df0be-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="df0be-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="df0be-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="df0be-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="df0be-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="df0be-133">RuntimeIdentifier</span></span>

<span data-ttu-id="df0be-134">`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="df0be-135">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="df0be-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="df0be-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="df0be-137">`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="df0be-138">여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="df0be-139">`RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="df0be-140">단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="df0be-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="df0be-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="df0be-142">`TrimmerRootAssembly` 항목을 사용하면 [‘트리밍’](../deploying/trim-self-contained.md)에서 어셈블리를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="df0be-143">트리밍은 패키지된 애플리케이션에서 런타임의 사용되지 않은 부분을 제거하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="df0be-144">일부 경우에는 트리밍이 필요한 참조를 잘못 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="df0be-145">다음 XML은 트리밍에서 `System.Security` 어셈블리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="df0be-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="df0be-146">UseAppHost</span></span>

<span data-ttu-id="df0be-147">`UseAppHost` 속성은 .NET Core SDK 2.1.400 버전에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="df0be-148">배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="df0be-149">자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="df0be-150">.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="df0be-151">`UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="df0be-152">배포에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="df0be-153">컴파일 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-153">Compile properties</span></span>

- [<span data-ttu-id="df0be-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="df0be-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="df0be-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="df0be-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="df0be-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="df0be-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="df0be-157">`EmbeddedResourceUseDependentUponConvention` 속성은 리소스 파일과 공동 배치된 소스 파일의 형식 정보에서 리소스 매니페스트 파일 이름을 생성할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="df0be-158">예를 들어 *Form1.resx*가 *Form1.cs*와 동일한 폴더에 있고 `EmbeddedResourceUseDependentUponConvention`가 `true`로 설정된 경우 생성된 *.resources* 파일은 *Form1.cs*에 정의된 첫 번째 형식에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="df0be-159">예를 들어 `MyNamespace.Form1`이 *Form1.cs*에 정의된 첫 번째 형식이면 생성된 파일 이름은 *MyNamespace.Form1.resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="df0be-160">`LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 `EmbeddedResource` 항목에 대해 지정된 경우 해당 리소스 파일에 대해 생성된 매니페스트 파일 이름은 이러한 메타데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="df0be-161">기본적으로 새 .NET Core 프로젝트에서 이 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="df0be-162">이 속성이 `false`로 설정되고 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 *.resx* 파일의 상대 파일 경로를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="df0be-163">자세한 내용은 [리소스 매니페스트 파일 이름이 지정되는 방식](../resources/manifest-file-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="df0be-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="df0be-164">LangVersion</span></span>

<span data-ttu-id="df0be-165">`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="df0be-166">예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="df0be-167">자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="df0be-168">코드 분석 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="df0be-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="df0be-169">AnalysisLevel</span></span>

<span data-ttu-id="df0be-170">`AnalysisLevel` 속성을 사용하여 코드 분석 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="df0be-171">예를 들어 코드 분석기를 미리 보기 위해 액세스하려면 `AnalysisLevel`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="df0be-172">기본값은 `latest`입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="df0be-173">다음 표에 사용 가능한 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-173">The following table shows the available options.</span></span>

| <span data-ttu-id="df0be-174">값</span><span class="sxs-lookup"><span data-stu-id="df0be-174">Value</span></span> | <span data-ttu-id="df0be-175">의미</span><span class="sxs-lookup"><span data-stu-id="df0be-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="df0be-176">릴리스된 최신 코드 분석기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="df0be-177">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="df0be-178">최신 코드 분석기는 미리 보기로 제공되는 경우에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="df0be-179">최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="df0be-180">최신 규칙을 사용할 수 있는 경우에도 .NET 5.0 릴리스에서 사용된 규칙 세트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="df0be-181">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="df0be-181">AnalysisMode</span></span>

<span data-ttu-id="df0be-182">.NET 5.0 RC2부터 .NET SDK에는 모든 [“CA” 모드 품질 규칙](/visualstudio/code-quality/code-analysis-for-managed-code-warnings)이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-182">Starting with .NET 5.0 RC2, the .NET SDK ships with all of the ["CA" code quality rules](/visualstudio/code-quality/code-analysis-for-managed-code-warnings).</span></span> <span data-ttu-id="df0be-183">기본적으로 [일부 규칙만 빌드 경고로 사용 설정](../../fundamentals/productivity/code-analysis.md#enabled-rules)됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-183">By default, only [some rules are enabled](../../fundamentals/productivity/code-analysis.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="df0be-184">`AnalysisMode` 속성을 사용하면 기본적으로 사용하도록 설정되는 규칙 집합을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-184">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="df0be-185">더욱 적극적인(옵트아웃) 분석 모드나 더욱 보수적인(옵트인) 분석 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-185">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="df0be-186">예를 들어 기본적으로 모든 규칙을 빌드 경고로 사용하도록 설정하려는 경우 값을 `AllEnabledByDefault`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-186">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="df0be-187">다음 표에 사용 가능한 옵션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-187">The following table shows the available options.</span></span>

| <span data-ttu-id="df0be-188">값</span><span class="sxs-lookup"><span data-stu-id="df0be-188">Value</span></span> | <span data-ttu-id="df0be-189">의미</span><span class="sxs-lookup"><span data-stu-id="df0be-189">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="df0be-190">특정 규칙이 빌드 경고로 사용되고, 다른 특정 규칙이 Visual Studio IDE 추천으로 사용되며, 나머지는 사용하지 않도록 설정되는 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-190">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="df0be-191">모든 규칙이 기본적으로 빌드 경고로 사용되는 적극적인(또는 옵트아웃) 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-191">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="df0be-192">개별 규칙을 선택적으로 [옵트아웃](../../fundamentals/productivity/configure-code-analysis-rules.md)하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-192">You can selectively [opt out](../../fundamentals/productivity/configure-code-analysis-rules.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="df0be-193">모든 규칙이 기본적으로 사용하지 않도록 설정되는 보수적인(또는 옵트인) 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-193">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="df0be-194">개별 규칙을 선택적으로 [옵트인](../../fundamentals/productivity/configure-code-analysis-rules.md)하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-194">You can selectively [opt into](../../fundamentals/productivity/configure-code-analysis-rules.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="df0be-195">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="df0be-195">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="df0be-196">`CodeAnalysisTreatWarningsAsErrors` 속성을 사용하면 코드 품질 분석 경고(CAxxxx)를 경고로 처리할지 여부를 구성하고 빌드를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-196">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="df0be-197">프로젝트를 빌드할 때 `-warnaserror` 플래그를 사용하면 [.NET 코드 품질 분석](../../fundamentals/productivity/code-analysis.md#code-quality-analysis) 경고도 오류로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-197">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/productivity/code-analysis.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="df0be-198">코드 품질 분석 경고를 오류로 처리하지 않으려는 경우 프로젝트 파일에서 `CodeAnalysisTreatWarningsAsErrors` MSBuild 속성을 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-198">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="df0be-199">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="df0be-199">EnableNETAnalyzers</span></span>

<span data-ttu-id="df0be-200">.NET 5.0 이상을 대상으로 하는 프로젝트의 경우 기본적으로 [.NET 코드 품질 분석](../../fundamentals/productivity/code-analysis.md#code-quality-analysis)이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-200">[.NET code quality analysis](../../fundamentals/productivity/code-analysis.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="df0be-201">`EnableNETAnalyzers` 속성을 `true`로 설정하여 이전 버전의 .NET을 대상으로 하는 프로젝트에서 .NET 코드 분석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-201">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="df0be-202">모든 프로젝트에서 코드 분석을 사용하지 않으려면 해당 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-202">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="df0be-203">.Net 5.0 이전 .NET 버전을 대상으로 하는 프로젝트에서 .NET 코드 분석을 사용할 수 있는 또 다른 방법은 [AnalysisLevel](#analysislevel) 속성을 `latest`로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-203">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="df0be-204">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="df0be-204">EnforceCodeStyleInBuild</span></span>

<span data-ttu-id="df0be-205">[.NET 코드 스타일 분석](../../fundamentals/productivity/code-analysis.md#code-style-analysis)은 모든 .NET 프로젝트에 대해 빌드 시 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-205">[.NET code style analysis](../../fundamentals/productivity/code-analysis.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="df0be-206">`EnforceCodeStyleInBuild` 속성을 `true`로 설정하여 .NET 프로젝트에 대해 코드 스타일 분석을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-206">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="df0be-207">경고 또는 오류로 [구성된](../../fundamentals/productivity/code-analysis.md#code-style-analysis) 모든 코드 스타일 규칙은 빌드 및 보고 위반 시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-207">All code style rules that are [configured](../../fundamentals/productivity/code-analysis.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="df0be-208">런타임 구성 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-208">Run-time configuration properties</span></span>

<span data-ttu-id="df0be-209">앱의 프로젝트 파일에서 MSBuild 속성을 지정하여 몇 가지 런타임 동작을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-209">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="df0be-210">런타임 동작을 구성하는 다른 방법에 관한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-210">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="df0be-211">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-211">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="df0be-212">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="df0be-212">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="df0be-213">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-213">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="df0be-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-214">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="df0be-215">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="df0be-215">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="df0be-216">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="df0be-216">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="df0be-217">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="df0be-217">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="df0be-218">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="df0be-218">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="df0be-219">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="df0be-219">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="df0be-220">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-220">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="df0be-221">`ConcurrentGarbageCollection` 속성은 [백그라운드(동시) 가비지 수집](../../standard/garbage-collection/background-gc.md)이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-221">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="df0be-222">백그라운드 가비지 수집을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-222">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="df0be-223">자세한 내용은 [백그라운드 GC](../run-time-config/garbage-collector.md#background-gc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-223">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="df0be-224">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="df0be-224">InvariantGlobalization</span></span>

<span data-ttu-id="df0be-225">`InvariantGlobalization` 속성은 앱이 문화권별 데이터에 액세스할 수 없는 ‘세계화 고정’ 모드에서 실행되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-225">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="df0be-226">세계화 고정 모드에서 실행하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-226">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="df0be-227">자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-227">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="df0be-228">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-228">RetainVMGarbageCollection</span></span>

<span data-ttu-id="df0be-229">`RetainVMGarbageCollection` 속성은 삭제된 메모리 세그먼트를 나중에 사용하기 위해 대기 목록에 넣거나 릴리스하도록 가비지 수집기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-229">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="df0be-230">값을 `true`로 설정하여 가비지 수집기가 대기 목록에 세그먼트를 넣도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-230">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="df0be-231">자세한 내용은 [VM 유지](../run-time-config/garbage-collector.md#retain-vm)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-231">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="df0be-232">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="df0be-232">ServerGarbageCollection</span></span>

<span data-ttu-id="df0be-233">`ServerGarbageCollection` 속성은 애플리케이션이 [워크스테이션 가비지 수집 또는 서버 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-233">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="df0be-234">서버 가비지 수집을 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-234">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="df0be-235">자세한 내용은 [워크스테이션과 서버 비교](../run-time-config/garbage-collector.md#workstation-vs-server)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-235">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="df0be-236">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="df0be-236">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="df0be-237">`ThreadPoolMaxThreads` 속성은 작업자 스레드 풀의 최대 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-237">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="df0be-238">자세한 내용은 [최대 스레드](../run-time-config/threading.md#maximum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-238">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="df0be-239">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="df0be-239">ThreadPoolMinThreads</span></span>

<span data-ttu-id="df0be-240">`ThreadPoolMinThreads` 속성은 작업자 스레드 풀의 최소 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-240">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="df0be-241">자세한 내용은 [최소 스레드](../run-time-config/threading.md#minimum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-241">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="df0be-242">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="df0be-242">TieredCompilation</span></span>

<span data-ttu-id="df0be-243">`TieredCompilation` 속성은 JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-243">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="df0be-244">계층화된 컴파일을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-244">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="df0be-245">자세한 내용은 [계층화된 컴파일](../run-time-config/compilation.md#tiered-compilation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-245">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="df0be-246">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="df0be-246">TieredCompilationQuickJit</span></span>

<span data-ttu-id="df0be-247">`TieredCompilationQuickJit` 속성은 JIT 컴파일러가 빠른 JIT를 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-247">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="df0be-248">빠른 JIT를 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-248">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="df0be-249">자세한 내용은 [빠른 JIT](../run-time-config/compilation.md#quick-jit)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-249">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="df0be-250">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="df0be-250">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="df0be-251">`TieredCompilationQuickJitForLoops` 속성은 JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-251">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="df0be-252">루프를 포함하는 메서드에서 빠른 JIT를 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-252">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="df0be-253">자세한 내용은 [루프에 대한 빠른 JIT](../run-time-config/compilation.md#quick-jit-for-loops)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-253">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="df0be-254">참조 속성 및 항목</span><span class="sxs-lookup"><span data-stu-id="df0be-254">Reference properties and items</span></span>

- [<span data-ttu-id="df0be-255">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="df0be-255">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="df0be-256">PackageReference</span><span class="sxs-lookup"><span data-stu-id="df0be-256">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="df0be-257">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="df0be-257">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="df0be-258">참조</span><span class="sxs-lookup"><span data-stu-id="df0be-258">Reference</span></span>](#reference)
- [<span data-ttu-id="df0be-259">restore 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-259">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="df0be-260">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="df0be-260">AssetTargetFallback</span></span>

<span data-ttu-id="df0be-261">`AssetTargetFallback` 속성을 사용하여 프로젝트 참조 및 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-261">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="df0be-262">예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-262">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="df0be-263">참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-263">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="df0be-264">`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-frameworks)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-264">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="df0be-265">PackageReference</span><span class="sxs-lookup"><span data-stu-id="df0be-265">PackageReference</span></span>

<span data-ttu-id="df0be-266">`PackageReference` 항목은 NuGet 패키지에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-266">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="df0be-267">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-267">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="df0be-268">`Version` 특성은 버전 또는 버전 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-268">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="df0be-269">최소 버전, 최대 버전, 범위 또는 정확한 일치를 지정하는 방법에 대한 자세한 내용은 [버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-269">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="df0be-270">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-270">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="df0be-271">다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-271">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="df0be-272">자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-272">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="df0be-273">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="df0be-273">ProjectReference</span></span>

<span data-ttu-id="df0be-274">`ProjectReference` 항목은 다른 프로젝트에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-274">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="df0be-275">참조된 프로젝트는 NuGet 패키지 종속성으로 추가됩니다. 즉, `PackageReference`와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-275">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="df0be-276">`Include` 특성은 프로젝트의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-276">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="df0be-277">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-277">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="df0be-278">다음 예제의 프로젝트 파일 코드 조각은 `Project2`라는 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-278">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="df0be-279">참고</span><span class="sxs-lookup"><span data-stu-id="df0be-279">Reference</span></span>

<span data-ttu-id="df0be-280">`Reference` 항목은 어셈블리 파일에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-280">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="df0be-281">`Include` 특성은 파일의 이름을 지정하고, `HintPath` 메타데이터는 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-281">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="df0be-282">restore 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-282">Restore properties</span></span>

<span data-ttu-id="df0be-283">참조된 패키지를 복원하면 패키지의 직접 종속성과 해당 종속성의 종속성이 모두 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-283">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="df0be-284">`RestorePackagesPath` 및 `RestoreIgnoreFailedSources`와 같은 속성을 지정하여 패키지 복원을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df0be-284">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="df0be-285">이러한 속성 및 다른 속성에 대한 자세한 내용은 [복원 대상](/nuget/reference/msbuild-targets#restore-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df0be-285">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="df0be-286">참조</span><span class="sxs-lookup"><span data-stu-id="df0be-286">See also</span></span>

- [<span data-ttu-id="df0be-287">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="df0be-287">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="df0be-288">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-288">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="df0be-289">NuGet 압축의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-289">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="df0be-290">NuGet 복원의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="df0be-290">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="df0be-291">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df0be-291">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
