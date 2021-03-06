---
title: 마이그레이션할 프로젝트의 시퀀스 식별
description: 일반적으로 규모가 작은 앱은 일반적으로 한 번에 새 플랫폼으로 마이그레이션되지 않지만 몇 가지 작은 단계로 진행 됩니다. ASP.NET MVC 앱을 ASP.NET Core으로 마이그레이션하기 위한 단계를 계획 하는 방법에 대해 알아봅니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 452898da5839f8979a5e4f9ebf5d4c21b250e1fa
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401765"
---
# <a name="identify-sequence-of-projects-to-migrate"></a><span data-ttu-id="f81c1-104">마이그레이션할 프로젝트의 시퀀스 식별</span><span class="sxs-lookup"><span data-stu-id="f81c1-104">Identify sequence of projects to migrate</span></span>

<span data-ttu-id="f81c1-105">여러 프런트 엔드 앱을 포함 하는 솔루션의 경우 앱을 하나씩 마이그레이션하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-105">For solutions that involve multiple front-end apps, it's best to migrate the apps one by one.</span></span> <span data-ttu-id="f81c1-106">예를 들어, 관련 된 작업의 범위를 쉽게 식별할 수 있도록 프런트 엔드 앱과 해당 종속성을 하나만 포함 하는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-106">For example, create a solution that only includes one front-end app and its dependencies so you can easily identify the scope of work involved.</span></span> <span data-ttu-id="f81c1-107">솔루션은 간단 하며, 필요한 경우 여러 솔루션에 프로젝트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-107">Solutions are lightweight, and you can include projects in multiple solutions if needed.</span></span> <span data-ttu-id="f81c1-108">마이그레이션할 때 솔루션을 조직 도구로 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-108">Take advantage of solutions as an organizational tool when migrating.</span></span>

<span data-ttu-id="f81c1-109">ASP.NET 앱이 마이그레이션 되도록 확인 하 고 해당 종속 프로젝트 (솔루션에서 이상적 임)가 있는 것으로 확인 되 면 다음 단계는 프레임 워크 및 NuGet 종속성을 식별 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-109">Once you've identified the ASP.NET app to migrate and have its dependent projects located with it (ideally in a solution), the next step is to identify framework and NuGet dependencies.</span></span> <span data-ttu-id="f81c1-110">모든 종속성을 식별 하 고 가장 간단한 마이그레이션 방법은 "상향식" 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-110">Having identified all dependencies, the simplest migration approach is a "bottom up" approach.</span></span> <span data-ttu-id="f81c1-111">이 방법을 사용 하는 경우 가장 낮은 종속성 수준이 먼저 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-111">With this approach, the lowest level of dependencies is migrated first.</span></span> <span data-ttu-id="f81c1-112">그런 다음 종속성의 다음 수준이 마이그레이션된 후에 야 가장 남아 있는 것은 프런트 엔드 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-112">Then the next level of dependencies is migrated, until eventually the only thing left is the front-end app.</span></span> <span data-ttu-id="f81c1-113">그림 3-1에서는 앱을 구성 하는 예제 프로젝트 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-113">Figure 3-1 shows an example set of projects composing an app.</span></span> <span data-ttu-id="f81c1-114">하위 수준 클래스 라이브러리는 아래쪽에 있고 ASP.NET MVC 프로젝트는 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-114">The low-level class libraries are at the bottom, and the ASP.NET MVC project is at the top.</span></span>

![프로젝트 종속성](./media/Figure3-1.png)

<span data-ttu-id="f81c1-116">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="f81c1-116">**Figure 3-1.**</span></span> <span data-ttu-id="f81c1-117">프로젝트 종속성 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-117">Project dependencies graph.</span></span>

