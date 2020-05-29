---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET Core SDK가 이해하는 MSBuild 속성 및 항목에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: cda56b3e23592a341d9fe672fc1f1530adcdab49
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206104"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="d7086-103">.NET Core SDK 프로젝트용 MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="d7086-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="d7086-104">이 페이지는 .NET Core 프로젝트를 구성하는 데 사용할 수 있는 MSBuild 속성 및 항목에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="d7086-105">이 페이지는 진행 중인 작업이며 .NET Core SDK의 일부 유용한 MSBuild 속성을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="d7086-106">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="d7086-107">프레임워크 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-107">Framework properties</span></span>

- [<span data-ttu-id="d7086-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="d7086-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="d7086-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="d7086-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="d7086-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="d7086-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="d7086-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="d7086-111">TargetFramework</span></span>

<span data-ttu-id="d7086-112">`TargetFramework` 속성은 [메타패키지](../packages.md#metapackages)를 암시적으로 참조하는 앱의 대상 프레임워크 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="d7086-113">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="d7086-114">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="d7086-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="d7086-115">TargetFrameworks</span></span>

<span data-ttu-id="d7086-116">앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="d7086-117">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="d7086-118">`TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="d7086-119">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="d7086-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="d7086-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="d7086-121">이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="d7086-122">`netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="d7086-123">[메타패키지](../packages.md#metapackages) 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="d7086-124">다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="d7086-125">패키지 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-125">Package properties</span></span>

<span data-ttu-id="d7086-126">`PackageId`, `PackageVersion`, `PackageIcon`, `Title`, `Description`과 같은 속성을 지정하여 프로젝트에서 생성되는 패키지를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="d7086-127">이러한 속성 및 다른 속성에 대한 자세한 내용은 [팩 대상](/nuget/reference/msbuild-targets#pack-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="d7086-128">속성 및 항목 게시</span><span class="sxs-lookup"><span data-stu-id="d7086-128">Publish properties and items</span></span>

- [<span data-ttu-id="d7086-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="d7086-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="d7086-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="d7086-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="d7086-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="d7086-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="d7086-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="d7086-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="d7086-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="d7086-133">RuntimeIdentifier</span></span>

<span data-ttu-id="d7086-134">`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="d7086-135">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="d7086-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="d7086-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="d7086-137">`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="d7086-138">여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="d7086-139">`RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="d7086-140">단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="d7086-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="d7086-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="d7086-142">`TrimmerRootAssembly` 항목을 사용하면 [‘트리밍’](../deploying/trim-self-contained.md)에서 어셈블리를 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="d7086-143">트리밍은 패키지된 애플리케이션에서 런타임의 사용되지 않은 부분을 제거하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="d7086-144">일부 경우에는 트리밍이 필요한 참조를 잘못 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="d7086-145">다음 XML은 트리밍에서 `System.Security` 어셈블리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="d7086-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="d7086-146">UseAppHost</span></span>

<span data-ttu-id="d7086-147">`UseAppHost` 속성은 .NET Core SDK 2.1.400 버전에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="d7086-148">배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="d7086-149">자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="d7086-150">.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="d7086-151">`UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="d7086-152">배포에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="d7086-153">컴파일 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-153">Compile properties</span></span>

- [<span data-ttu-id="d7086-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="d7086-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="d7086-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="d7086-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="d7086-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="d7086-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="d7086-157">`EmbeddedResourceUseDependentUponConvention` 속성은 리소스 파일과 공동 배치된 소스 파일의 형식 정보에서 리소스 매니페스트 파일 이름을 생성할지 여부를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="d7086-158">예를 들어 *Form1.resx*가 *Form1.cs*와 동일한 폴더에 있고 `EmbeddedResourceUseDependentUponConvention`가 `true`로 설정된 경우 생성된 *.resources* 파일은 *Form1.cs*에 정의된 첫 번째 형식에서 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="d7086-159">예를 들어 `MyNamespace.Form1`이 *Form1.cs*에 정의된 첫 번째 형식이면 생성된 파일 이름은 *MyNamespace.Form1.resources*입니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="d7086-160">`LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 `EmbeddedResource` 항목에 대해 지정된 경우 해당 리소스 파일에 대해 생성된 매니페스트 파일 이름은 이러한 메타데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="d7086-161">기본적으로 새 .NET Core 프로젝트에서 이 속성은 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="d7086-162">이 속성이 `false`로 설정되고 프로젝트 파일의 `EmbeddedResource` 항목에 대해 `LogicalName`, `ManifestResourceName` 또는 `DependentUpon` 메타데이터가 지정되지 않은 경우 리소스 매니페스트 파일 이름은 프로젝트의 루트 네임스페이스와 *.resx* 파일의 상대 파일 경로를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="d7086-163">자세한 내용은 [리소스 매니페스트 파일 이름이 지정되는 방식](../resources/manifest-file-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="d7086-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="d7086-164">LangVersion</span></span>

<span data-ttu-id="d7086-165">`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="d7086-166">예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="d7086-167">자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="d7086-168">런타임 구성 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-168">Run-time configuration properties</span></span>

<span data-ttu-id="d7086-169">앱의 프로젝트 파일에서 MSBuild 속성을 지정하여 몇 가지 런타임 동작을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-169">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="d7086-170">런타임 동작을 구성하는 다른 방법에 관한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-170">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="d7086-171">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-171">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="d7086-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="d7086-172">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="d7086-173">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-173">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="d7086-174">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-174">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="d7086-175">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d7086-175">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="d7086-176">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="d7086-176">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="d7086-177">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="d7086-177">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="d7086-178">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="d7086-178">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="d7086-179">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="d7086-179">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="d7086-180">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-180">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="d7086-181">`ConcurrentGarbageCollection` 속성은 [백그라운드(동시) 가비지 수집](../../standard/garbage-collection/background-gc.md)이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-181">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="d7086-182">백그라운드 가비지 수집을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-182">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="d7086-183">자세한 내용은 [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-183">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="d7086-184">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="d7086-184">InvariantGlobalization</span></span>

<span data-ttu-id="d7086-185">`InvariantGlobalization` 속성은 앱이 문화권별 데이터에 액세스할 수 없는 ‘세계화 고정’ 모드에서 실행되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-185">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="d7086-186">세계화 고정 모드에서 실행하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-186">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="d7086-187">자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-187">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="d7086-188">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-188">RetainVMGarbageCollection</span></span>

<span data-ttu-id="d7086-189">`RetainVMGarbageCollection` 속성은 삭제된 메모리 세그먼트를 나중에 사용하기 위해 대기 목록에 넣거나 릴리스하도록 가비지 수집기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-189">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="d7086-190">값을 `true`로 설정하여 가비지 수집기가 대기 목록에 세그먼트를 넣도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-190">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="d7086-191">자세한 내용은 [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-191">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="d7086-192">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="d7086-192">ServerGarbageCollection</span></span>

<span data-ttu-id="d7086-193">`ServerGarbageCollection` 속성은 애플리케이션이 [워크스테이션 가비지 수집 또는 서버 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-193">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="d7086-194">서버 가비지 수집을 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-194">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="d7086-195">자세한 내용은 [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-195">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="d7086-196">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d7086-196">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="d7086-197">`ThreadPoolMaxThreads` 속성은 작업자 스레드 풀의 최대 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-197">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="d7086-198">자세한 내용은 [최대 스레드](../run-time-config/threading.md#maximum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-198">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="d7086-199">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="d7086-199">ThreadPoolMinThreads</span></span>

<span data-ttu-id="d7086-200">`ThreadPoolMinThreads` 속성은 작업자 스레드 풀의 최소 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-200">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="d7086-201">자세한 내용은 [최소 스레드](../run-time-config/threading.md#minimum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-201">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="d7086-202">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="d7086-202">TieredCompilation</span></span>

<span data-ttu-id="d7086-203">`TieredCompilation` 속성은 JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-203">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="d7086-204">계층화된 컴파일을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-204">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="d7086-205">자세한 내용은 [계층화된 컴파일](../run-time-config/compilation.md#tiered-compilation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-205">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="d7086-206">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="d7086-206">TieredCompilationQuickJit</span></span>

<span data-ttu-id="d7086-207">`TieredCompilationQuickJit` 속성은 JIT 컴파일러가 빠른 JIT를 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-207">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="d7086-208">빠른 JIT를 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-208">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="d7086-209">자세한 내용은 [빠른 JIT](../run-time-config/compilation.md#quick-jit)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-209">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="d7086-210">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="d7086-210">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="d7086-211">`TieredCompilationQuickJitForLoops` 속성은 JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-211">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="d7086-212">루프를 포함하는 메서드에서 빠른 JIT를 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-212">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="d7086-213">자세한 내용은 [루프에 대한 빠른 JIT](../run-time-config/compilation.md#quick-jit-for-loops)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-213">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="d7086-214">참조 속성 및 항목</span><span class="sxs-lookup"><span data-stu-id="d7086-214">Reference properties and items</span></span>

- [<span data-ttu-id="d7086-215">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="d7086-215">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="d7086-216">PackageReference</span><span class="sxs-lookup"><span data-stu-id="d7086-216">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="d7086-217">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="d7086-217">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="d7086-218">참조</span><span class="sxs-lookup"><span data-stu-id="d7086-218">Reference</span></span>](#reference)
- [<span data-ttu-id="d7086-219">restore 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-219">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="d7086-220">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="d7086-220">AssetTargetFallback</span></span>

<span data-ttu-id="d7086-221">`AssetTargetFallback` 속성을 사용하여 프로젝트 참조 및 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-221">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="d7086-222">예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-222">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="d7086-223">참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-223">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="d7086-224">`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-framework-versions)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-224">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="d7086-225">PackageReference</span><span class="sxs-lookup"><span data-stu-id="d7086-225">PackageReference</span></span>

<span data-ttu-id="d7086-226">`PackageReference` 항목은 NuGet 패키지에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-226">The `PackageReference` item defines a reference to a NuGet package.</span></span> <span data-ttu-id="d7086-227">예를 들어 [메타패키지](../packages.md#metapackages) 대신 단일 패키지를 참조하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-227">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="d7086-228">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-228">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="d7086-229">`Version` 특성은 버전 또는 버전 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-229">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="d7086-230">최소 버전, 최대 버전, 범위 또는 정확한 일치를 지정하는 방법에 대한 자세한 내용은 [버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-230">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="d7086-231">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-231">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="d7086-232">다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-232">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="d7086-233">자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-233">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="d7086-234">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="d7086-234">ProjectReference</span></span>

<span data-ttu-id="d7086-235">`ProjectReference` 항목은 다른 프로젝트에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-235">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="d7086-236">참조된 프로젝트는 NuGet 패키지 종속성으로 추가됩니다. 즉, `PackageReference`와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-236">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="d7086-237">`Include` 특성은 프로젝트의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-237">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="d7086-238">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-238">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="d7086-239">다음 예제의 프로젝트 파일 코드 조각은 `Project2`라는 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-239">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="d7086-240">참고</span><span class="sxs-lookup"><span data-stu-id="d7086-240">Reference</span></span>

<span data-ttu-id="d7086-241">`Reference` 항목은 어셈블리 파일에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-241">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="d7086-242">`Include` 특성은 파일의 이름을 지정하고, `HintPath` 메타데이터는 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-242">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="d7086-243">restore 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-243">Restore properties</span></span>

<span data-ttu-id="d7086-244">참조된 패키지를 복원하면 패키지의 직접 종속성과 해당 종속성의 종속성이 모두 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-244">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="d7086-245">`RestorePackagesPath` 및 `RestoreIgnoreFailedSources`와 같은 속성을 지정하여 패키지 복원을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7086-245">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="d7086-246">이러한 속성 및 다른 속성에 대한 자세한 내용은 [복원 대상](/nuget/reference/msbuild-targets#restore-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7086-246">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="d7086-247">참조</span><span class="sxs-lookup"><span data-stu-id="d7086-247">See also</span></span>

- [<span data-ttu-id="d7086-248">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="d7086-248">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="d7086-249">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-249">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="d7086-250">NuGet 압축의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-250">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="d7086-251">NuGet 복원의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="d7086-251">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="d7086-252">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d7086-252">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
