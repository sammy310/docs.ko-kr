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
# <a name="netsdk1080-packagereference-to-microsoftaspnetcoreapp-is-not-necessary"></a><span data-ttu-id="f51c2-103">NETSDK1080: Microsoft.AspNetCore.App에 대한 PackageReference가 필요하지 않음</span><span class="sxs-lookup"><span data-stu-id="f51c2-103">NETSDK1080: PackageReference to Microsoft.AspNetCore.App is not necessary</span></span>

<span data-ttu-id="f51c2-104">NETSDK1080은 프로젝트 파일에 있는 `Microsoft.AspNetCore.App`의 `PackageReference` 요소가 필요하지 않음을 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-104">NETSDK1080 warns you that the `PackageReference` element for `Microsoft.AspNetCore.App` in your project file is not necessary.</span></span> <span data-ttu-id="f51c2-105">전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-105">The full error message is similar to the following example:</span></span>

> <span data-ttu-id="f51c2-106">경고 NETSDK1080: .NET Core 3.0 이상을 대상으로 하는 경우 Microsoft.AspNetCore.App에 대한 PackageReference가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-106">warning NETSDK1080: A PackageReference to Microsoft.AspNetCore.App is not necessary when targeting .NET Core 3.0 or higher.</span></span> <span data-ttu-id="f51c2-107">Microsoft.NET.Sdk.Web이 사용되는 경우 공유 프레임워크가 자동으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-107">If Microsoft.NET.Sdk.Web is used, the shared framework will be referenced automatically.</span></span> <span data-ttu-id="f51c2-108">그러지 않으면 PackageReference를 FrameworkReference로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-108">Otherwise, the PackageReference should be replaced with a FrameworkReference.</span></span>

<span data-ttu-id="f51c2-109">위 오류는 일반적으로 프로젝트 파일에 `PackageReference` 항목이 필요했던 이전 버전에서 .NET Core 3.0 이상으로 프로젝트를 업그레이드한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-109">This error typically occurs after you've upgraded a project to .NET Core 3.0 or later, from an earlier version that required `PackageReference` entries in the project file.</span></span>

## <a name="aspnet-core-project-files"></a><span data-ttu-id="f51c2-110">ASP.NET Core 프로젝트 파일</span><span class="sxs-lookup"><span data-stu-id="f51c2-110">ASP.NET Core project files</span></span>

<span data-ttu-id="f51c2-111">예를 들어, 원래 프로젝트 파일은 다음 예제와 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-111">For example, your original project file might look like this example:</span></span>

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

<span data-ttu-id="f51c2-112">.NET Core 3.1로 업데이트한 후 동일한 프로젝트의 프로젝트 파일은 다음 예제와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-112">After updating to .NET Core 3.1 the project file for the same project should look like the following example:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f51c2-113">이와 같이 변경합니다. 특히, `PackageReference` 요소를 삭제하여 경고를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-113">Make these changes, in particular delete the `PackageReference` element, to eliminate the warning.</span></span> <span data-ttu-id="f51c2-114">자세한 내용은 [사용되지 않는 패키지 참조 제거](/aspnet/core/migration/22-to-30#remove-obsolete-package-references)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f51c2-114">For more information, see [Remove obsolete package references](/aspnet/core/migration/22-to-30#remove-obsolete-package-references).</span></span>

## <a name="class-library-project"></a><span data-ttu-id="f51c2-115">클래스 라이브러리 프로젝트</span><span class="sxs-lookup"><span data-stu-id="f51c2-115">Class library project</span></span>

<span data-ttu-id="f51c2-116">ASP.NET Core API를 사용하는 클래스 라이브러리 프로젝트에서 다음 예제와 같이 `PackageReference`를 `FrameworkReference`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f51c2-116">In a class library project that uses ASP.NET Core APIs, replace the `PackageReference` with a `FrameworkReference`, as shown in the following example:</span></span>

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

<span data-ttu-id="f51c2-117">자세한 내용은 [클래스 라이브러리에서 ASP.NET Core API 사용](/aspnet/core/fundamentals/target-aspnetcore)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f51c2-117">For more information, see [Use ASP.NET Core APIs in a class library](/aspnet/core/fundamentals/target-aspnetcore).</span></span>