<span data-ttu-id="f81c1-118">ASP.NET MVC 5/Web API 2 프로젝트인 특정 프런트 엔드 앱을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-118">Choose a particular front-end app, an ASP.NET MVC 5 / Web API 2 project.</span></span> <span data-ttu-id="f81c1-119">솔루션에서 해당 종속성을 식별 하 고 전체 목록이 표시 될 때까지 해당 종속성을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-119">Identify its dependencies in the solution, and map out their dependencies until you have a complete list.</span></span> <span data-ttu-id="f81c1-120">그림 3-1에 표시 된 것과 같은 다이어그램은 프로젝트 종속성을 매핑할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-120">A diagram like the one shown in Figure 3-1 may be useful when mapping out project dependencies.</span></span> <span data-ttu-id="f81c1-121">Visual Studio는 사용 중인 버전에 따라 [솔루션에 대 한 종속성 다이어그램](/visualstudio/modeling/create-layer-diagrams-from-your-code)을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-121">Visual Studio can produce a [dependency diagram for your solution](/visualstudio/modeling/create-layer-diagrams-from-your-code), depending on which edition you're using.</span></span> <span data-ttu-id="f81c1-122">[.Net 이식성 분석기는](../../standard/analyzers/portability-analyzer.md) 종속성 다이어그램도 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-122">[The .NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) can also produce dependency diagrams.</span></span>

<span data-ttu-id="f81c1-123">그림 3-2에서는 [.Net 이식성 분석기 Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)에 대 한 설치 관리자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-123">Figure 3-2 shows the installer for the [.NET Portability Analyzer Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer):</span></span>

![.NET 이식성 분석기 확장 설치](./media/Figure3-2.png)

<span data-ttu-id="f81c1-125">**그림 3-2.**</span><span class="sxs-lookup"><span data-stu-id="f81c1-125">**Figure 3-2.**</span></span> <span data-ttu-id="f81c1-126">.NET 이식성 분석기 설치 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-126">.NET Portability Analyzer installer.</span></span>

<span data-ttu-id="f81c1-127">확장은 Visual Studio 2017 이상을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-127">The extension supports Visual Studio 2017 and later.</span></span> <span data-ttu-id="f81c1-128">일단 설치 되 면   >  그림 3-3에 표시 된 것 처럼 **이식성 분석기 설정** 분석 메뉴에서 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-128">Once installed, you configure it from the **Analyze** > **Portability Analyzer Settings** menu, as shown in Figure 3-3.</span></span>

![.NET 이식성 분석기 확장 구성](./media/Figure3-3.png)

<span data-ttu-id="f81c1-130">**그림 3-3.**</span><span class="sxs-lookup"><span data-stu-id="f81c1-130">**Figure 3-3.**</span></span> <span data-ttu-id="f81c1-131">.NET 이식성 분석기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-131">Configure the .NET Portability Analyzer.</span></span>

<span data-ttu-id="f81c1-132">분석기는 각 어셈블리에 대 한 자세한 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-132">The analyzer produces a detailed report for each assembly.</span></span> <span data-ttu-id="f81c1-133">보고서:</span><span class="sxs-lookup"><span data-stu-id="f81c1-133">The report:</span></span>

* <span data-ttu-id="f81c1-134">.NET Core 3.1 또는 .NET Standard 2.0과 같은 지정 된 대상 프레임 워크를 사용 하 여 각 프로젝트와 호환 되는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-134">Describes how compatible each project is with a given target framework, such as .NET Core 3.1 or .NET Standard 2.0.</span></span>
* <span data-ttu-id="f81c1-135">팀에서 특정 프로젝트를 특정 대상 프레임 워크로 이식 하는 데 필요한 노력을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-135">Helps teams assess the effort required to port a particular project to a particular target framework.</span></span>

<span data-ttu-id="f81c1-136">이 분석의 세부 정보는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-136">The details of this analysis are covered in the next section.</span></span>

<span data-ttu-id="f81c1-137">프로젝트와 해당 관계를 서로 매핑한 후에는 프로젝트를 마이그레이션할 순서를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-137">Once you've mapped out the projects and their relationships with one another, you're ready to determine the order in which you'll migrate the projects.</span></span> <span data-ttu-id="f81c1-138">종속성이 없는 프로젝트부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-138">Begin with projects that have no dependencies.</span></span> <span data-ttu-id="f81c1-139">그런 다음 이러한 프로젝트에 의존 하는 프로젝트에 대 한 트리를 원하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-139">Then, work your way up the tree to the projects that depend on these projects.</span></span>

