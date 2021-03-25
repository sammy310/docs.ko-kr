---
title: .NET으로 라이브러리 포팅
description: .NET Framework에서 .NET으로 라이브러리 프로젝트를 포팅하는 방법을 알아봅니다.
author: cartermp
ms.date: 03/04/2021
ms.openlocfilehash: 5fe7b57e583f74c12649746cd9968fde03b94435
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604946"
---
# <a name="port-net-framework-libraries-to-net"></a><span data-ttu-id="a615c-103">.NET으로 .NET Framework 라이브러리 포팅</span><span class="sxs-lookup"><span data-stu-id="a615c-103">Port .NET Framework libraries to .NET</span></span>

<span data-ttu-id="a615c-104">.NET Framework 라이브러리 코드를 .NET으로 포팅하고, 플랫폼 간에 실행하고, 코드를 사용하는 앱의 도달 범위를 확장하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-104">Learn how to port .NET Framework library code to .NET, where it runs cross-platform and expands the reach of the apps that use it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a615c-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a615c-105">Prerequisites</span></span>

<span data-ttu-id="a615c-106">이 문서에서는 다음을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-106">This article assumes that you:</span></span>

- <span data-ttu-id="a615c-107">Visual Studio 2019 이상을 사용하고 있나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-107">Are using Visual Studio 2019 or later?</span></span>
  - <span data-ttu-id="a615c-108">.NET 5에는 Visual Studio 2019(v16.9) 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-108">.NET 5 requires Visual Studio 2019 (v16.9) or later.</span></span>
  - <span data-ttu-id="a615c-109">.NET Core 3.1에는 Visual Studio 2019(v16.4) 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-109">.NET Core 3.1 requires Visual Studio 2019 (v16.4) or later.</span></span>
- <span data-ttu-id="a615c-110">사용자가 [권장 이식 프로세스](index.md)를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-110">Understand the [recommended porting process](index.md).</span></span>
- <span data-ttu-id="a615c-111">사용자가 [타사 종속성](third-party-deps.md)과 관련된 문제를 모두 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-111">Have resolved any issues with [third-party dependencies](third-party-deps.md).</span></span>

<span data-ttu-id="a615c-112">다음 문서의 내용을 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="a615c-112">Familiarize yourself with the content of the following articles:</span></span>

