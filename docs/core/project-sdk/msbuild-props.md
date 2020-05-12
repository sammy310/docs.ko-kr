---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET Core SDK가 이해하는 MSBuild 속성에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 800ff59310d8437d7f770bf20a5bdf37714f8515
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795575"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="1bc42-103">.NET Core SDK 프로젝트의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="1bc42-104">이 페이지에서는 .NET Core 프로젝트를 구성하기 위한 MSBuild 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span> <span data-ttu-id="1bc42-105">각 속성에 대해 ‘메타데이터’를 속성의 자식 요소로 지정할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1bc42-105">You can specify *metadata* for each property as child elements of the property.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc42-106">이 페이지는 진행 중인 작업이며 .NET Core SDK의 일부 유용한 MSBuild 속성을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-106">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="1bc42-107">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="1bc42-108">프레임워크 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-108">Framework properties</span></span>

- [<span data-ttu-id="1bc42-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="1bc42-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="1bc42-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="1bc42-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="1bc42-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="1bc42-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="1bc42-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="1bc42-112">TargetFramework</span></span>

<span data-ttu-id="1bc42-113">`TargetFramework` 속성은 [메타패키지](../packages.md#metapackages)를 암시적으로 참조하는 앱의 대상 프레임워크 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-113">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="1bc42-114">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="1bc42-115">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="1bc42-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="1bc42-116">TargetFrameworks</span></span>

<span data-ttu-id="1bc42-117">앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="1bc42-118">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="1bc42-119">`TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="1bc42-120">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="1bc42-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="1bc42-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="1bc42-122">이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="1bc42-123">`netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="1bc42-124">[메타패키지](../packages.md#metapackages) 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="1bc42-125">다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="1bc42-126">패키지 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-126">Package properties</span></span>

<span data-ttu-id="1bc42-127">`PackageId`, `PackageVersion`, `PackageIcon`, `Title`, `Description`과 같은 속성을 지정하여 프로젝트에서 생성되는 패키지를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-127">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="1bc42-128">이러한 속성 및 다른 속성에 대한 자세한 내용은 [팩 대상](/nuget/reference/msbuild-targets#pack-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-128">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties"></a><span data-ttu-id="1bc42-129">속성 게시</span><span class="sxs-lookup"><span data-stu-id="1bc42-129">Publish properties</span></span>

- [<span data-ttu-id="1bc42-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="1bc42-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="1bc42-131">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1bc42-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="1bc42-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="1bc42-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="1bc42-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="1bc42-133">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="1bc42-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="1bc42-134">RuntimeIdentifier</span></span>

<span data-ttu-id="1bc42-135">`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-135">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="1bc42-136">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-136">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="1bc42-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1bc42-137">RuntimeIdentifiers</span></span>

<span data-ttu-id="1bc42-138">`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-138">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="1bc42-139">여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-139">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="1bc42-140">`RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-140">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="1bc42-141">단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-141">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="1bc42-142">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="1bc42-142">TrimmerRootAssembly</span></span>

<span data-ttu-id="1bc42-143">`TrimmerRootAssembly` 항목을 사용하면 [‘트리밍’](../deploying/trim-self-contained.md)에서 어셈블리를 제외할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1bc42-143">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="1bc42-144">트리밍은 패키지된 애플리케이션에서 런타임의 사용되지 않은 부분을 제거하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-144">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="1bc42-145">일부 경우에는 트리밍이 필요한 참조를 잘못 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-145">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="1bc42-146">다음 XML은 트리밍에서 `System.Security` 어셈블리를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-146">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="1bc42-147">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="1bc42-147">UseAppHost</span></span>

<span data-ttu-id="1bc42-148">`UseAppHost` 속성은 .NET Core SDK 2.1.400 버전에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-148">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="1bc42-149">배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-149">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="1bc42-150">자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-150">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="1bc42-151">.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-151">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="1bc42-152">`UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-152">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="1bc42-153">배포에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-153">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="1bc42-154">컴파일 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-154">Compile properties</span></span>

- [<span data-ttu-id="1bc42-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="1bc42-155">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="1bc42-156">LangVersion</span><span class="sxs-lookup"><span data-stu-id="1bc42-156">LangVersion</span></span>

<span data-ttu-id="1bc42-157">`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-157">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="1bc42-158">예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-158">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="1bc42-159">자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-159">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="1bc42-160">런타임 구성 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-160">Run-time configuration properties</span></span>

<span data-ttu-id="1bc42-161">앱의 프로젝트 파일에서 MSBuild 속성을 지정하여 몇 가지 런타임 동작을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-161">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="1bc42-162">런타임 동작을 구성하는 다른 방법에 관한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-162">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="1bc42-163">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-163">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="1bc42-164">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="1bc42-164">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="1bc42-165">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-165">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="1bc42-166">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-166">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="1bc42-167">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="1bc42-167">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="1bc42-168">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="1bc42-168">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="1bc42-169">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="1bc42-169">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="1bc42-170">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="1bc42-170">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="1bc42-171">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="1bc42-171">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="1bc42-172">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-172">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="1bc42-173">`ConcurrentGarbageCollection` 속성은 [백그라운드(동시) 가비지 수집](../../standard/garbage-collection/background-gc.md)이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-173">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="1bc42-174">백그라운드 가비지 수집을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-174">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="1bc42-175">자세한 내용은 [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-175">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="1bc42-176">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="1bc42-176">InvariantGlobalization</span></span>

<span data-ttu-id="1bc42-177">`InvariantGlobalization` 속성은 앱이 문화권별 데이터에 액세스할 수 없는 ‘세계화 고정’ 모드에서 실행되는지 여부를 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="1bc42-177">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="1bc42-178">세계화 고정 모드에서 실행하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-178">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="1bc42-179">자세한 내용은 [고정 모드](../run-time-config/globalization.md#invariant-mode)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-179">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="1bc42-180">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-180">RetainVMGarbageCollection</span></span>

<span data-ttu-id="1bc42-181">`RetainVMGarbageCollection` 속성은 삭제된 메모리 세그먼트를 나중에 사용하기 위해 대기 목록에 넣거나 릴리스하도록 가비지 수집기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-181">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="1bc42-182">값을 `true`로 설정하여 가비지 수집기가 대기 목록에 세그먼트를 넣도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-182">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="1bc42-183">자세한 내용은 [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-183">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="1bc42-184">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="1bc42-184">ServerGarbageCollection</span></span>

<span data-ttu-id="1bc42-185">`ServerGarbageCollection` 속성은 애플리케이션이 [워크스테이션 가비지 수집 또는 서버 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-185">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="1bc42-186">서버 가비지 수집을 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-186">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="1bc42-187">자세한 내용은 [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-187">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="1bc42-188">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="1bc42-188">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="1bc42-189">`ThreadPoolMaxThreads` 속성은 작업자 스레드 풀의 최대 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-189">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="1bc42-190">자세한 내용은 [최대 스레드](../run-time-config/threading.md#maximum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-190">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="1bc42-191">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="1bc42-191">ThreadPoolMinThreads</span></span>

<span data-ttu-id="1bc42-192">`ThreadPoolMinThreads` 속성은 작업자 스레드 풀의 최소 스레드 수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-192">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="1bc42-193">자세한 내용은 [최소 스레드](../run-time-config/threading.md#minimum-threads)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-193">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="1bc42-194">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="1bc42-194">TieredCompilation</span></span>

<span data-ttu-id="1bc42-195">`TieredCompilation` 속성은 JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-195">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="1bc42-196">계층화된 컴파일을 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-196">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="1bc42-197">자세한 내용은 [계층화된 컴파일](../run-time-config/compilation.md#tiered-compilation)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-197">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="1bc42-198">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="1bc42-198">TieredCompilationQuickJit</span></span>

<span data-ttu-id="1bc42-199">`TieredCompilationQuickJit` 속성은 JIT 컴파일러가 빠른 JIT를 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-199">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="1bc42-200">빠른 JIT를 사용하지 않으려면 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-200">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="1bc42-201">자세한 내용은 [빠른 JIT](../run-time-config/compilation.md#quick-jit)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-201">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="1bc42-202">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="1bc42-202">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="1bc42-203">`TieredCompilationQuickJitForLoops` 속성은 JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-203">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="1bc42-204">루프를 포함하는 메서드에서 빠른 JIT를 사용하려면 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-204">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="1bc42-205">자세한 내용은 [루프에 대한 빠른 JIT](../run-time-config/compilation.md#quick-jit-for-loops)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-205">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="1bc42-206">참조 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-206">Reference properties</span></span>

- [<span data-ttu-id="1bc42-207">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="1bc42-207">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="1bc42-208">PackageReference</span><span class="sxs-lookup"><span data-stu-id="1bc42-208">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="1bc42-209">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="1bc42-209">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="1bc42-210">참조</span><span class="sxs-lookup"><span data-stu-id="1bc42-210">Reference</span></span>](#reference)
- [<span data-ttu-id="1bc42-211">restore 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-211">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="1bc42-212">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="1bc42-212">AssetTargetFallback</span></span>

<span data-ttu-id="1bc42-213">`AssetTargetFallback` 속성을 사용하여 프로젝트 참조 및 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-213">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="1bc42-214">예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-214">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="1bc42-215">참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-215">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="1bc42-216">`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-framework-versions)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-216">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="1bc42-217">PackageReference</span><span class="sxs-lookup"><span data-stu-id="1bc42-217">PackageReference</span></span>

<span data-ttu-id="1bc42-218">`PackageReference`는 NuGet 패키지에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-218">The `PackageReference` defines a reference to a NuGet package.</span></span> <span data-ttu-id="1bc42-219">예를 들어 [메타패키지](../packages.md#metapackages) 대신 단일 패키지를 참조하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-219">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="1bc42-220">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-220">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="1bc42-221">`Version` 특성은 버전 또는 버전 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-221">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="1bc42-222">최소 버전, 최대 버전, 범위 또는 정확한 일치를 지정하는 방법에 대한 자세한 내용은 [버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-222">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="1bc42-223">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-223">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="1bc42-224">다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-224">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="1bc42-225">자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-225">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="1bc42-226">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="1bc42-226">ProjectReference</span></span>

<span data-ttu-id="1bc42-227">`ProjectReference` 항목은 다른 프로젝트에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-227">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="1bc42-228">참조된 프로젝트는 NuGet 패키지 종속성으로 추가됩니다. 즉, `PackageReference`와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-228">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="1bc42-229">`Include` 특성은 프로젝트의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-229">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="1bc42-230">또한 메타데이터 `IncludeAssets`, `ExcludeAssets`, `PrivateAssets`를 프로젝트 참조에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="1bc42-231">다음 예제의 프로젝트 파일 코드 조각은 `Project2`라는 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-231">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="1bc42-232">참고</span><span class="sxs-lookup"><span data-stu-id="1bc42-232">Reference</span></span>

<span data-ttu-id="1bc42-233">`Reference` 항목은 어셈블리 파일에 대한 참조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-233">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="1bc42-234">`Include` 특성은 파일의 이름을 지정하고, `HintPath` 자식 요소는 어셈블리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-234">The `Include` attribute specifies the name of the file, and the `HintPath` child element specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="1bc42-235">restore 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-235">Restore properties</span></span>

<span data-ttu-id="1bc42-236">참조된 패키지를 복원하면 패키지의 직접 종속성과 해당 종속성의 종속성이 모두 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-236">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="1bc42-237">`RestorePackagesPath` 및 `RestoreIgnoreFailedSources`와 같은 속성을 지정하여 패키지 복원을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bc42-237">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="1bc42-238">이러한 속성 및 다른 속성에 대한 자세한 내용은 [복원 대상](/nuget/reference/msbuild-targets#restore-target)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bc42-238">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="1bc42-239">참조</span><span class="sxs-lookup"><span data-stu-id="1bc42-239">See also</span></span>

- [<span data-ttu-id="1bc42-240">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="1bc42-240">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="1bc42-241">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-241">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="1bc42-242">NuGet 압축의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-242">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="1bc42-243">NuGet 복원의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1bc42-243">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="1bc42-244">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1bc42-244">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