<span data-ttu-id="f81c1-140">그림 3-1에 표시 된 예제에서는 다른 프로젝트에 종속 되지 않기 때문에 *유틸리티* 프로젝트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-140">In the example shown in Figure 3-1, you would start with the *Contoso.Utils* project, since it doesn't depend on any other projects.</span></span> <span data-ttu-id="f81c1-141">다음으로 *Contoso. 데이터* 는 "유틸리티"에만 종속 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-141">Next, *Contoso.Data* since it only depends on "Utils".</span></span> <span data-ttu-id="f81c1-142">그런 다음 "Businesslogic.dll" 라이브러리를 마이그레이션하고 마지막으로 프런트 엔드 ASP.NET "Web" 프로젝트를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-142">Then migrate the "BusinessLogic" library, and finally the front-end ASP.NET "Web" project.</span></span> <span data-ttu-id="f81c1-143">이 "상향식" 접근 방식은 모든 프로젝트가 마이그레이션된 후 하나의 단위로 마이그레이션될 수 있는 비교적 작고 잘 구성 된 앱에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-143">Following this "bottom up" approach works well for relatively small and well-factored apps that can be migrated as a unit once all of their projects have migrated.</span></span> <span data-ttu-id="f81c1-144">더 복잡 하거나 마이그레이션하는 데 더 많은 코드를 사용 하는 더 큰 앱은 더 많은 증분 전략을 고려해 야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-144">Larger apps with more complexity, or more code that will take longer to migrate, may need to consider more incremental strategies.</span></span>

## <a name="unit-tests"></a><span data-ttu-id="f81c1-145">단위 테스트</span><span class="sxs-lookup"><span data-stu-id="f81c1-145">Unit tests</span></span>

<span data-ttu-id="f81c1-146">이전 다이어그램에는 단위 테스트 프로젝트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-146">Missing from the previous diagrams are unit test projects.</span></span> <span data-ttu-id="f81c1-147">이식 중인 라이브러리의 기존 동작 중 일부를 포함 하는 테스트가 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-147">Hopefully there are tests covering at least some of the existing behavior of the libraries being ported.</span></span>

<span data-ttu-id="f81c1-148">단위 테스트가 있는 경우 해당 프로젝트를 먼저 변환 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-148">If you have unit tests, it's best to convert those projects first.</span></span> <span data-ttu-id="f81c1-149">작업 중인 프로젝트에서 변경 내용을 계속 테스트 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-149">You'll want to continue testing changes in the project you're working on.</span></span> <span data-ttu-id="f81c1-150">.NET Core로 이식 하는 것은 코드 베이스의 중요 한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-150">Remember that porting to .NET Core is a significant change to your codebase.</span></span>

<span data-ttu-id="f81c1-151">MSTest, xUnit 및 NUnit은 모두 .NET Core에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-151">MSTest, xUnit, and NUnit all work on .NET Core.</span></span> <span data-ttu-id="f81c1-152">현재 앱에 대 한 테스트가 없는 경우 시스템의 현재 동작을 확인 하는 몇 가지 특성화 테스트를 작성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-152">If you don't currently have tests for your app, consider building some characterization tests that verify the system's current behavior.</span></span> <span data-ttu-id="f81c1-153">마이그레이션을 완료 한 후에는 앱의 동작이 변경 되지 않은 상태로 유지 된다는 이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-153">The benefit is that once the migration is complete, you can confirm the app's behavior remains unchanged.</span></span>

## <a name="considerations-for-migrating-many-apps"></a><span data-ttu-id="f81c1-154">많은 앱 마이그레이션에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f81c1-154">Considerations for migrating many apps</span></span>

