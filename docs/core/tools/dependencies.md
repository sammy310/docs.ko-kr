---
title: .NET Core 도구에서 종속성 관리
description: .NET Core 도구로 종속성을 관리하는 방법을 설명합니다.
ms.date: 03/06/2017
ms.openlocfilehash: 916daca0240c10dc63ca96048590a426bc51d450
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965622"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="6db5f-103">.NET Core SDK 1.0으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="6db5f-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="6db5f-104">.NET Core 프로젝트가 project.json에서 csproj 및 MSBuild로 전환하면서 상당한 투자가 발생했으며, 그 결과 종속성 추적을 허용하는 프로젝트 파일과 자산 통합이 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="6db5f-105">.NET Core 프로젝트의 경우 project.json의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="6db5f-106">NuGet 종속성을 추적하는 별도 JSON 또는 XML 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="6db5f-107">이 변경으로 `<PackageReference>`라는 csproj 구문에 대한 다른 *참조* 형식도 소개하였습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="6db5f-108">이 문서에서는 새 참조 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-108">This document describes the new reference type.</span></span> <span data-ttu-id="6db5f-109">또한 프로젝트에 대한 이 새 참조 형식을 사용하여 패키지 종속성을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="6db5f-110">새 \<PackageReference> 요소</span><span class="sxs-lookup"><span data-stu-id="6db5f-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="6db5f-111">`<PackageReference>`의 기본 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="6db5f-112">MSBuild에 익숙한 경우 이미 존재하는 다른 참조 형식에 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="6db5f-113">키는 프로젝트에 추가할 패키지 ID를 지정하는 `Include` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-113">The key is the `Include` statement, which specifies the package ID that you wish to add to the project.</span></span> <span data-ttu-id="6db5f-114">`<Version>` 자식 요소는 가져올 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="6db5f-115">버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="6db5f-116">project-file 구문에 대해 잘 알고 있지 않은 경우 자세한 내용은[MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db5f-116">If you're not familiar with the project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="6db5f-117">특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같이 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-117">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="6db5f-118">종속성은 지정된 대상에 대해 빌드가 발생한 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-118">The dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="6db5f-119">조건에서 `$(TargetFramework)`는 프로젝트에 설정되는 MSBuild 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-119">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="6db5f-120">가장 일반적인.NET Core 애플리케이션의 경우 이 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="6db5f-121">프로젝트에 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="6db5f-121">Add a dependency to the project</span></span>

<span data-ttu-id="6db5f-122">프로젝트에 종속성을 추가하는 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="6db5f-123">다음은 Json.NET 버전 `9.0.1`을 프로젝트에 추가하는 방법을 보여 주는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="6db5f-124">물론, 다른 NuGet 종속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="6db5f-125">프로젝트 파일에 둘 이상의 `<ItemGroup>` 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-125">Your project file has two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="6db5f-126">노드 중 하나에 이미 `<PackageReference>` 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-126">One of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="6db5f-127">이 노드에 새 종속성을 추가하거나 새로 만들 수 있습니다. 결과는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-127">You can add your new dependency to this node or create a new one; the result will be the same.</span></span>

<span data-ttu-id="6db5f-128">다음 예는 `dotnet new console`에 의해 삭제된 기본 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="6db5f-129">이는 간단한 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-129">This is a simple console application.</span></span> <span data-ttu-id="6db5f-130">프로젝트를 열면 이미 기존 `<PackageReference>`가 있는 `<ItemGroup>`을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="6db5f-131">여기에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="6db5f-132">그 다음 프로젝트를 저장하고 `dotnet restore` 명령을 실행하여 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="6db5f-133">전체 프로젝트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="6db5f-134">프로젝트에서 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="6db5f-134">Remove a dependency from the project</span></span>

<span data-ttu-id="6db5f-135">프로젝트 파일에서 종속성을 제거하는 작업은 프로젝트 파일에서 `<PackageReference>`를 단순히 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6db5f-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