- <span data-ttu-id="a615c-113">[.NET Standard.](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="a615c-113">[.NET Standard.](../../standard/net-standard.md)</span></span>\
<span data-ttu-id="a615c-114">이 문서에서는 모든 .NET 구현에서 사용할 수 있는 .NET API의 공식 사양에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-114">This article describes the formal specification of .NET APIs that are intended to be available on all .NET implementations.</span></span>

- <span data-ttu-id="a615c-115">[.NET CLI를 사용하여 라이브러리를 개발합니다.](../tutorials/libraries.md)</span><span class="sxs-lookup"><span data-stu-id="a615c-115">[Develop libraries with the .NET CLI.](../tutorials/libraries.md)</span></span>\
<span data-ttu-id="a615c-116">이 문서에서는 .NET CLI를 사용하여 라이브러리를 작성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-116">This article explains how to write libraries using the .NET CLI.</span></span>

- <span data-ttu-id="a615c-117">[.NET 프로젝트 SDK.](../project-sdk/overview.md)</span><span class="sxs-lookup"><span data-stu-id="a615c-117">[.NET project SDKs.](../project-sdk/overview.md)</span></span>\
<span data-ttu-id="a615c-118">이 문서에서는 SDK 스타일 프로젝트 파일 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-118">This article describes the SDK-style project file format.</span></span>

- <span data-ttu-id="a615c-119">[.NET Framework에서 .NET으로 코드를 포팅하기 위한 종속성을 분석합니다.](third-party-deps.md)</span><span class="sxs-lookup"><span data-stu-id="a615c-119">[Analyze your dependencies to port code from .NET Framework to .NET.](third-party-deps.md)</span></span>\
<span data-ttu-id="a615c-120">이 문서에서는 타사 종속성의 이식성 및 .NET에서 NuGet 패키지 종속성이 실행되지 않는 경우 수행해야 할 작업에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-120">This article discusses the portability of third-party dependencies, and what to do when a NuGet package dependency doesn't run on .NET.</span></span>

## <a name="retarget-to-net-framework-472"></a><span data-ttu-id="a615c-121">.NET Framework 4.7.2로 대상 변경</span><span class="sxs-lookup"><span data-stu-id="a615c-121">Retarget to .NET Framework 4.7.2</span></span>

<span data-ttu-id="a615c-122">코드가 .NET Framework 4.7.2를 대상으로 하지 않는 경우 .NET Framework 4.7.2로 대상을 다시 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-122">If your code isn't targeting .NET Framework 4.7.2, we recommended that you retarget to .NET Framework 4.7.2.</span></span> <span data-ttu-id="a615c-123">그러면 .NET Standard에서 기존 API를 지원하지 않는 경우 최신 API를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-123">This ensures the availability of the latest API alternatives for cases where .NET Standard doesn't support existing APIs.</span></span>

<span data-ttu-id="a615c-124">이식하려는 각 프로젝트에 대해 Visual Studio에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-124">For each of the projects you wish to port, do the following in Visual Studio:</span></span>

01. <span data-ttu-id="a615c-125">프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-125">Right-click on the project and select **Properties**.</span></span>
01. <span data-ttu-id="a615c-126">**대상 프레임워크** 드롭다운에서 **.NET Framework 4.7.2** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-126">In the **Target Framework** dropdown, select **.NET Framework 4.7.2**.</span></span>
01. <span data-ttu-id="a615c-127">프로젝트를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-127">Recompile the project.</span></span>

<span data-ttu-id="a615c-128">프로젝트가 .NET Framework 4.7.2를 대상으로 하기 때문에 해당 버전의 .NET Framework를 코드 포팅의 기반으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-128">Because your projects now target .NET Framework 4.7.2, use that version of the .NET Framework as your base for porting code.</span></span>

## <a name="determine-portability"></a><span data-ttu-id="a615c-129">이식성 확인</span><span class="sxs-lookup"><span data-stu-id="a615c-129">Determine portability</span></span>

<span data-ttu-id="a615c-130">다음 단계에서는 API Portability Analyzer(ApiPort)를 실행하여 분석을 위한 이식성 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-130">The next step is to run the API Portability Analyzer (ApiPort) to generate a portability report for analysis.</span></span>

<span data-ttu-id="a615c-131">[API 이식성 분석기(ApiPort)](../../standard/analyzers/portability-analyzer.md)와 .NET을 대상으로 하는 이식성 보고서를 생성하는 방법을 이해하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-131">Make sure you understand the [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) and how to generate portability reports for targeting .NET.</span></span> <span data-ttu-id="a615c-132">이 작업을 수행하는 방법은 요구 사항 및 개인적 취향에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-132">How you do this likely varies based on your needs and personal tastes.</span></span> <span data-ttu-id="a615c-133">다음 섹션에서는 몇 가지 다른 방법을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-133">The following sections detail a few different approaches.</span></span> <span data-ttu-id="a615c-134">코드가 어떻게 구성되어 있는가에 따라 이러한 접근 방식의 단계를 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-134">You may find yourself mixing steps of these approaches depending on how your code is structured.</span></span>

### <a name="deal-primarily-with-the-compiler"></a><span data-ttu-id="a615c-135">주로 컴파일러 처리</span><span class="sxs-lookup"><span data-stu-id="a615c-135">Deal primarily with the compiler</span></span>

<span data-ttu-id="a615c-136">이 접근 방식은 작은 프로젝트 또는 많은 .NET Framework API를 사용하지 않는 프로젝트에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-136">This approach works well for small projects or projects that don't use many .NET Framework APIs.</span></span> <span data-ttu-id="a615c-137">접근 방식은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-137">The approach is simple:</span></span>

01. <span data-ttu-id="a615c-138">필요에 따라 프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-138">Optionally, run ApiPort on your project.</span></span> <span data-ttu-id="a615c-139">ApiPort를 실행하는 경우 해결해야 할 문제에 대한 보고서에서 정보를 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="a615c-139">If you run ApiPort, gain knowledge from the report on issues you'll need to address.</span></span>
01. <span data-ttu-id="a615c-140">모든 코드를 새 .NET 프로젝트에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-140">Copy all of your code over into a new .NET project.</span></span>
01. <span data-ttu-id="a615c-141">이식성 보고서(생성된 경우)를 참조하면서 프로젝트가 완전히 컴파일될 때까지 컴파일러 오류를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-141">While referring to the portability report (if generated), solve compiler errors until the project fully compiles.</span></span>

<span data-ttu-id="a615c-142">구조화되지 않은 경우에도 이 코드 중심 접근 방식은 문제를 빠르게 해결하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-142">Although it's unstructured, this code-focused approach often resolves issues quickly.</span></span> <span data-ttu-id="a615c-143">데이터 모델만 포함하는 프로젝트가 이 접근 방식에 적합한 후보가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-143">A project that contains only data models might be an ideal candidate for this approach.</span></span>

### <a name="stay-on-the-net-framework-until-portability-issues-are-resolved"></a><span data-ttu-id="a615c-144">이식성 문제가 해결될 때까지 .NET Framework 유지</span><span class="sxs-lookup"><span data-stu-id="a615c-144">Stay on the .NET Framework until portability issues are resolved</span></span>

<span data-ttu-id="a615c-145">이 접근 방식은 전체 프로세스 중에 컴파일되는 코드를 선호하는 경우 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-145">This approach might be the best if you prefer to have code that compiles during the entire process.</span></span> <span data-ttu-id="a615c-146">이 접근 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-146">The approach is as follows:</span></span>

01. <span data-ttu-id="a615c-147">프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-147">Run ApiPort on a project.</span></span>
01. <span data-ttu-id="a615c-148">이식 가능한 다른 API를 사용하여 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-148">Address issues by using different APIs that are portable.</span></span>
01. <span data-ttu-id="a615c-149">직접적인 대안을 사용할 수 없는 영역을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-149">Take note of any areas where you're prevented from using a direct alternative.</span></span>
01. <span data-ttu-id="a615c-150">각 프로젝트를 새 .NET 프로젝트에 복사할 준비가 되었다고 확신할 때까지 포팅하려는 모든 프로젝트에 대해 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-150">Repeat the prior steps for all projects you're porting until you're confident each is ready to be copied over into a new .NET project.</span></span>
01. <span data-ttu-id="a615c-151">새 .NET 프로젝트에 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-151">Copy the code into a new .NET project.</span></span>
01. <span data-ttu-id="a615c-152">직접적인 대안이 없는 것으로 기록해 둔 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-152">Work out any issues where you noted that a direct alternative doesn't exist.</span></span>

<span data-ttu-id="a615c-153">이 신중한 접근 방식은 단순히 컴파일러 오류를 해결하는 것보다는 구조적이지만 비교적 코드 중심적이며 컴파일되는 코드가 항상 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-153">This careful approach is more structured than simply working out compiler errors, but it's still relatively code-focused and has the benefit of always having code that compiles.</span></span> <span data-ttu-id="a615c-154">다른 API를 사용하여 해결할 수 없는 특정 문제를 해결하는 방법은 현저하게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-154">The way you resolve certain issues that couldn't be addressed by just using another API varies greatly.</span></span> <span data-ttu-id="a615c-155">특정 프로젝트에 대해 보다 포괄적인 계획을 개발해야 할 수 있으며, 이는 다음 접근 방식에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-155">You may find that you need to develop a more comprehensive plan for certain projects, which is covered in the next approach.</span></span>

### <a name="develop-a-comprehensive-plan-of-attack"></a><span data-ttu-id="a615c-156">포괄적인 공격 계획 개발</span><span class="sxs-lookup"><span data-stu-id="a615c-156">Develop a comprehensive plan of attack</span></span>

<span data-ttu-id="a615c-157">이 접근 방식은 .NET을 지원하기 위해 코드를 재구성하거나 코드의 특정 영역을 완전히 다시 작성해야 할 수 있는 더 크고 더 복잡한 프로젝트에 가장 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-157">This approach might be best for larger and more complex projects, where restructuring code or completely rewriting certain areas of code might be necessary to support .NET.</span></span> <span data-ttu-id="a615c-158">이 접근 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-158">The approach is as follows:</span></span>

01. <span data-ttu-id="a615c-159">프로젝트에서 ApiPort를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-159">Run ApiPort on a project.</span></span>
01. <span data-ttu-id="a615c-160">이식 불가능한 각 형식이 사용되고 있는 위치 및 해당 형식이 전체 이식성에 어떻게 영향을 주는지를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-160">Understand where each non-portable type is used and how that affects overall portability.</span></span>

    - <span data-ttu-id="a615c-161">해당 형식의 특성을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-161">Understand the nature of those types.</span></span> <span data-ttu-id="a615c-162">수는 적은데 자주 사용되나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-162">Are they small in number but used frequently?</span></span> <span data-ttu-id="a615c-163">아니면 수는 많지만 자주 사용되지 않나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-163">Are they large in number but used infrequently?</span></span> <span data-ttu-id="a615c-164">집중적으로 사용되나요? 아니면 코드 전체에 분산되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-164">Is their use concentrated, or is it spread throughout your code?</span></span>
    - <span data-ttu-id="a615c-165">이식할 수 없는 코드는 격리가 쉬우므로 더 효과적으로 처리할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-165">Is it easy to isolate code that isn't portable so that you can deal with it more effectively?</span></span>
    - <span data-ttu-id="a615c-166">코드를 리팩터링해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-166">Do you need to refactor your code?</span></span>
    - <span data-ttu-id="a615c-167">이식할 수 없는 해당 형식에 대해 동일한 작업을 수행하는 다른 API가 있나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-167">For those types that aren't portable, are there alternative APIs that accomplish the same task?</span></span> <span data-ttu-id="a615c-168">예를 들어 <xref:System.Net.WebClient> 클래스를 사용하고 있는 경우 <xref:System.Net.Http.HttpClient> 클래스를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-168">For example, if you're using the <xref:System.Net.WebClient> class, use the <xref:System.Net.Http.HttpClient> class instead.</span></span>
    - <span data-ttu-id="a615c-169">드롭인 대체가 아닌 경우에도 작업을 수행하는 데 사용할 수 있는 이식 가능한 다른 API가 있나요?</span><span class="sxs-lookup"><span data-stu-id="a615c-169">Are there different portable APIs available to accomplish a task, even if it's not a drop-in replacement?</span></span> <span data-ttu-id="a615c-170">예를 들어 <xref:System.Xml.Schema.XmlSchema>를 사용하여 XML을 구문 분석하지만 XML 스키마 검색이 필요하지 않은 경우, API를 사용하는 대신 <xref:System.Xml.Linq> API를 사용하고 직접 구문 분석을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-170">For example, if you're using <xref:System.Xml.Schema.XmlSchema> to parse XML but don't require XML schema discovery, you could use <xref:System.Xml.Linq> APIs and implement parsing yourself instead of relying on an API.</span></span>

01. <span data-ttu-id="a615c-171">이식하기 어려운 어셈블리가 있는 경우 지금은 .NET Framework에 유지하는 것이 나을까요?</span><span class="sxs-lookup"><span data-stu-id="a615c-171">If you have assemblies that are difficult to port, is it worth leaving them on .NET Framework for now?</span></span> <span data-ttu-id="a615c-172">다음과 같은 몇 가지 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-172">Here are some things to consider:</span></span>

    - <span data-ttu-id="a615c-173">.NET Framework 또는 Windows 관련 기능을 너무 많이 사용하기 때문에 .NET과 호환되지 않는 일부 기능이 라이브러리에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-173">You may have some functionality in your library that's incompatible with .NET because it relies too heavily on .NET Framework or Windows-specific functionality.</span></span> <span data-ttu-id="a615c-174">기능 이식을 위해 리소스를 사용할 수 있을 때까지 해당 기능을 유지하고 당분간은 기능이 적은 라이브러리의 임시 .NET 버전을 릴리스하는 것이 더 나을까요?</span><span class="sxs-lookup"><span data-stu-id="a615c-174">Is it worth leaving that functionality behind for now and releasing a temporary .NET version of your library with fewer features until resources are available to port the features?</span></span>
    - <span data-ttu-id="a615c-175">리팩터링이 도움이 될까요?</span><span class="sxs-lookup"><span data-stu-id="a615c-175">Would a refactor help?</span></span>

01. <span data-ttu-id="a615c-176">사용할 수 없는 .NET Framework API의 고유한 구현을 작성하는 것이 합리적일까요?</span><span class="sxs-lookup"><span data-stu-id="a615c-176">Is it reasonable to write your own implementation of an unavailable .NET Framework API?</span></span>

    <span data-ttu-id="a615c-177">[.NET Framework 참조 소스](https://github.com/Microsoft/referencesource)에서 코드를 복사, 수정 및 사용하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-177">You could consider copying, modifying, and using code from the [.NET Framework reference source](https://github.com/Microsoft/referencesource).</span></span> <span data-ttu-id="a615c-178">참조 소스 코드는 [MIT 라이선스](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt)에 따라 라이선스가 부여되므로, 소스를 자신의 코드에 대한 기초로 매우 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-178">The reference source code is licensed under the [MIT License](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), so you have significant freedom to use the source as a basis for your own code.</span></span> <span data-ttu-id="a615c-179">코드에서 Microsoft 특성을 제대로 지정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-179">Just be sure to properly attribute Microsoft in your code.</span></span>

01. <span data-ttu-id="a615c-180">필요에 따라 다른 프로젝트에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-180">Repeat this process as needed for different projects.</span></span>

<span data-ttu-id="a615c-181">분석 단계는 코드베이스의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-181">The analysis phase could take some time depending on the size of your codebase.</span></span> <span data-ttu-id="a615c-182">이 단계에서 시간을 할애하여 필요한 변경의 범위를 철저하게 이해하고 계획을 개발하면 특히 복잡한 코드베이스가 있는 경우 대개 최종적으로 시간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-182">Spending time in this phase to thoroughly understand the scope of changes needed and to develop a plan usually saves you time in the end, particularly if you have a complex codebase.</span></span>

<span data-ttu-id="a615c-183">계획에는 .NET Framework 4.7.2를 계속 대상으로 지정하는 동시에 코드베이스를 크게 변경하는 것이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-183">Your plan could involve making significant changes to your codebase while still targeting .NET Framework 4.7.2.</span></span> <span data-ttu-id="a615c-184">이는 이전 접근 방식의 좀 더 구조화된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-184">This is a more structured version of the previous approach.</span></span> <span data-ttu-id="a615c-185">계획 실행을 시작하는 방법은 코드베이스에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-185">How you go about executing your plan is dependent on your codebase.</span></span>

### <a name="mixed-approach"></a><span data-ttu-id="a615c-186">혼합형 접근 방식</span><span class="sxs-lookup"><span data-stu-id="a615c-186">Mixed approach</span></span>

<span data-ttu-id="a615c-187">위의 접근 방식을 프로젝트 단위로 혼합하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-187">It's likely that you'll mix the above approaches on a per-project basis.</span></span> <span data-ttu-id="a615c-188">사용자 및 코드베이스에 가장 적합한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-188">Do what makes the most sense to you and for your codebase.</span></span>

## <a name="port-your-tests"></a><span data-ttu-id="a615c-189">테스트 이식</span><span class="sxs-lookup"><span data-stu-id="a615c-189">Port your tests</span></span>

<span data-ttu-id="a615c-190">코드를 이식한 경우 모든 항목이 제대로 작동하는지 확인하는 가장 좋은 방법은 .NET에 이식할 때 코드를 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-190">The best way to make sure everything works when you've ported your code is to test your code as you port it to .NET.</span></span> <span data-ttu-id="a615c-191">이렇게 하려면 .NET에 대한 테스트를 빌드하고 실행하는 테스트 프레임워크를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-191">To do this, you'll need to use a testing framework that builds and runs tests for .NET.</span></span> <span data-ttu-id="a615c-192">현재는 다음과 같은 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-192">Currently, you have three options:</span></span>

- [<span data-ttu-id="a615c-193">xUnit</span><span class="sxs-lookup"><span data-stu-id="a615c-193">xUnit</span></span>](https://xunit.net/)
  - [<span data-ttu-id="a615c-194">시작</span><span class="sxs-lookup"><span data-stu-id="a615c-194">Getting Started</span></span>](https://xunit.net/docs/getting-started/netcore/cmdline)
  - [<span data-ttu-id="a615c-195">MSTest 프로젝트를 xUnit으로 변환하는 도구</span><span class="sxs-lookup"><span data-stu-id="a615c-195">Tool to convert an MSTest project to xUnit</span></span>](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [<span data-ttu-id="a615c-196">NUnit</span><span class="sxs-lookup"><span data-stu-id="a615c-196">NUnit</span></span>](https://nunit.org/)
  - [<span data-ttu-id="a615c-197">시작</span><span class="sxs-lookup"><span data-stu-id="a615c-197">Getting Started</span></span>](https://github.com/nunit/docs/wiki/Installation)
  - [<span data-ttu-id="a615c-198">MSTest에서 NUnit으로 마이그레이션에 대한 블로그 게시물</span><span class="sxs-lookup"><span data-stu-id="a615c-198">Blog post about migrating from MSTest to NUnit</span></span>](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [<span data-ttu-id="a615c-199">MSTest</span><span class="sxs-lookup"><span data-stu-id="a615c-199">MSTest</span></span>](/visualstudio/test/unit-test-basics)

## <a name="recommended-approach"></a><span data-ttu-id="a615c-200">권장 접근 방식</span><span class="sxs-lookup"><span data-stu-id="a615c-200">Recommended approach</span></span>

<span data-ttu-id="a615c-201">궁극적으로 이식 작업은 .NET Framework 코드가 구성된 방법에 따라 크게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-201">Ultimately, the porting effort depends heavily on how your .NET Framework code is structured.</span></span> <span data-ttu-id="a615c-202">코드를 이식하는 좋은 방법은 코드의 기본 구성 요소인 라이브러리의 *기본* 으로 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-202">A good way to port your code is to begin with the *base* of your library, which is the foundational components of your code.</span></span> <span data-ttu-id="a615c-203">이는 다른 모든 항목에서 직접적으로나 간접적으로 사용하는 데이터 모델이나 일부 다른 기본 클래스 및 메서드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-203">This might be data models or some other foundational classes and methods that everything else uses directly or indirectly.</span></span>

01. <span data-ttu-id="a615c-204">현재 이식하고 있는 라이브러리의 계층을 테스트하는 테스트 프로젝트를 이식합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-204">Port the test project that tests the layer of your library that you're currently porting.</span></span>
01. <span data-ttu-id="a615c-205">라이브러리의 기본을 새 .NET 프로젝트에 복사하고 지원하려는 .NET Standard의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-205">Copy over the base of your library into a new .NET project and select the version of .NET Standard you wish to support.</span></span>
01. <span data-ttu-id="a615c-206">코드를 컴파일하는 데 필요한 대로 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-206">Make any changes needed to get the code to compile.</span></span> <span data-ttu-id="a615c-207">이 작업의 많은 부분에서 NuGet 패키지 종속성을 *csproj* 파일에 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-207">Much of this may require adding NuGet package dependencies to your *csproj* file.</span></span>
01. <span data-ttu-id="a615c-208">테스트를 실행하고 필요에 따라 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-208">Run the tests and make any needed adjustments.</span></span>
01. <span data-ttu-id="a615c-209">이식할 다음 코드 계층을 선택하고 이전 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-209">Pick the next layer of code to port over and repeat the prior steps.</span></span>

<span data-ttu-id="a615c-210">라이브러리의 기본으로 시작하고 기본에서 바깥쪽으로 이동하면서 필요에 따라 각 계층을 테스트하면, 이식은 한 번에 하나의 코드 계층으로 문제가 격리되는 체계적인 프로세스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a615c-210">If you start with the base of your library and move outward from the base and test each layer as needed, porting is a systematic process where problems are isolated to one layer of code at a time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a615c-211">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a615c-211">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="a615c-212">.NET에 대한 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="a615c-212">Organize projects for .NET</span></span>](project-structure.md)
