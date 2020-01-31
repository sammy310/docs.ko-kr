---
title: 종속성 및 .NET 라이브러리
description: .NET 라이브러리에서 NuGet 종속성을 관리하는 모범 사례 권장 사항입니다.
ms.date: 10/02/2018
ms.openlocfilehash: 6a260b54c45a0cd231059ab3bc6f2707ef7fb20e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731483"
---
# <a name="dependencies"></a><span data-ttu-id="b1f4f-103">종속성</span><span class="sxs-lookup"><span data-stu-id="b1f4f-103">Dependencies</span></span>

<span data-ttu-id="b1f4f-104">.NET 라이브러리에 종속성을 추가하는 기본 방법은 NuGet 패키지를 참조하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-104">The primary way of adding dependencies to a .NET library is referencing NuGet packages.</span></span> <span data-ttu-id="b1f4f-105">NuGet 패키지 참조를 사용하면 이미 작성된 기능을 빠르게 다시 사용하고 활용할 수 있지만 .NET 개발자에게는 일반적인 마찰 소스이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-105">NuGet package references allow you to quickly reuse and leverage already written functionality, but they're a common source of friction for .NET developers.</span></span> <span data-ttu-id="b1f4f-106">종속성을 올바르게 관리하는 것은 다른 .NET 라이브러리의 변경 내용으로 인한 사용자 .NET 라이브러리의 중단이나 그 반대의 경우를 방지하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-106">Correctly managing dependencies is important to prevent changes in other .NET libraries from breaking your .NET library, and vice versa!</span></span>

## <a name="diamond-dependencies"></a><span data-ttu-id="b1f4f-107">다이아몬드 종속성</span><span class="sxs-lookup"><span data-stu-id="b1f4f-107">Diamond dependencies</span></span>

<span data-ttu-id="b1f4f-108">.NET 프로젝트의 종속성 트리에 여러 버전의 패키지가 포함되는 것이 일반적인 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-108">It's a common situation for a .NET project to have multiple versions of a package in its dependency tree.</span></span> <span data-ttu-id="b1f4f-109">예를 들어 앱이 두 개의 NuGet 패키지에 종속되어 있고, 각 패키지는 동일한 패키지의 서로 다른 버전에 종속되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-109">For example, an app depends on two NuGet packages, each of which depends on different versions of the same package.</span></span> <span data-ttu-id="b1f4f-110">이제 앱의 종속성 그래프에 다이아몬드 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-110">A diamond dependency now exists in the app's dependency graph.</span></span>

<span data-ttu-id="b1f4f-111">![다이아몬드 종속성](./media/dependencies/diamond-dependency.png "다이아몬드 종속성")</span><span class="sxs-lookup"><span data-stu-id="b1f4f-111">![Diamond dependency](./media/dependencies/diamond-dependency.png "Diamond dependency")</span></span>

<span data-ttu-id="b1f4f-112">빌드 시 NuGet은 종속성의 종속성을 포함하여 프로젝트가 종속된 모든 패키지를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-112">At build time, NuGet analyzes all the packages that a project depends on, including the dependencies of dependencies.</span></span> <span data-ttu-id="b1f4f-113">패키지의 여러 버전이 검색되면 규칙을 평가하여 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-113">When multiple versions of a package are detected, rules are evaluated to pick one.</span></span> <span data-ttu-id="b1f4f-114">.NET에서 동일한 애플리케이션에 있는 어셈블리의 병렬 버전을 실행하면 문제가 발생하기 때문에 패키지를 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-114">Unifying packages is necessary because running side-by-side versions of an assembly in the same application is problematic in .NET.</span></span>

<span data-ttu-id="b1f4f-115">대부분의 다이아몬드 종속성은 쉽게 확인되지만 다음과 같은 특정 상황에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-115">Most diamond dependencies are easily resolved; however, they can create issues in certain circumstances:</span></span>

