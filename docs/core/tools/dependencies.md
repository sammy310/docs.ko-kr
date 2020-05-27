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
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="45788-101">.NET Core 애플리케이션에서 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="45788-101">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="45788-102">이 문서에서는 프로젝트 파일을 편집하거나 CLI를 사용하여 종속성을 추가하고 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-102">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="45788-103">\<PackageReference> 요소</span><span class="sxs-lookup"><span data-stu-id="45788-103">The \<PackageReference> element</span></span>

<span data-ttu-id="45788-104">`<PackageReference>` 프로젝트 파일 요소는 다음과 같은 구조를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="45788-104">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="45788-105">`Include` 특성은 프로젝트에 추가할 패키지의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-105">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="45788-106">`Version` 특성은 가져올 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-106">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="45788-107">버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="45788-107">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="45788-108">project-file 구문에 대해 잘 모르면 [MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서에서 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45788-108">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="45788-109">특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같이 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-109">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="45788-110">앞에 나온 예제의 종속성은 해당 대상에 대해 빌드가 발생한 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-110">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="45788-111">조건에서 `$(TargetFramework)`는 프로젝트에 설정되는 MSBuild 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="45788-111">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="45788-112">대부분의 일반적인 .NET Core 애플리케이션에서는 이 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45788-112">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="45788-113">프로젝트 파일을 편집하여 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="45788-113">Add a dependency by editing the project file</span></span>

<span data-ttu-id="45788-114">종속성을 추가하려면 `<ItemGroup>` 요소 안에 `<PackageReference>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-114">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="45788-115">기존 `<ItemGroup>`에 추가하거나 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45788-115">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="45788-116">다음 예제에서는 `dotnet new console`로 만든 기본 콘솔 애플리케이션 프로젝트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-116">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="45788-117">CLI를 사용하여 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="45788-117">Add a dependency by using the CLI</span></span>

<span data-ttu-id="45788-118">종속성을 추가하려면 다음 예제와 같이 [dotnet add package](dotnet-add-package.md) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-118">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="45788-119">프로젝트 파일을 편집하여 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="45788-119">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="45788-120">종속성을 제거하려면 프로젝트 파일에서 `<PackageReference>` 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-120">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="45788-121">CLI를 사용하여 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="45788-121">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="45788-122">종속성을 제거하려면 다음 예제와 같이 [dotnet remove package](dotnet-remove-package.md) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="45788-122">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="45788-123">참조</span><span class="sxs-lookup"><span data-stu-id="45788-123">See also</span></span>

* [<span data-ttu-id="45788-124">프로젝트 파일의 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="45788-124">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="45788-125">[dotnet list package 명령](dotnet-list-package.md)</span><span class="sxs-lookup"><span data-stu-id="45788-125">[dotnet list package command](dotnet-list-package.md)</span></span>
