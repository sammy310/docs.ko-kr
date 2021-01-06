---
title: .NET Core로 라이브러리 포팅
description: .NET Framework에서 .NET Core로 라이브러리 프로젝트를 이식하는 방법에 관해 알아봅니다.
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 25c53cdc71f4269b058953ef1903dc72d222f65f
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633912"
---
# <a name="port-net-framework-libraries-to-net-core"></a><span data-ttu-id="07c26-103">.NET Core로 .NET Framework 라이브러리 포팅</span><span class="sxs-lookup"><span data-stu-id="07c26-103">Port .NET Framework libraries to .NET Core</span></span>

<span data-ttu-id="07c26-104">.NET Framework 라이브러리 코드를 .NET Core로 포팅하고, 플랫폼 간에 실행하고, 코드를 사용하는 앱의 도달 범위를 확장하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-104">Learn how to port .NET Framework library code to .NET Core, where it runs cross-platform and expands the reach of the apps that use it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07c26-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="07c26-105">Prerequisites</span></span>

<span data-ttu-id="07c26-106">이 문서에서는 다음을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-106">This article assumes that you:</span></span>

- <span data-ttu-id="07c26-107">사용자가 Visual Studio 2017 이상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-107">Are using Visual Studio 2017 or later.</span></span> <span data-ttu-id="07c26-108">(.NET Core는 이전 버전의 Visual Studio에서 지원되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="07c26-108">(.NET Core isn't supported on earlier versions of Visual Studio.)</span></span>
- <span data-ttu-id="07c26-109">사용자가 [권장 이식 프로세스](index.md)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-109">Understand the [recommended porting process](index.md).</span></span>
- <span data-ttu-id="07c26-110">사용자가 [타사 종속성](third-party-deps.md)과 관련된 문제를 모두 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-110">Have resolved any issues with [third-party dependencies](third-party-deps.md).</span></span>

<span data-ttu-id="07c26-111">또한 다음 문서의 내용을 숙지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-111">You should also become familiar with the content of the following articles:</span></span>

