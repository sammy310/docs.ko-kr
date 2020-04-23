---
title: Microsoft.NET.Sdk의 MSBuild 속성
description: .NET Core SDK가 이해하는 MSBuild 속성에 대한 참조입니다.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386659"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="1be27-103">.NET Core SDK 프로젝트의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="1be27-104">이 페이지에서는 .NET Core 프로젝트를 구성하기 위한 MSBuild 속성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="1be27-105">이 페이지는 진행 중인 작업이며 .NET Core SDK의 일부 유용한 MSBuild 속성을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="1be27-106">일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="1be27-107">프레임워크 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-107">Framework properties</span></span>

- [<span data-ttu-id="1be27-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="1be27-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="1be27-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="1be27-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="1be27-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="1be27-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="1be27-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="1be27-111">TargetFramework</span></span>

<span data-ttu-id="1be27-112">`TargetFramework` 속성은 [메타패키지](../packages.md#metapackages)를 암시적으로 참조하는 앱의 대상 프레임워크 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="1be27-113">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="1be27-114">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="1be27-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="1be27-115">TargetFrameworks</span></span>

<span data-ttu-id="1be27-116">앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="1be27-117">유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="1be27-118">`TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="1be27-119">자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="1be27-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="1be27-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="1be27-121">이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="1be27-122">`netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="1be27-123">[메타패키지](../packages.md#metapackages) 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="1be27-124">다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="1be27-125">속성 게시</span><span class="sxs-lookup"><span data-stu-id="1be27-125">Publish properties</span></span>

- [<span data-ttu-id="1be27-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="1be27-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="1be27-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1be27-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="1be27-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="1be27-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="1be27-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="1be27-129">RuntimeIdentifier</span></span>

<span data-ttu-id="1be27-130">`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="1be27-131">RID를 통해 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="1be27-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1be27-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="1be27-133">`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="1be27-134">여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="1be27-135">`RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="1be27-136">단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="1be27-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="1be27-137">UseAppHost</span></span>

<span data-ttu-id="1be27-138">`UseAppHost` 속성은 .NET Core SDK 2.1.400 버전에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="1be27-139">배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="1be27-140">자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="1be27-141">.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="1be27-142">`UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="1be27-143">배포에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="1be27-144">컴파일 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="1be27-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="1be27-145">LangVersion</span></span>

<span data-ttu-id="1be27-146">`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="1be27-147">예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="1be27-148">자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="1be27-149">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="1be27-149">NuGet packages</span></span>

- [<span data-ttu-id="1be27-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="1be27-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="1be27-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="1be27-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="1be27-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="1be27-152">PackageReference</span></span>

<span data-ttu-id="1be27-153">`PackageReference` 항목을 사용하여 NuGet 종속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="1be27-154">예를 들어 [메타패키지](../packages.md#metapackages) 대신 단일 패키지를 참조하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="1be27-155">`Include` 특성은 패키지 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="1be27-156">다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="1be27-157">자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="1be27-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="1be27-158">AssetTargetFallback</span></span>

<span data-ttu-id="1be27-159">`AssetTargetFallback` 속성을 사용하여 프로젝트에서 참조하는 프로젝트 및 프로젝트에서 사용하는 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="1be27-160">예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="1be27-161">참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="1be27-162">`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-framework-versions)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="1be27-163">압축 및 복원 대상</span><span class="sxs-lookup"><span data-stu-id="1be27-163">Pack and restore targets</span></span>

<span data-ttu-id="1be27-164">MSBuild 15.1에는 빌드의 일부로 NuGet 패키지를 만들고 복원하기 위한 `pack` 및 `restore` 대상이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1be27-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="1be27-165">`PackageTargetFallback`을 포함하여 해당 대상의 MSBuild 속성에 대한 내용은 [MSBuild 대상으로서의 NuGet 압축 및 복원](/nuget/reference/msbuild-targets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be27-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="1be27-166">참조</span><span class="sxs-lookup"><span data-stu-id="1be27-166">See also</span></span>

- [<span data-ttu-id="1be27-167">MSBuild 스키마 참조</span><span class="sxs-lookup"><span data-stu-id="1be27-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="1be27-168">일반 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="1be27-169">NuGet 압축의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="1be27-170">NuGet 복원의 MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="1be27-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="1be27-171">빌드 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1be27-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
