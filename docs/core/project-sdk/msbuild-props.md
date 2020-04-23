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
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>.NET Core SDK 프로젝트의 MSBuild 속성

이 페이지에서는 .NET Core 프로젝트를 구성하기 위한 MSBuild 속성을 설명합니다.

> [!NOTE]
> 이 페이지는 진행 중인 작업이며 .NET Core SDK의 일부 유용한 MSBuild 속성을 나열하지 않습니다. 일반적인 MSBuild 속성의 목록을 보려면 [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.

## <a name="framework-properties"></a>프레임워크 속성

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

`TargetFramework` 속성은 [메타패키지](../packages.md#metapackages)를 암시적으로 참조하는 앱의 대상 프레임워크 버전을 지정합니다. 유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.

### <a name="targetframeworks"></a>TargetFrameworks

앱의 대상 플랫폼을 여러 개 지정하려면 `TargetFrameworks` 속성을 사용합니다. 유효한 대상 프레임워크 모니커의 목록을 보려면 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md#supported-target-framework-versions)를 참조하세요.

> [!NOTE]
> `TargetFramework`(단수형)이 지정되면 이 속성은 무시됩니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

자세한 내용은 [SDK 스타일 프로젝트의 대상 프레임워크](../../standard/frameworks.md)를 참조하세요.

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> 이 속성은 `netstandard1.x`를 사용하는 프로젝트에만 적용됩니다. `netstandard2.x`를 사용하는 프로젝트에는 적용되지 않습니다.

[메타패키지](../packages.md#metapackages) 버전보다 낮은 프레임워크 버전을 지정하려면 `NetStandardImplicitPackageVersion` 속성을 사용합니다. 다음 예제의 프로젝트 파일은 `netstandard1.3`을 대상으로 하지만 `NETStandard.Library`의 1.6.0 버전을 사용합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a>속성 게시

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

`RuntimeIdentifier` 속성을 사용하여 프로젝트의 단일 [RID(런타임 식별자)](../rid-catalog.md)를 지정할 수 있습니다. RID를 통해 자체 포함 배포를 게시할 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

`RuntimeIdentifiers` 속성을 사용하여 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../rid-catalog.md) 목록을 지정할 수 있습니다. 여러 런타임에 게시해야 하는 경우 이 속성을 사용합니다. `RuntimeIdentifiers`는 복원 시간에 올바른 자산이 그래프에 있는지 확인하는 데 사용됩니다.

> [!TIP]
> 단일 런타임만 필요한 경우에는 `RuntimeIdentifier`(단수형)를 사용하면 빌드 속도가 더 빨라집니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

`UseAppHost` 속성은 .NET Core SDK 2.1.400 버전에서 도입되었습니다. 배포용으로 네이티브 실행 파일을 만들지 여부를 제어합니다. 자체 포함 배포의 경우 네이티브 실행 파일이 필요합니다.

.NET Core 3.0 이상 버전에서는 프레임워크 종속 실행 파일이 기본적으로 생성됩니다. `UseAppHost` 속성을 `false`로 설정하여 실행 파일 생성을 사용하지 않도록 설정합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

배포에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.

## <a name="compile-properties"></a>컴파일 속성

### <a name="langversion"></a>LangVersion

`LangVersion` 속성을 사용하여 특정 프로그래밍 언어 버전을 지정할 수 있습니다. 예를 들어 C# 미리 보기 기능에 액세스하려면 `LangVersion`을 `preview`로 설정합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

자세한 내용은 [C# 언어 버전 관리](../../csharp/language-reference/configure-language-version.md#override-a-default)를 참조하세요.

## <a name="nuget-packages"></a>NuGet 패키지

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

`PackageReference` 항목을 사용하여 NuGet 종속성을 지정할 수 있습니다. 예를 들어 [메타패키지](../packages.md#metapackages) 대신 단일 패키지를 참조하려고 할 수 있습니다. `Include` 특성은 패키지 ID를 지정합니다. 다음 예제의 프로젝트 파일 코드 조각은 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 패키지를 참조합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

자세한 내용은 [프로젝트 파일의 패키지 참조](/nuget/consume-packages/package-references-in-project-files)를 참조하세요.

### <a name="assettargetfallback"></a>AssetTargetFallback

`AssetTargetFallback` 속성을 사용하여 프로젝트에서 참조하는 프로젝트 및 프로젝트에서 사용하는 NuGet 패키지에 대해 호환되는 추가 프레임워크 버전을 지정할 수 있습니다. 예를 들어 `PackageReference`를 사용하여 패키지 종속성을 지정하지만 해당 패키지에 프로젝트의 `TargetFramework`와 호환되는 자산이 포함되지 않은 경우 `AssetTargetFallback` 속성이 작동합니다. 참조된 패키지의 호환성은 `AssetTargetFallback`에 지정된 각 대상 프레임워크를 사용하여 다시 확인됩니다.

`AssetTargetFallback` 속성을 하나 이상의 [대상 프레임워크 버전](../../standard/frameworks.md#supported-target-framework-versions)으로 설정할 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>압축 및 복원 대상

MSBuild 15.1에는 빌드의 일부로 NuGet 패키지를 만들고 복원하기 위한 `pack` 및 `restore` 대상이 도입되었습니다. `PackageTargetFallback`을 포함하여 해당 대상의 MSBuild 속성에 대한 내용은 [MSBuild 대상으로서의 NuGet 압축 및 복원](/nuget/reference/msbuild-targets)을 참조하세요.

## <a name="see-also"></a>참조

- [MSBuild 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [일반 MSBuild 속성](/visualstudio/msbuild/common-msbuild-project-properties)
- [NuGet 압축의 MSBuild 속성](/nuget/reference/msbuild-targets#pack-target)
- [NuGet 복원의 MSBuild 속성](/nuget/reference/msbuild-targets#restore-properties)
- [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build)
