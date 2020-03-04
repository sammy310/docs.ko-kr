---
title: .NET Core에서 종속성 관리
description: .NET Core 애플리케이션의 프로젝트 종속성을 관리하는 방법을 설명합니다.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: 02/25/2020
ms.openlocfilehash: 367be7eb04d58bffc0846de1d035a5801e8d9376
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157247"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="1f2bf-103">.NET Core 애플리케이션에서 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="1f2bf-103">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="1f2bf-104">이 문서에서는 프로젝트 파일을 편집하거나 CLI를 사용하여 종속성을 추가하고 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-104">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="1f2bf-105">\<PackageReference> 요소</span><span class="sxs-lookup"><span data-stu-id="1f2bf-105">The \<PackageReference> element</span></span>

<span data-ttu-id="1f2bf-106">`<PackageReference>` 프로젝트 파일 요소는 다음과 같은 구조를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-106">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="1f2bf-107">`Include` 특성은 프로젝트에 추가할 패키지의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-107">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="1f2bf-108">`Version` 특성은 가져올 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-108">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="1f2bf-109">버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-109">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="1f2bf-110">project-file 구문에 대해 잘 모르면 [MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서에서 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-110">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="1f2bf-111">특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같이 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-111">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="1f2bf-112">앞에 나온 예제의 종속성은 해당 대상에 대해 빌드가 발생한 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-112">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="1f2bf-113">조건에서 `$(TargetFramework)`는 프로젝트에 설정되는 MSBuild 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-113">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="1f2bf-114">대부분의 일반적인 .NET Core 애플리케이션에서는 이 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-114">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="1f2bf-115">프로젝트 파일을 편집하여 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="1f2bf-115">Add a dependency by editing the project file</span></span>

<span data-ttu-id="1f2bf-116">종속성을 추가하려면 `<ItemGroup>` 요소 안에 `<PackageReference>` 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-116">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="1f2bf-117">기존 `<ItemGroup>`에 추가하거나 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-117">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="1f2bf-118">다음 예제에서는 `dotnet new console`로 만든 기본 콘솔 애플리케이션 프로젝트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-118">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

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

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="1f2bf-119">CLI를 사용하여 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="1f2bf-119">Add a dependency by using the CLI</span></span>

<span data-ttu-id="1f2bf-120">종속성을 추가하려면 다음 예제와 같이 [dotnet add package](dotnet-add-package.md) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-120">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="1f2bf-121">프로젝트 파일을 편집하여 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="1f2bf-121">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="1f2bf-122">종속성을 제거하려면 프로젝트 파일에서 `<PackageReference>` 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-122">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="1f2bf-123">CLI를 사용하여 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="1f2bf-123">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="1f2bf-124">종속성을 제거하려면 다음 예제와 같이 [dotnet remove package](dotnet-remove-package.md) 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f2bf-124">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="1f2bf-125">참조</span><span class="sxs-lookup"><span data-stu-id="1f2bf-125">See also</span></span>

* [<span data-ttu-id="1f2bf-126">프로젝트 파일의 NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="1f2bf-126">NuGet packages in project files</span></span>](../project-sdk/msbuild-props.md#nuget-packages)
* <span data-ttu-id="1f2bf-127">[dotnet list package 명령](dotnet-remove-package.md)</span><span class="sxs-lookup"><span data-stu-id="1f2bf-127">[dotnet list package command](dotnet-remove-package.md)</span></span>