1. <span data-ttu-id="b1f4f-116">**NuGet 패키지 참조가 충돌**하는 경우 패키지 복원 중에 버전이 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-116">**Conflicting NuGet package references** prevent a version from being resolved during package restore.</span></span>
2. <span data-ttu-id="b1f4f-117">**버전 간에 호환성이 손상되는 변경**이 있는 경우 런타임 시 버그와 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-117">**Breaking changes between the versions** cause bugs and exceptions at runtime.</span></span>
3. <span data-ttu-id="b1f4f-118">**패키지 어셈블리에 강력한 이름이 지정**되었고, 어셈블리 버전이 변경되었으며, 앱이 .NET Framework에서 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-118">**The package assembly is strong named**, the assembly version changed, and the app is running on the .NET Framework.</span></span> <span data-ttu-id="b1f4f-119">어셈블리 바인딩 리디렉션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-119">Assembly binding redirects are required.</span></span>

<span data-ttu-id="b1f4f-120">사용자 고유의 패키지와 함께 사용할 패키지를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-120">It's not possible to know what packages will be used alongside your own.</span></span> <span data-ttu-id="b1f4f-121">다이아몬드 종속성으로 인한 라이브러리 중단 가능성을 줄이는 좋은 방법은 사용자가 종속되는 패키지 수를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-121">A good way to reduce the likelihood of a diamond dependency breaking your library is to minimize the number of packages you depend on.</span></span>

<span data-ttu-id="b1f4f-122">✔️ 사용자 .NET 라이브러리에서 불필요한 종속성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-122">✔️ DO review your .NET library for unnecessary dependencies.</span></span>

## <a name="nuget-dependency-version-ranges"></a><span data-ttu-id="b1f4f-123">NuGet 종속성 버전 범위</span><span class="sxs-lookup"><span data-stu-id="b1f4f-123">NuGet dependency version ranges</span></span>

<span data-ttu-id="b1f4f-124">패키지 참조는 허용하는 유효한 패키지 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-124">A package reference specifies the range of valid packages it allows.</span></span> <span data-ttu-id="b1f4f-125">일반적으로 프로젝트 파일의 패키지 참조 버전은 최소 버전이며 최댓값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-125">Typically, the package reference version in the project file is the minimum version and there's no maximum.</span></span>

```xml
<!-- Accepts any version 1.0 and above. -->
<PackageReference Include="ExamplePackage" Version="1.0" />
```

<span data-ttu-id="b1f4f-126">NuGet에서 종속성을 확인할 때 사용하는 규칙은 [복잡](/nuget/consume-packages/dependency-resolution)하지만 NuGet은 항상 적용 가능한 가장 낮은 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-126">The rules that NuGet uses when resolving dependencies are [complex](/nuget/consume-packages/dependency-resolution), but NuGet always looks for the lowest applicable version.</span></span> <span data-ttu-id="b1f4f-127">가장 낮은 버전에서 호환성 문제가 가장 적기 때문에 NuGet은 사용 가능한 가장 높은 버전보다 적용 가능한 가장 낮은 버전을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-127">NuGet prefers the lowest applicable version over using the highest available because the lowest will have the least compatibility issues.</span></span>

<span data-ttu-id="b1f4f-128">NuGet의 적용 가능한 가장 낮은 버전 규칙 때문에 최신 버전을 가져오지 않도록 패키지 참조에 상위 버전이나 정확한 범위를 배치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-128">Because of NuGet's lowest applicable version rule, it isn't necessary to place an upper version or exact range on package references to avoid getting the latest version.</span></span> <span data-ttu-id="b1f4f-129">NuGet이 이미 가장 낮고, 가장 호환되는 버전을 찾으려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-129">NuGet already tries to find the lowest, most compatible version for you.</span></span>

```xml
<!-- Accepts 1.0 up to 1.x, but not 2.0 and higher. -->
<PackageReference Include="ExamplePackage" Version="[1.0,2.0)" />

<!-- Accepts exactly 1.0. -->
<PackageReference Include="ExamplePackage" Version="[1.0]" />
```

