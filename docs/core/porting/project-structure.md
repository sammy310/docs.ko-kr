---
title: .NET Framework 및 .NET Core용 프로젝트 구성
description: .NET Framework 및 .NET Core에 대해 솔루션을 나란히 컴파일하려는 프로젝트 소유자를 위한 도움말입니다.
author: conniey
ms.date: 12/07/2018
ms.openlocfilehash: d71cc3102846c08f4e35831921b8cc4ca82f9e1b
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777327"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a><span data-ttu-id="9f5ae-103">.NET Framework 및 .NET Core를 둘 다 지원하도록 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="9f5ae-103">Organize your project to support both .NET Framework and .NET Core</span></span>

<span data-ttu-id="9f5ae-104">.NET Framework와 .NET Core 둘 다에 대해 나란히 컴파일되는 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-104">You can create a solution that compiles for both .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="9f5ae-105">이 문서에서는 이러한 목표를 달성하는 데 도움이 되는 여러 가지 프로젝트 구성 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-105">This article covers several project-organization options to help you achieve this goal.</span></span> <span data-ttu-id="9f5ae-106">.NET Core를 사용하여 프로젝트 레이아웃을 설정하는 방법을 결정할 때 고려해야 할 몇 가지 일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-106">Here are some typical scenarios to consider when you're deciding how to set up your project layout with .NET Core.</span></span> <span data-ttu-id="9f5ae-107">여기에서 모든 것을 다루지는 못할 수 있습니다. 프로젝트 요구에 따라 우선 순위를 정하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