<span data-ttu-id="07c26-112">[.NET 표준](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="07c26-112">[.NET Standard](../../standard/net-standard.md)</span></span>\
<span data-ttu-id="07c26-113">이 문서에서는 모든 .NET 구현에서 사용할 수 있는 .NET API의 공식 사양에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-113">This article describes the formal specification of .NET APIs that are intended to be available on all .NET implementations.</span></span>

<span data-ttu-id="07c26-114">[플랫폼 간 도구로 라이브러리 개발](../tutorials/libraries.md)</span><span class="sxs-lookup"><span data-stu-id="07c26-114">[Developing Libraries with Cross Platform Tools](../tutorials/libraries.md)</span></span>\
<span data-ttu-id="07c26-115">이 문서에서는 .NET Core CLI를 사용하여 라이브러리를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-115">This article explains how to write libraries using the .NET Core CLI.</span></span>

<span data-ttu-id="07c26-116">[.NET Core용 *csproj* 형식에 대한 추가 사항](../tools/csproj.md)</span><span class="sxs-lookup"><span data-stu-id="07c26-116">[Additions to the *csproj* format for .NET Core](../tools/csproj.md)</span></span>\
<span data-ttu-id="07c26-117">이 문서에서는 *csproj* 및 MSBuild로 프로젝트 시스템을 전환함에 따라 프로젝트 파일에 추가된 변경 내용을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-117">This article outlines the changes that were added to the project file as part of the move to *csproj* and MSBuild.</span></span>

<span data-ttu-id="07c26-118">[.NET Core로 이식 - 타사 종속성 분석](third-party-deps.md)</span><span class="sxs-lookup"><span data-stu-id="07c26-118">[Porting to .NET Core - Analyzing your Third-Party Party Dependencies](third-party-deps.md)</span></span>\
<span data-ttu-id="07c26-119">이 문서에서는 타사 종속성의 이식성 및 .NET Core에서 NuGet 패키지 종속성이 실행되지 않는 경우 해야 할 작업에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-119">This article discusses the portability of third-party dependencies and what to do when a NuGet package dependency doesn't run on .NET Core.</span></span>

## <a name="retarget-to-net-framework-472"></a><span data-ttu-id="07c26-120">.NET Framework 4.7.2로 대상 변경</span><span class="sxs-lookup"><span data-stu-id="07c26-120">Retarget to .NET Framework 4.7.2</span></span>

<span data-ttu-id="07c26-121">코드가 .NET Framework 4.7.2를 대상으로 하지 않는 경우 .NET Framework 4.7.2로 대상을 다시 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-121">If your code isn't targeting .NET Framework 4.7.2, we recommended that you retarget to .NET Framework 4.7.2.</span></span> <span data-ttu-id="07c26-122">그러면 .NET Standard에서 기존 API를 지원하지 않는 경우 최신 API를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-122">This ensures the availability of the latest API alternatives for cases where .NET Standard doesn't support existing APIs.</span></span>

<span data-ttu-id="07c26-123">이식하려는 각 프로젝트에 대해 Visual Studio에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-123">For each of the projects you wish to port, do the following in Visual Studio:</span></span>

1. <span data-ttu-id="07c26-124">프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-124">Right-click on the project and select **Properties**.</span></span>
1. <span data-ttu-id="07c26-125">**대상 프레임워크** 드롭다운에서 **.NET Framework 4.7.2** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-125">In the **Target Framework** dropdown, select **.NET Framework 4.7.2**.</span></span>
1. <span data-ttu-id="07c26-126">프로젝트를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-126">Recompile the project.</span></span>

<span data-ttu-id="07c26-127">프로젝트가 .NET Framework 4.7.2를 대상으로 하기 때문에 해당 버전의 .NET Framework를 코드 포팅의 기반으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-127">Because your projects now target .NET Framework 4.7.2, use that version of the .NET Framework as your base for porting code.</span></span>

## <a name="determine-portability"></a><span data-ttu-id="07c26-128">이식성 확인</span><span class="sxs-lookup"><span data-stu-id="07c26-128">Determine portability</span></span>

<span data-ttu-id="07c26-129">다음 단계에서는 API Portability Analyzer(ApiPort)를 실행하여 분석을 위한 이식성 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-129">The next step is to run the API Portability Analyzer (ApiPort) to generate a portability report for analysis.</span></span>

<span data-ttu-id="07c26-130">[API 이식성 도구(ApiPort)](../../standard/analyzers/portability-analyzer.md)를 이해하고 .NET Core를 대상으로 하는 이식성 보고서를 생성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-130">Make sure you understand the [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) and how to generate portability reports for targeting .NET Core.</span></span> <span data-ttu-id="07c26-131">이 작업을 수행하는 방법은 요구 사항 및 개인적 취향에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-131">How you do this likely varies based on your needs and personal tastes.</span></span> <span data-ttu-id="07c26-132">다음 섹션에서는 몇 가지 다른 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-132">The following sections detail a few different approaches.</span></span> <span data-ttu-id="07c26-133">코드가 어떻게 구성되어 있는가에 따라 이러한 접근 방식의 단계를 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-133">You may find yourself mixing steps of these approaches depending on how your code is structured.</span></span>

### <a name="deal-primarily-with-the-compiler"></a><span data-ttu-id="07c26-134">주로 컴파일러 처리</span><span class="sxs-lookup"><span data-stu-id="07c26-134">Deal primarily with the compiler</span></span>

<span data-ttu-id="07c26-135">이 접근 방식은 작은 프로젝트 또는 많은 .NET Framework API를 사용하지 않는 프로젝트에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-135">This approach works well for small projects or projects that don't use many .NET Framework APIs.</span></span> <span data-ttu-id="07c26-136">접근 방식은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-136">The approach is simple:</span></span>

1. <span data-ttu-id="07c26-137">필요에 따라 프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-137">Optionally, run ApiPort on your project.</span></span> <span data-ttu-id="07c26-138">ApiPort를 실행하는 경우 해결해야 할 문제에 대한 보고서에서 정보를 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="07c26-138">If you run ApiPort, gain knowledge from the report on issues you'll need to address.</span></span>
1. <span data-ttu-id="07c26-139">모든 코드를 새 .NET Core 프로젝트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-139">Copy all of your code over into a new .NET Core project.</span></span>
1. <span data-ttu-id="07c26-140">이식성 보고서(생성된 경우)를 참조하면서 프로젝트가 완전히 컴파일될 때까지 컴파일러 오류를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-140">While referring to the portability report (if generated), solve compiler errors until the project fully compiles.</span></span>

<span data-ttu-id="07c26-141">구조화되지 않은 경우에도 이 코드 중심 접근 방식은 문제를 빠르게 해결하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-141">Although it is unstructured, this code-focused approach often resolves issues quickly.</span></span> <span data-ttu-id="07c26-142">데이터 모델만 포함하는 프로젝트가 이 접근 방식에 적합한 후보가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-142">A project that contains only data models might be an ideal candidate for this approach.</span></span>

### <a name="stay-on-the-net-framework-until-portability-issues-are-resolved"></a><span data-ttu-id="07c26-143">이식성 문제가 해결될 때까지 .NET Framework 유지</span><span class="sxs-lookup"><span data-stu-id="07c26-143">Stay on the .NET Framework until portability issues are resolved</span></span>

<span data-ttu-id="07c26-144">이 접근 방식은 전체 프로세스 중에 컴파일되는 코드를 선호하는 경우 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-144">This approach might be the best if you prefer to have code that compiles during the entire process.</span></span> <span data-ttu-id="07c26-145">이 접근 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-145">The approach is as follows:</span></span>

1. <span data-ttu-id="07c26-146">프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-146">Run ApiPort on a project.</span></span>
1. <span data-ttu-id="07c26-147">이식 가능한 다른 API를 사용하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-147">Address issues by using different APIs that are portable.</span></span>
1. <span data-ttu-id="07c26-148">직접적인 대안을 사용할 수 없는 영역을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-148">Take note of any areas where you're prevented from using a direct alternative.</span></span>
1. <span data-ttu-id="07c26-149">각 프로젝트를 새 .NET Core 프로젝트에 복사할 준비가 되었다고 확신할 때까지 이식하려는 모든 프로젝트에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-149">Repeat the prior steps for all projects you're porting until you're confident each is ready to be copied over into a new .NET Core project.</span></span>
1. <span data-ttu-id="07c26-150">새 .NET Core 프로젝트에 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-150">Copy the code into a new .NET Core project.</span></span>
1. <span data-ttu-id="07c26-151">직접적인 대안이 없는 것으로 기록해 둔 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-151">Work out any issues where you noted that a direct alternative doesn't exist.</span></span>

<span data-ttu-id="07c26-152">이 신중한 접근 방식은 단순히 컴파일러 오류를 해결하는 것보다는 구조적이지만 비교적 코드 중심적이며 컴파일되는 코드가 항상 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-152">This careful approach is more structured than simply working out compiler errors, but it's still relatively code-focused and has the benefit of always having code that compiles.</span></span> <span data-ttu-id="07c26-153">다른 API를 사용하여 해결할 수 없는 특정 문제를 해결하는 방법은 현저하게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-153">The way you resolve certain issues that couldn't be addressed by just using another API varies greatly.</span></span> <span data-ttu-id="07c26-154">특정 프로젝트에 대해 보다 포괄적인 계획을 개발해야 할 수 있으며, 이는 다음 접근 방식에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-154">You may find that you need to develop a more comprehensive plan for certain projects, which is covered in the next approach.</span></span>

### <a name="develop-a-comprehensive-plan-of-attack"></a><span data-ttu-id="07c26-155">포괄적인 공격 계획 개발</span><span class="sxs-lookup"><span data-stu-id="07c26-155">Develop a comprehensive plan of attack</span></span>

<span data-ttu-id="07c26-156">이 접근 방식은 .NET Core를 지원하기 위해 코드를 재구성하거나 코드의 특정 영역을 완전히 다시 작성해야 할 수 있는 더 크고 더 복잡한 프로젝트에 가장 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-156">This approach might be best for larger and more complex projects, where restructuring code or completely rewriting certain areas of code might be necessary to support .NET Core.</span></span> <span data-ttu-id="07c26-157">이 접근 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-157">The approach is as follows:</span></span>

1. <span data-ttu-id="07c26-158">프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-158">Run ApiPort on a project.</span></span>
1. <span data-ttu-id="07c26-159">이식 불가능한 각 형식이 사용되고 있는 위치 및 해당 형식이 전체 이식성에 어떻게 영향을 주는지를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-159">Understand where each non-portable type is used and how that affects overall portability.</span></span>
   - <span data-ttu-id="07c26-160">해당 형식의 특성을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-160">Understand the nature of those types.</span></span> <span data-ttu-id="07c26-161">수는 적은데 자주 사용되나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-161">Are they small in number but used frequently?</span></span> <span data-ttu-id="07c26-162">아니면 수는 많지만 자주 사용되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-162">Are they large in number but used infrequently?</span></span> <span data-ttu-id="07c26-163">집중적으로 사용되나요? 아니면 코드 전체에 분산되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-163">Is their use concentrated, or is it spread throughout your code?</span></span>
   - <span data-ttu-id="07c26-164">이식할 수 없는 코드는 격리가 쉬우므로 더 효과적으로 처리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-164">Is it easy to isolate code that isn't portable so that you can deal with it more effectively?</span></span>
   - <span data-ttu-id="07c26-165">코드를 리팩터링해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-165">Do you need to refactor your code?</span></span>
   - <span data-ttu-id="07c26-166">이식할 수 없는 해당 형식에 대해 동일한 작업을 수행하는 다른 API가 있나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-166">For those types that aren't portable, are there alternative APIs that accomplish the same task?</span></span> <span data-ttu-id="07c26-167">예를 들어 <xref:System.Net.WebClient> 클래스를 사용하고 있는 경우 <xref:System.Net.Http.HttpClient> 클래스를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-167">For example, if you're using the <xref:System.Net.WebClient> class, you might be able to use the <xref:System.Net.Http.HttpClient> class instead.</span></span>
   - <span data-ttu-id="07c26-168">드롭인 대체가 아닌 경우에도 작업을 수행하는 데 사용할 수 있는 이식 가능한 다른 API가 있나요?</span><span class="sxs-lookup"><span data-stu-id="07c26-168">Are there different portable APIs available to accomplish a task, even if it's not a drop-in replacement?</span></span> <span data-ttu-id="07c26-169">예를 들어 <xref:System.Xml.Schema.XmlSchema>를 사용하여 XML을 구문 분석하지만 XML 스키마 검색이 필요하지 않은 경우, API를 사용하는 대신 <xref:System.Xml.Linq> API를 사용하고 직접 구문 분석을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-169">For example, if you're using <xref:System.Xml.Schema.XmlSchema> to parse XML but don't require XML schema discovery, you could use <xref:System.Xml.Linq> APIs and implement parsing yourself as opposed to relying on an API.</span></span>
1. <span data-ttu-id="07c26-170">이식하기 어려운 어셈블리가 있는 경우 지금은 .NET Framework에 유지하는 것이 나을까요?</span><span class="sxs-lookup"><span data-stu-id="07c26-170">If you have assemblies that are difficult to port, is it worth leaving them on .NET Framework for now?</span></span> <span data-ttu-id="07c26-171">다음과 같은 몇 가지 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-171">Here are some things to consider:</span></span>
   - <span data-ttu-id="07c26-172">.NET Framework 또는 Windows 관련 기능을 너무 많이 사용하기 때문에 .NET Core와 호환되지 않는 일부 기능이 라이브러리에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-172">You may have some functionality in your library that's incompatible with .NET Core because it relies too heavily on .NET Framework or Windows-specific functionality.</span></span> <span data-ttu-id="07c26-173">기능 이식을 위해 리소스를 사용할 수 있을 때까지 해당 기능을 유지하고 당분간은 기능이 더 적은 라이브러리의 임시 .NET Core 버전을 릴리스하는 것이 더 나을까요?</span><span class="sxs-lookup"><span data-stu-id="07c26-173">Is it worth leaving that functionality behind for now and releasing a temporary .NET Core version of your library with less features until resources are available to port the features?</span></span>
   - <span data-ttu-id="07c26-174">리팩터링이 도움이 될까요?</span><span class="sxs-lookup"><span data-stu-id="07c26-174">Would a refactor help?</span></span>
1. <span data-ttu-id="07c26-175">사용할 수 없는 .NET Framework API의 고유한 구현을 작성하는 것이 합리적일까요?</span><span class="sxs-lookup"><span data-stu-id="07c26-175">Is it reasonable to write your own implementation of an unavailable .NET Framework API?</span></span>
   <span data-ttu-id="07c26-176">[.NET Framework 참조 소스](https://github.com/Microsoft/referencesource)에서 코드를 복사, 수정 및 사용하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-176">You could consider copying, modifying, and using code from the [.NET Framework reference source](https://github.com/Microsoft/referencesource).</span></span> <span data-ttu-id="07c26-177">참조 소스 코드는 [MIT 라이선스](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt)에 따라 라이선스가 부여되므로, 소스를 자신의 코드에 대한 기초로 매우 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-177">The reference source code is licensed under the [MIT License](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), so you have significant freedom to use the source as a basis for your own code.</span></span> <span data-ttu-id="07c26-178">코드에서 Microsoft 특성을 제대로 지정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-178">Just be sure to properly attribute Microsoft in your code.</span></span>
1. <span data-ttu-id="07c26-179">필요에 따라 다른 프로젝트에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-179">Repeat this process as needed for different projects.</span></span>

<span data-ttu-id="07c26-180">분석 단계는 코드베이스의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-180">The analysis phase could take some time depending on the size of your codebase.</span></span> <span data-ttu-id="07c26-181">이 단계에서 시간을 할애하여 필요한 변경의 범위를 철저하게 이해하고 계획을 개발하면 장기 실행, 특히 복잡한 코드베이스가 있는 경우 일반적으로 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-181">Spending time in this phase to thoroughly understand the scope of changes needed and to develop a plan usually saves you time in the long run, particularly if you have a complex codebase.</span></span>

<span data-ttu-id="07c26-182">계획에 코드베이스의 중요한 변경 작업을 포함하는 동시에 .NET Framework 4.7.2를 계속 대상으로 지정할 수 있으므로 이전 접근 방식보다 더 구조화된 버전으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-182">Your plan could involve making significant changes to your codebase while still targeting .NET Framework 4.7.2, making this a more structured version of the previous approach.</span></span> <span data-ttu-id="07c26-183">계획 실행을 시작하는 방법은 코드베이스에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-183">How you go about executing your plan is dependent on your codebase.</span></span>

### <a name="mixed-approach"></a><span data-ttu-id="07c26-184">혼합형 접근 방식</span><span class="sxs-lookup"><span data-stu-id="07c26-184">Mixed approach</span></span>

<span data-ttu-id="07c26-185">위의 접근 방식을 프로젝트 단위로 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-185">It's likely that you'll mix the above approaches on a per-project basis.</span></span> <span data-ttu-id="07c26-186">사용자 및 코드베이스에 가장 적합한 방법을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-186">You should do what makes the most sense to you and for your codebase.</span></span>

## <a name="port-your-tests"></a><span data-ttu-id="07c26-187">테스트 이식</span><span class="sxs-lookup"><span data-stu-id="07c26-187">Port your tests</span></span>

<span data-ttu-id="07c26-188">코드를 이식한 경우 모든 항목이 제대로 작동하는지 확인하는 가장 좋은 방법은 .NET Core에 이식할 때 코드를 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-188">The best way to make sure everything works when you've ported your code is to test your code as you port it to .NET Core.</span></span> <span data-ttu-id="07c26-189">이렇게 하려면 .NET Core에 대한 테스트를 빌드하고 실행하는 테스트 프레임워크를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-189">To do this, you'll need to use a testing framework that builds and runs tests for .NET Core.</span></span> <span data-ttu-id="07c26-190">현재는 다음과 같은 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-190">Currently, you have three options:</span></span>

- [<span data-ttu-id="07c26-191">xUnit</span><span class="sxs-lookup"><span data-stu-id="07c26-191">xUnit</span></span>](https://xunit.net/)
  - [<span data-ttu-id="07c26-192">시작</span><span class="sxs-lookup"><span data-stu-id="07c26-192">Getting Started</span></span>](https://xunit.net/docs/getting-started/netcore/cmdline)
  - [<span data-ttu-id="07c26-193">MSTest 프로젝트를 xUnit으로 변환하는 도구</span><span class="sxs-lookup"><span data-stu-id="07c26-193">Tool to convert an MSTest project to xUnit</span></span>](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [<span data-ttu-id="07c26-194">NUnit</span><span class="sxs-lookup"><span data-stu-id="07c26-194">NUnit</span></span>](https://nunit.org/)
  - [<span data-ttu-id="07c26-195">시작</span><span class="sxs-lookup"><span data-stu-id="07c26-195">Getting Started</span></span>](https://github.com/nunit/docs/wiki/Installation)
  - [<span data-ttu-id="07c26-196">MSTest에서 NUnit으로 마이그레이션에 대한 블로그 게시물</span><span class="sxs-lookup"><span data-stu-id="07c26-196">Blog post about migrating from MSTest to NUnit</span></span>](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [<span data-ttu-id="07c26-197">MSTest</span><span class="sxs-lookup"><span data-stu-id="07c26-197">MSTest</span></span>](/visualstudio/test/unit-test-basics)

## <a name="recommended-approach"></a><span data-ttu-id="07c26-198">권장 접근 방식</span><span class="sxs-lookup"><span data-stu-id="07c26-198">Recommended approach</span></span>

<span data-ttu-id="07c26-199">궁극적으로 이식 작업은 .NET Framework 코드가 구성된 방법에 따라 크게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-199">Ultimately, the porting effort depends heavily on how your .NET Framework code is structured.</span></span> <span data-ttu-id="07c26-200">코드를 이식하는 좋은 방법은 코드의 기본 구성 요소인 라이브러리의 *기본* 으로 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-200">A good way to port your code is to begin with the *base* of your library, which is the foundational components of your code.</span></span> <span data-ttu-id="07c26-201">이는 다른 모든 항목에서 직접적으로나 간접적으로 사용하는 데이터 모델이나 일부 다른 기본 클래스 및 메서드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-201">This might be data models or some other foundational classes and methods that everything else uses directly or indirectly.</span></span>

1. <span data-ttu-id="07c26-202">현재 이식하고 있는 라이브러리의 계층을 테스트하는 테스트 프로젝트를 이식합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-202">Port the test project that tests the layer of your library that you're currently porting.</span></span>
1. <span data-ttu-id="07c26-203">라이브러리의 기본을 새 .NET Core 프로젝트에 복사하고 지원하려는 .NET Standard의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-203">Copy over the base of your library into a new .NET Core project and select the version of .NET Standard you wish to support.</span></span>
1. <span data-ttu-id="07c26-204">코드를 컴파일하는 데 필요한 대로 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-204">Make any changes needed to get the code to compile.</span></span> <span data-ttu-id="07c26-205">이 작업의 많은 부분에서 NuGet 패키지 종속성을 *csproj* 파일에 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-205">Much of this may require adding NuGet package dependencies to your *csproj* file.</span></span>
1. <span data-ttu-id="07c26-206">테스트를 실행하고 필요에 따라 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-206">Run the tests and make any needed adjustments.</span></span>
1. <span data-ttu-id="07c26-207">이식할 다음 코드 계층을 선택하고 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-207">Pick the next layer of code to port over and repeat the prior steps.</span></span>

<span data-ttu-id="07c26-208">라이브러리의 기본으로 시작하고 기본에서 바깥쪽으로 이동하면서 필요에 따라 각 계층을 테스트하면, 이식은 한 번에 하나의 코드 계층으로 문제가 격리되는 체계적인 프로세스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c26-208">If you start with the base of your library and move outward from the base and test each layer as needed, porting is a systematic process where problems are isolated to one layer of code at a time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07c26-209">다음 단계</span><span class="sxs-lookup"><span data-stu-id="07c26-209">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="07c26-210">.NET Core 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="07c26-210">Organize projects for .NET Core</span></span>](project-structure.md)