<span data-ttu-id="b1f4f-130">충돌이 있을 경우 상위 버전 제한으로 인해 NuGet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-130">Upper version limits will cause NuGet to fail if there's a conflict.</span></span> <span data-ttu-id="b1f4f-131">예를 들어 한 라이브러리는 정확히 1.0을 허용하는 반면, 다른 라이브러리에는 2.0 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-131">For example, one library accepts exactly 1.0 while another library requires 2.0 or above.</span></span> <span data-ttu-id="b1f4f-132">버전 2.0에서 호환성이 손상되는 변경이 도입되었을 수도 있지만, 엄격한 버전 종속성 또는 상한 버전 종속성이 적용되어 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-132">While breaking changes may have been introduced in version 2.0, a strict or upper limit version dependency guarantees an error.</span></span>

<span data-ttu-id="b1f4f-133">![다이아몬드 종속성 충돌](./media/dependencies/diamond-dependency-conflict.png "다이아몬드 종속성 충돌")</span><span class="sxs-lookup"><span data-stu-id="b1f4f-133">![Diamond dependency conflict](./media/dependencies/diamond-dependency-conflict.png "Diamond dependency conflict")</span></span>

<span data-ttu-id="b1f4f-134">❌ 최소 버전이 없는 NuGet 패키지 참조를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-134">❌ DO NOT have NuGet package references with no minimum version.</span></span>

<span data-ttu-id="b1f4f-135">❌ 정확한 버전을 요구하는 NuGet 패키지 참조는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-135">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="b1f4f-136">❌ 버전 상한이 있는 NuGet 패키지 참조를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-136">❌ AVOID NuGet package references with a version upper limit.</span></span>

## <a name="nuget-shared-source-packages"></a><span data-ttu-id="b1f4f-137">NuGet 공유 소스 패키지</span><span class="sxs-lookup"><span data-stu-id="b1f4f-137">NuGet shared source packages</span></span>