- [<span data-ttu-id="9f5ae-108">**기존 프로젝트와 .NET Core 프로젝트를 단일 프로젝트로 결합**</span><span class="sxs-lookup"><span data-stu-id="9f5ae-108">**Combine existing projects and .NET Core projects into single projects**</span></span>](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  <span data-ttu-id="9f5ae-109">*좋은 점:*</span><span class="sxs-lookup"><span data-stu-id="9f5ae-109">*What this is good for:*</span></span>
  - <span data-ttu-id="9f5ae-110">각각 다른 .NET Framework 버전 또는 플랫폼을 대상으로 하는 여러 프로젝트가 아닌 단일 프로젝트를 컴파일함으로써 빌드 프로세스를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-110">Simplifies your build process by compiling a single project rather than multiple projects that each target a different .NET Framework version or platform.</span></span>
  - <span data-ttu-id="9f5ae-111">단일 프로젝트 파일을 관리해야 하므로 멀티 타기팅 프로젝트에 대한 소스 파일 관리를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-111">Simplifies source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="9f5ae-112">소스 파일을 추가 또는 제거할 때 대체 방법에서는 이를 다른 프로젝트와 수동으로 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-112">When adding or removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  - <span data-ttu-id="9f5ae-113">사용할 NuGet 패키지를 쉽게 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-113">Easily generate a NuGet package for consumption.</span></span>
  - <span data-ttu-id="9f5ae-114">컴파일러 지시문을 사용하여 라이브러리에서 특정 .NET Framework 버전에 대한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="9f5ae-115">*지원되지 않는 시나리오:*</span><span class="sxs-lookup"><span data-stu-id="9f5ae-115">*Unsupported scenarios:*</span></span>
  - <span data-ttu-id="9f5ae-116">개발자가 기존 프로젝트를 열려면 Visual Studio 2017 이상 버전을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-116">Requires developers to use Visual Studio 2017 or a later version to open existing projects.</span></span> <span data-ttu-id="9f5ae-117">Visual Studio의 이전 버전을 지원하려면 [프로젝트 파일을 서로 다른 폴더에 유지](#support-vs)하는 것이 더 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

- <a name="support-vs"></a><span data-ttu-id="9f5ae-118">[**기존 프로젝트와 새로운 .NET Core 프로젝트를 별도로 유지**](#keep-existing-projects-and-create-a-net-core-project)</span><span class="sxs-lookup"><span data-stu-id="9f5ae-118">[**Keep existing projects and new .NET Core projects separate**](#keep-existing-projects-and-create-a-net-core-project)</span></span>

  <span data-ttu-id="9f5ae-119">*좋은 점:*</span><span class="sxs-lookup"><span data-stu-id="9f5ae-119">*What this is good for:*</span></span>
  - <span data-ttu-id="9f5ae-120">Visual Studio 2017 이상 버전이 없는 개발자/참가자의 경우 기존 프로젝트에 대한 개발을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-120">Supports development on existing projects for developers and contributors who may not have Visual Studio 2017 or a later version.</span></span>
  - <span data-ttu-id="9f5ae-121">기존 프로젝트에서 코드 변동이 필요하지 않으므로 새 버그가 발생할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-121">Decreases the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="9f5ae-122">예제</span><span class="sxs-lookup"><span data-stu-id="9f5ae-122">Example</span></span>

<span data-ttu-id="9f5ae-123">아래 리포지토리를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-123">Consider the repository below:</span></span>

![기존 프로젝트](./media/project-structure/existing-project-structure.png)

[<span data-ttu-id="9f5ae-125">**소스 코드**</span><span class="sxs-lookup"><span data-stu-id="9f5ae-125">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

<span data-ttu-id="9f5ae-126">아래에서는 기존 프로젝트의 제약 조건 및 복잡성에 따라 이 리포지토리에 대한 .NET Core 지원을 추가하는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="9f5ae-127">기존 프로젝트를 멀티 타기팅 .NET Core 프로젝트로 교체</span><span class="sxs-lookup"><span data-stu-id="9f5ae-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="9f5ae-128">기존 *\*.csproj* 파일을 제거하고 여러 프레임워크를 대상으로 하는 단일 *\*.csproj* 파일을 만들도록 리포지토리를 재구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="9f5ae-129">서로 다른 프레임워크에 대해 단일 프로젝트를 컴파일할 수 있으므로 이는 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-129">This is a great option, because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="9f5ae-130">대상 프레임워크별로 서로 다른 컴파일 옵션 및 종속성을 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

![여러 프레임워크를 대상으로 하는 csproj 만들기](./media/project-structure/multi-targeted-project.png)

[<span data-ttu-id="9f5ae-132">**소스 코드**</span><span class="sxs-lookup"><span data-stu-id="9f5ae-132">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

<span data-ttu-id="9f5ae-133">주목할 변경 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-133">Changes to note are:</span></span>

- <span data-ttu-id="9f5ae-134">*packages.config* 및 *\*.csproj*가 새로운 [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj)로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj).</span></span> <span data-ttu-id="9f5ae-135">NuGet 패키지가 `<PackageReference> ItemGroup`을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="9f5ae-136">기존 프로젝트를 유지하고 .NET Core 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9f5ae-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="9f5ae-137">이전 프레임워크를 대상으로 하는 기존 프로젝트가 있는 경우, 이러한 프로젝트는 그대로 두고 이후 프레임워크를 대상으로 하는 .NET Core를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

![다른 폴더에 기존 프로젝트가 있는 .NET Core 프로젝트](./media/project-structure/separate-projects-same-source.png)

[<span data-ttu-id="9f5ae-139">**소스 코드**</span><span class="sxs-lookup"><span data-stu-id="9f5ae-139">**Source Code**</span></span>](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

<span data-ttu-id="9f5ae-140">.NET Core와 기존 프로젝트가 별도의 폴더에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-140">The .NET Core and existing projects are kept in separate folders.</span></span> <span data-ttu-id="9f5ae-141">프로젝트를 별도의 폴더에 유지하면 Visual Studio 2017 이상 버전을 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-141">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017 or later versions.</span></span> <span data-ttu-id="9f5ae-142">이전 프로젝트만 여는 별도 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5ae-142">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f5ae-143">참조</span><span class="sxs-lookup"><span data-stu-id="9f5ae-143">See also</span></span>

- [<span data-ttu-id="9f5ae-144">.NET Core 이식 설명서</span><span class="sxs-lookup"><span data-stu-id="9f5ae-144">.NET Core porting documentation</span></span>](index.md)
