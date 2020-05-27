---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702843"
---
# <a name="manage-dependencies-in-net-core-applications"></a>.NET Core 애플리케이션에서 종속성 관리

이 문서에서는 프로젝트 파일을 편집하거나 CLI를 사용하여 종속성을 추가하고 제거하는 방법을 설명합니다.

## <a name="the-packagereference-element"></a>\<PackageReference> 요소

`<PackageReference>` 프로젝트 파일 요소는 다음과 같은 구조를 갖습니다.

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

`Include` 특성은 프로젝트에 추가할 패키지의 ID를 지정합니다. `Version` 특성은 가져올 버전을 지정합니다. 버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.

> [!NOTE]
> project-file 구문에 대해 잘 모르면 [MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서에서 자세한 내용을 참조하세요.

특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같이 조건을 사용합니다.

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

앞에 나온 예제의 종속성은 해당 대상에 대해 빌드가 발생한 경우에만 유효합니다. 조건에서 `$(TargetFramework)`는 프로젝트에 설정되는 MSBuild 속성입니다. 대부분의 일반적인 .NET Core 애플리케이션에서는 이 작업을 수행하지 않아도 됩니다.

## <a name="add-a-dependency-by-editing-the-project-file"></a>프로젝트 파일을 편집하여 종속성 추가

종속성을 추가하려면 `<ItemGroup>` 요소 안에 `<PackageReference>` 요소를 추가합니다. 기존 `<ItemGroup>`에 추가하거나 새로 만들 수 있습니다. 다음 예제에서는 `dotnet new console`로 만든 기본 콘솔 애플리케이션 프로젝트를 사용합니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a>CLI를 사용하여 종속성 추가

종속성을 추가하려면 다음 예제와 같이 [dotnet add package](dotnet-add-package.md) 명령을 실행합니다.

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>프로젝트 파일을 편집하여 종속성 제거

종속성을 제거하려면 프로젝트 파일에서 `<PackageReference>` 요소를 제거합니다.

## <a name="remove-a-dependency-by-using-the-cli"></a>CLI를 사용하여 종속성 제거

종속성을 제거하려면 다음 예제와 같이 [dotnet remove package](dotnet-remove-package.md) 명령을 실행합니다.

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>참조

* [프로젝트 파일의 패키지 참조](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [dotnet list package 명령](dotnet-list-package.md)