<span data-ttu-id="b1f4f-138">외부 NuGet 패키지 종속성을 줄이는 한 가지 방법은 공유 소스 패키지를 참조하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-138">One way to reduce external NuGet package dependencies is to reference shared source packages.</span></span> <span data-ttu-id="b1f4f-139">공유 소스 패키지에는 참조 시 프로젝트에 포함되는 [소스 코드 파일](/nuget/reference/nuspec#including-content-files)이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-139">A shared source package contains [source code files](/nuget/reference/nuspec#including-content-files) that are included in a project when referenced.</span></span> <span data-ttu-id="b1f4f-140">프로젝트의 나머지 부분과 함께 컴파일되는 소스 코드 파일만 포함하기 때문에 외부 종속성 및 충돌 가능성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-140">Because you're just including source code files that are compiled with the rest of your project, there's no external dependency and chance of conflict.</span></span>

<span data-ttu-id="b1f4f-141">공유 소스 패키지는 작은 기능 집합을 포함하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-141">Shared source packages are great for including small pieces of functionality.</span></span> <span data-ttu-id="b1f4f-142">HTTP 호출을 수행하기 위한 도우미 메서드의 공유 소스 패키지를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-142">For example, a shared source package of helper methods for making HTTP calls.</span></span>

<span data-ttu-id="b1f4f-143">![공유 소스 패키지](./media/dependencies/shared-source-package.png "공유 소스 패키지")</span><span class="sxs-lookup"><span data-stu-id="b1f4f-143">![Shared source package](./media/dependencies/shared-source-package.png "Shared source package")</span></span>

```xml
<PackageReference Include="Microsoft.Extensions.Buffers.Testing.Sources" PrivateAssets="All" Version="1.0" />
```

<span data-ttu-id="b1f4f-144">![공유 소스 프로젝트](./media/dependencies/shared-source-project.png "공유 소스 프로젝트")</span><span class="sxs-lookup"><span data-stu-id="b1f4f-144">![Shared source project](./media/dependencies/shared-source-project.png "Shared source project")</span></span>

<span data-ttu-id="b1f4f-145">공유 소스 패키지에는 몇 가지 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-145">Shared source packages have some limitations.</span></span> <span data-ttu-id="b1f4f-146">`PackageReference`에서만 참조할 수 있으므로, 이전 `packages.config` 프로젝트는 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-146">They can only be referenced by `PackageReference`, so older `packages.config` projects are excluded.</span></span> <span data-ttu-id="b1f4f-147">또한 공유 소스 패키지는 동일한 언어 형식의 프로젝트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-147">Also shared source packages are only usable by projects with the same language type.</span></span> <span data-ttu-id="b1f4f-148">이러한 제한 사항 때문에 공유 소스 패키지는 오픈 소스 프로젝트 내에서 기능을 공유하는 데 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-148">Because of these limitations shared source packages are best used to share functionality within an open-source project.</span></span>

<span data-ttu-id="b1f4f-149">✔️ 작은 내부 기능 집합을 위해 공유 소스 패키지를 참조하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-149">✔️ CONSIDER referencing shared source packages for small, internal pieces of functionality.</span></span>

<span data-ttu-id="b1f4f-150">✔️ 작은 내부 기능 집합을 제공하는 경우 사용자 패키지를 공유 소스 패키지로 설정하는 것을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-150">✔️ CONSIDER making your package a shared source package if it provides small, internal pieces of functionality.</span></span>

<span data-ttu-id="b1f4f-151">✔️ `PrivateAssets="All"`을 사용하여 공유 소스 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-151">✔️ DO reference shared source packages with `PrivateAssets="All"`.</span></span>

> <span data-ttu-id="b1f4f-152">이 설정은 개발할 때만 패키지를 사용하고 공용 종속성으로 노출하지 않도록 NuGet에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-152">This setting tells NuGet the package is only to be used at development time and shouldn't be exposed as a public dependency.</span></span>

<span data-ttu-id="b1f4f-153">❌ 공용 API에 공유 소스 패키지 형식을 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-153">❌ DO NOT have shared source package types in your public API.</span></span>

> <span data-ttu-id="b1f4f-154">공유 소스 형식은 참조 어셈블리로 컴파일되며 어셈블리 경계를 넘어 교환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-154">Shared source types are compiled into the referencing assembly and can't be exchanged across assembly boundaries.</span></span> <span data-ttu-id="b1f4f-155">예를 들어 한 프로젝트에 있는 공유 소스 `IRepository` 형식은 다른 프로젝트에 있는 동일한 공유 소스 `IRepository`와 별개의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-155">For example, a shared-source `IRepository` type in one project is a separate type from the same shared-source `IRepository` in another project.</span></span> <span data-ttu-id="b1f4f-156">공유 소스 패키지의 형식에 `internal` 가시성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-156">Types in shared source packages should have an `internal` visibility.</span></span>

<span data-ttu-id="b1f4f-157">❌ 공유 소스 패키지를 NuGet.org에 게시하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-157">❌ DO NOT publish shared source packages to NuGet.org.</span></span>

> <span data-ttu-id="b1f4f-158">공유 소스 패키지에는 소스 코드가 들어 있으며 동일한 언어 형식의 프로젝트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-158">Shared source packages contain source code and can only be used by projects with the same language type.</span></span> <span data-ttu-id="b1f4f-159">예를 들어 C# 공유 소스 패키지는 F# 애플리케이션에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-159">For example, a C# shared source package cannot be used by an F# application.</span></span>
>
> <span data-ttu-id="b1f4f-160">공유 소스 패키지를 [로컬 피드 또는 MyGet](./publish-nuget-package.md)에 게시하여 프로젝트 내에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f4f-160">Publish shared source packages to a [local feed or MyGet](./publish-nuget-package.md) to consume them internally within your project.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1f4f-161">[이전](nuget.md)
>[다음](sourcelink.md)</span><span class="sxs-lookup"><span data-stu-id="b1f4f-161">[Previous](nuget.md)
[Next](sourcelink.md)</span></span>