<span data-ttu-id="f81c1-155">일부 조직에는 서로 다른 여러 앱을 마이그레이션할 수 있으며, 각 조직에서 수동으로 마이그레이션하는 경우에는 너무 많은 리소스를 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-155">Some organizations will have many different apps to migrate, and migrating each one by hand may require too many resources to be tenable.</span></span> <span data-ttu-id="f81c1-156">이러한 경우에는 어떤 수준의 자동화를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-156">In these situations, some degree of automation is recommended.</span></span> <span data-ttu-id="f81c1-157">이 챕터의 다음 단계를 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-157">The steps followed in this chapter can be automated.</span></span> <span data-ttu-id="f81c1-158">프로젝트 파일의 차이점과 일반적인 패키지에 대 한 업데이트와 같은 구조적 변경은 스크립트를 통해 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-158">Structural changes, like project file differences and updates to common packages, can be applied by scripts.</span></span> <span data-ttu-id="f81c1-159">이러한 스크립트는 더 많은 프로젝트에서 반복적으로 실행 되므로 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-159">These scripts can be refined as they're run iteratively on more projects.</span></span> <span data-ttu-id="f81c1-160">각 실행에서 각 프로젝트에 필요한 모든 수동 단계를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-160">On each run, examine whatever manual steps are required for each project.</span></span> <span data-ttu-id="f81c1-161">가능 하면 수동 단계를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-161">Automate those manual steps, if possible.</span></span> <span data-ttu-id="f81c1-162">이 접근 방식을 사용 하 여 조직에서는 시간이 지남에 따라 앱을 이식할 때 보다 빠르고 효율적으로 성장 하 고 각 단계에서 향상 된 자동화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-162">Using this approach, the organization should grow faster and better at porting their apps over time, with improved automation support each step of the way.</span></span>

