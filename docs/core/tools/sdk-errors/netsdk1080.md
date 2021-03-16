---
title: 'NETSDK1080: Microsoft.AspNetCore.App에 대한 PackageReference가 필요하지 않음'
description: 프로젝트 파일에서 불필요한 항목에 관해 경고하는 .NET SDK 오류 NETSDK1080에 관해 알아봅니다.
ms.topic: error-reference
ms.date: 02/25/2021
f1_keywords:
- NETSDK1080
ms.openlocfilehash: ebf9484e4a358597a1177f95e92f68330180cd35
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206792"
---
# <a name="netsdk1080-packagereference-to-microsoftaspnetcoreapp-is-not-necessary"></a>NETSDK1080: Microsoft.AspNetCore.App에 대한 PackageReference가 필요하지 않음

NETSDK1080은 프로젝트 파일에 있는 `Microsoft.AspNetCore.App`의 `PackageReference` 요소가 필요하지 않음을 경고합니다. 전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.

> 경고 NETSDK1080: .NET Core 3.0 이상을 대상으로 하는 경우 Microsoft.AspNetCore.App에 대한 PackageReference가 필요하지 않습니다. Microsoft.NET.Sdk.Web이 사용되는 경우 공유 프레임워크가 자동으로 참조됩니다. 그러지 않으면 PackageReference를 FrameworkReference로 바꿔야 합니다.

위 오류는 일반적으로 프로젝트 파일에 `PackageReference` 항목이 필요했던 이전 버전에서 .NET Core 3.0 이상으로 프로젝트를 업그레이드한 후에 발생합니다.

## <a name="aspnet-core-project-files"></a>ASP.NET Core 프로젝트 파일

예를 들어, 원래 프로젝트 파일은 다음 예제와 같이 표시될 수 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp2.2</TargetFramework>
    <AspNetCoreHostingModel>InProcess</AspNetCoreHostingModel>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.App"/>
    <PackageReference Include="Microsoft.AspNetCore.Razor.Design" Version="2.2.0" PrivateAssets="All" />
  </ItemGroup>

</Project>
```

.NET Core 3.1로 업데이트한 후 동일한 프로젝트의 프로젝트 파일은 다음 예제와 같이 표시됩니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

</Project>
```

이와 같이 변경합니다. 특히, `PackageReference` 요소를 삭제하여 경고를 제거합니다. 자세한 내용은 [사용되지 않는 패키지 참조 제거](/aspnet/core/migration/22-to-30#remove-obsolete-package-references)를 참조하세요.

## <a name="class-library-project"></a>클래스 라이브러리 프로젝트

ASP.NET Core API를 사용하는 클래스 라이브러리 프로젝트에서 다음 예제와 같이 `PackageReference`를 `FrameworkReference`로 바꿉니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <FrameworkReference Include="Microsoft.AspNetCore.App" />
  </ItemGroup>

</Project>
```

자세한 내용은 [클래스 라이브러리에서 ASP.NET Core API 사용](/aspnet/core/fundamentals/target-aspnetcore)을 참조하세요.