<span data-ttu-id="f81c1-163">[Lizzy Gallagher Of Mastercard이 dotNetConf 프레젠테이션에서](https://www.youtube.com/watch?v=C-2haqb60No)이 접근 방식을 사용 하는 방법에 대 한 개요를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="f81c1-163">Watch an overview of how to employ this approach in this [dotNetConf presentation by Lizzy Gallagher of Mastercard](https://www.youtube.com/watch?v=C-2haqb60No).</span></span> <span data-ttu-id="f81c1-164">이 프레젠테이션에 사용 된 5 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-164">The five phases employed in this presentation included:</span></span>

- <span data-ttu-id="f81c1-165">타사 NuGet 종속성 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f81c1-165">Migrate third-party NuGet dependencies</span></span>
- <span data-ttu-id="f81c1-166">새 *.csproj* 파일 형식을 사용 하도록 앱 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f81c1-166">Migrate apps to use new *.csproj* file format</span></span>
- <span data-ttu-id="f81c1-167">앱을 ASP.NET Core로 마이그레이션 (.NET Framework 대상 지정)</span><span class="sxs-lookup"><span data-stu-id="f81c1-167">Migrate apps to ASP.NET Core (targeting .NET Framework)</span></span>
- <span data-ttu-id="f81c1-168">.NET Standard에 대 한 내부 NuGet 종속성 업데이트</span><span class="sxs-lookup"><span data-stu-id="f81c1-168">Update internal NuGet dependencies to .NET Standard</span></span>
- <span data-ttu-id="f81c1-169">.NET Core 3.1을 대상으로 하는 모든 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="f81c1-169">Update all apps to target .NET Core 3.1</span></span>

<span data-ttu-id="f81c1-170">큰 앱 제품군을 자동화할 때 일관 된 코딩 지침과 프로젝트 조직을 따르는 경우 크게 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-170">When automating a large suite of apps, it helps significantly if they follow consistent coding guidelines and project organization.</span></span> <span data-ttu-id="f81c1-171">Automation 활동은 이러한 일관성을 사용 하 여 효과적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-171">Automation efforts rely on this consistency to be effective.</span></span> <span data-ttu-id="f81c1-172">프로젝트 파일을 구문 분석 하 고 마이그레이션하는 것 외에도 일반적인 코드 패턴을 자동으로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-172">In addition to parsing and migrating project files, common code patterns can be migrated automatically.</span></span> <span data-ttu-id="f81c1-173">일부 코드 패턴 예제에는 컨트롤러 작업의 선언 방법 또는 결과 반환 방법의 차이점이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-173">Some code pattern examples include differences in how controller actions are declared or how they return results.</span></span>

<span data-ttu-id="f81c1-174">예를 들어, 마이그레이션 스크립트는 다음 패턴 중 하 나와 일치 하는 코드 줄에 대해 *Controller.cs* 일치 하는 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-174">For example, a migration script could search files matching *Controller.cs* for lines of code matching one of these patterns:</span></span>

```csharp
   return new HttpStatusCodeResult(200);
   // or
   return new HttpStatusCodeResult(HttpStatusCode.OK);
```

<span data-ttu-id="f81c1-175">ASP.NET Core에서 위의 코드 줄 중 하나를 다음으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-175">In ASP.NET Core, either of the preceding lines of code can be replaced with:</span></span>

```csharp
    return Ok();
```

## <a name="summary"></a><span data-ttu-id="f81c1-176">요약</span><span class="sxs-lookup"><span data-stu-id="f81c1-176">Summary</span></span>

<span data-ttu-id="f81c1-177">많은 .NET Framework 앱을 .NET Core로 이식 하는 가장 좋은 방법은 다음을 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-177">The best approach to porting a large .NET Framework app to .NET Core is to:</span></span>

1. <span data-ttu-id="f81c1-178">프로젝트 종속성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-178">Identify project dependencies.</span></span>
1. <span data-ttu-id="f81c1-179">각 프로젝트를 이식 하는 데 필요한 작업을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-179">Analyze what's required to port each project.</span></span>
1. <span data-ttu-id="f81c1-180">아래쪽부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-180">Start from the bottom up.</span></span>

<span data-ttu-id="f81c1-181">.NET 이식성 분석기를 사용 하 여 대상 플랫폼과 호환 되는 기존 라이브러리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-181">You can use the .NET Portability Analyzer to determine how compatible existing libraries may be with target platforms.</span></span> <span data-ttu-id="f81c1-182">자동화 된 테스트를 통해 앱이 이식 될 때 주요 변경 사항이 도입 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-182">Automated tests will help ensure no breaking changes are introduced as the app is ported.</span></span> <span data-ttu-id="f81c1-183">이러한 테스트 프로젝트는 이식 된 첫 번째 프로젝트 사이에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c1-183">These test projects should be among the first projects ported.</span></span>

## <a name="references"></a><span data-ttu-id="f81c1-184">참조</span><span class="sxs-lookup"><span data-stu-id="f81c1-184">References</span></span>

- [<span data-ttu-id="f81c1-185">.NET Framework에서 .NET Core로 이식</span><span class="sxs-lookup"><span data-stu-id="f81c1-185">Porting from .NET Framework to .NET Core</span></span>](../../core/porting/index.md)
- [<span data-ttu-id="f81c1-186">.NET 이식성 분석기</span><span class="sxs-lookup"><span data-stu-id="f81c1-186">The .NET Portability Analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
- [<span data-ttu-id="f81c1-187">Channel 9: .NET 이식성 분석기에 대 한 간략 한 개요 (비디오)</span><span class="sxs-lookup"><span data-stu-id="f81c1-187">Channel 9: A Brief Look at the .NET Portability Analyzer (Video)</span></span>](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)
- [<span data-ttu-id="f81c1-188">2 년, 200 앱: 규모의 .NET Core 마이그레이션 (비디오)</span><span class="sxs-lookup"><span data-stu-id="f81c1-188">2 Years, 200 Apps: A .NET Core Migration at Scale (Video)</span></span>](https://www.youtube.com/watch?v=C-2haqb60No)

>[!div class="step-by-step"]
><span data-ttu-id="f81c1-189">[이전](migrate-large-solutions.md)
>[다음](understand-update-dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="f81c1-189">[Previous](migrate-large-solutions.md)
[Next](understand-update-dependencies.md)</span></span>
