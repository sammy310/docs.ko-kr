---
title: .NET의 코드 분석
titleSuffix: ''
description: .NET SDK의 소스 코드 분석에 대해 알아봅니다.
ms.date: 08/22/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: ca3a9cb914befbc8e0982070b818b27ee3143793
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "96593841"
---
# <a name="overview-of-net-source-code-analysis"></a><span data-ttu-id="86b03-103">.NET 소스 코드 분석 개요</span><span class="sxs-lookup"><span data-stu-id="86b03-103">Overview of .NET source code analysis</span></span>

<span data-ttu-id="86b03-104">.NET 컴파일러 플랫폼(Roslyn) 분석기는 C# 또는 Visual Basic 코드를 검사하여 코드 품질 및 코드 스타일 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-104">.NET compiler platform (Roslyn) analyzers inspect your C# or Visual Basic code for code quality and code style issues.</span></span> <span data-ttu-id="86b03-105">.NET 5.0부터 이러한 분석기는 .NET SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-105">Starting in .NET 5.0, these analyzers are included with the .NET SDK.</span></span> <span data-ttu-id="86b03-106">(이전에는 코드 품질 분석기를 [NuGet 패키지로](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)설치 했 고 코드 스타일 분석기는 Visual Studio와 함께 설치 했습니다.)</span><span class="sxs-lookup"><span data-stu-id="86b03-106">(Previously, you installed code quality analyzers as a [NuGet package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), and code style analyzers were installed with Visual Studio.)</span></span>

- [<span data-ttu-id="86b03-107">코드 품질 분석 ("CAxxxx" 규칙)</span><span class="sxs-lookup"><span data-stu-id="86b03-107">Code quality analysis ("CAxxxx" rules)</span></span>](#code-quality-analysis)
- [<span data-ttu-id="86b03-108">코드 스타일 분석 ("IDExxxx" 규칙)</span><span class="sxs-lookup"><span data-stu-id="86b03-108">Code style analysis ("IDExxxx" rules)</span></span>](#code-style-analysis)

<span data-ttu-id="86b03-109">분석기에서 규칙 위반을 발견 하는 경우 각 규칙의 [구성](configuration-options.md)방법에 따라 제안, 경고 또는 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-109">If rule violations are found by an analyzer, they're reported as a suggestion, warning, or error, depending on how each rule is [configured](configuration-options.md).</span></span> <span data-ttu-id="86b03-110">코드 분석 위반은 컴파일러 오류와 구별 하기 위해 접두사 "CA" 또는 "IDE"와 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-110">Code analysis violations appear with the prefix "CA" or "IDE" to differentiate them from compiler errors.</span></span>

> [!TIP]
>
> - <span data-ttu-id="86b03-111">StyleCop, [rosl](https://www.nuget.org/packages/Roslynator.Analyzers/), [Xunit 분석기](https://www.nuget.org/packages/xunit.analyzers/)및 [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/) [sonar.projectname) Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/)와 같은 타사 분석기를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-111">You can also install third party analyzers, such as [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [XUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/), and [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).</span></span>
> - <span data-ttu-id="86b03-112">Visual Studio를 사용 하는 경우 많은 분석기 규칙에 연결 된 *코드 수정* 이 있으므로 문제를 해결 하는 데 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-112">If you're using Visual Studio, many analyzer rules have associated *code fixes* that you can apply to correct the problem.</span></span> <span data-ttu-id="86b03-113">코드 수정이 전구 아이콘 메뉴에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-113">Code fixes are shown in the light bulb icon menu.</span></span>

## <a name="code-quality-analysis"></a><span data-ttu-id="86b03-114">코드 품질 분석</span><span class="sxs-lookup"><span data-stu-id="86b03-114">Code quality analysis</span></span>

<span data-ttu-id="86b03-115">_코드 품질 분석 ("CA") 규칙_ 은 c # 또는 Visual Basic 코드에서 보안, 성능, 디자인 및 기타 문제를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-115">_Code quality analysis ("CA") rules_ inspect your C# or Visual Basic code for security, performance, design and other issues.</span></span> <span data-ttu-id="86b03-116">분석은 기본적으로 .NET 5.0 이상을 대상으로 하는 프로젝트에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-116">Analysis is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="86b03-117">[EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을로 설정 하 여 이전 .net 버전을 대상으로 하는 프로젝트에 대해 코드 분석을 사용 하도록 설정할 수 있습니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="86b03-117">You can enable code analysis on projects that target earlier .NET versions by setting the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to `true`.</span></span> <span data-ttu-id="86b03-118">을로 설정 하 여 프로젝트에 대 한 코드 분석을 사용 하지 않도록 설정할 수도 있습니다 `EnableNETAnalyzers` `false` .</span><span class="sxs-lookup"><span data-stu-id="86b03-118">You can also disable code analysis for your project by setting `EnableNETAnalyzers` to `false`.</span></span>

> [!TIP]
> <span data-ttu-id="86b03-119">Visual Studio에서는 프로젝트 속성 창를 사용 하 여 코드 분석을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-119">In Visual Studio, you can enable or disable code analysis using the Project Properties window.</span></span> <span data-ttu-id="86b03-120">프로젝트 속성 창에 액세스 하려면 솔루션 탐색기 내에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-120">To access the Project Properties window, right-click on a project within Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="86b03-121">그런 다음 **코드 분석** 탭을 선택 하 고 확인란을 선택 하거나 선택 취소 하 여 **.Net 분석기를 사용 하도록 설정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-121">Next, select the **Code Analysis** tab, and then either select or clear the checkbox to **Enable .NET analyzers**.</span></span>

### <a name="enabled-rules"></a><span data-ttu-id="86b03-122">활성화 된 규칙</span><span class="sxs-lookup"><span data-stu-id="86b03-122">Enabled rules</span></span>

<span data-ttu-id="86b03-123">다음 규칙은 기본적으로 .NET 5.0 Preview 8에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-123">The following rules are enabled, by default, in .NET 5.0 Preview 8.</span></span>

| <span data-ttu-id="86b03-124">진단 ID</span><span class="sxs-lookup"><span data-stu-id="86b03-124">Diagnostic ID</span></span> | <span data-ttu-id="86b03-125">범주</span><span class="sxs-lookup"><span data-stu-id="86b03-125">Category</span></span> | <span data-ttu-id="86b03-126">심각도</span><span class="sxs-lookup"><span data-stu-id="86b03-126">Severity</span></span> | <span data-ttu-id="86b03-127">설명</span><span class="sxs-lookup"><span data-stu-id="86b03-127">Description</span></span> |
| - | - | - | - |
| [<span data-ttu-id="86b03-128">CA1416</span><span class="sxs-lookup"><span data-stu-id="86b03-128">CA1416</span></span>](/visualstudio/code-quality/ca1416) | <span data-ttu-id="86b03-129">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="86b03-129">Interoperability</span></span> | <span data-ttu-id="86b03-130">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-130">Warning</span></span> | <span data-ttu-id="86b03-131">플랫폼 호환성 분석기</span><span class="sxs-lookup"><span data-stu-id="86b03-131">Platform compatibility analyzer</span></span> |
| [<span data-ttu-id="86b03-132">CA1417</span><span class="sxs-lookup"><span data-stu-id="86b03-132">CA1417</span></span>](/visualstudio/code-quality/ca1417) | <span data-ttu-id="86b03-133">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="86b03-133">Interoperability</span></span> | <span data-ttu-id="86b03-134">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-134">Warning</span></span> | <span data-ttu-id="86b03-135">`OutAttribute`P/invoke에 문자열 매개 변수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="86b03-135">Do not use `OutAttribute` on string parameters for P/Invokes</span></span> |
| [<span data-ttu-id="86b03-136">CA1831</span><span class="sxs-lookup"><span data-stu-id="86b03-136">CA1831</span></span>](/visualstudio/code-quality/ca1831) | <span data-ttu-id="86b03-137">성능</span><span class="sxs-lookup"><span data-stu-id="86b03-137">Performance</span></span> | <span data-ttu-id="86b03-138">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-138">Warning</span></span> | <span data-ttu-id="86b03-139">`AsSpan`적절 한 경우 문자열에 범위 기반 인덱서 대신을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-139">Use `AsSpan` instead of range-based indexers for string when appropriate</span></span> |
| [<span data-ttu-id="86b03-140">CA2013</span><span class="sxs-lookup"><span data-stu-id="86b03-140">CA2013</span></span>](/visualstudio/code-quality/ca2013) | <span data-ttu-id="86b03-141">안정성</span><span class="sxs-lookup"><span data-stu-id="86b03-141">Reliability</span></span> | <span data-ttu-id="86b03-142">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-142">Warning</span></span> | <span data-ttu-id="86b03-143">값 형식과 함께 사용 하지 마십시오. `ReferenceEquals`</span><span class="sxs-lookup"><span data-stu-id="86b03-143">Do not use `ReferenceEquals` with value types</span></span> |
| [<span data-ttu-id="86b03-144">CA2014</span><span class="sxs-lookup"><span data-stu-id="86b03-144">CA2014</span></span>](/visualstudio/code-quality/ca2014) | <span data-ttu-id="86b03-145">안정성</span><span class="sxs-lookup"><span data-stu-id="86b03-145">Reliability</span></span> | <span data-ttu-id="86b03-146">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-146">Warning</span></span> | <span data-ttu-id="86b03-147">루프에 사용 하지 마십시오. `stackalloc`</span><span class="sxs-lookup"><span data-stu-id="86b03-147">Do not use `stackalloc` in loops</span></span> |
| [<span data-ttu-id="86b03-148">CA2015</span><span class="sxs-lookup"><span data-stu-id="86b03-148">CA2015</span></span>](/visualstudio/code-quality/ca2015) | <span data-ttu-id="86b03-149">안정성</span><span class="sxs-lookup"><span data-stu-id="86b03-149">Reliability</span></span> | <span data-ttu-id="86b03-150">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-150">Warning</span></span> | <span data-ttu-id="86b03-151">에서 파생 된 형식에 대해 종료자를 정의 하지 마십시오. <xref:System.Buffers.MemoryManager%601></span><span class="sxs-lookup"><span data-stu-id="86b03-151">Do not define finalizers for types derived from <xref:System.Buffers.MemoryManager%601></span></span> |
| [<span data-ttu-id="86b03-152">CA2200</span><span class="sxs-lookup"><span data-stu-id="86b03-152">CA2200</span></span>](/visualstudio/code-quality/ca2200) | <span data-ttu-id="86b03-153">사용</span><span class="sxs-lookup"><span data-stu-id="86b03-153">Usage</span></span> | <span data-ttu-id="86b03-154">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-154">Warning</span></span> | <span data-ttu-id="86b03-155">스택 정보를 유지하도록 다시 throw하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b03-155">Rethrow to preserve stack details</span></span>
| [<span data-ttu-id="86b03-156">CA2247</span><span class="sxs-lookup"><span data-stu-id="86b03-156">CA2247</span></span>](/visualstudio/code-quality/ca2247) | <span data-ttu-id="86b03-157">사용</span><span class="sxs-lookup"><span data-stu-id="86b03-157">Usage</span></span> | <span data-ttu-id="86b03-158">경고</span><span class="sxs-lookup"><span data-stu-id="86b03-158">Warning</span></span> | <span data-ttu-id="86b03-159">TaskCompletionSource 생성자에 전달 된 인수는 <xref:System.Threading.Tasks.TaskCreationOptions> 대신 열거형 이어야 합니다. <xref:System.Threading.Tasks.TaskContinuationOptions></span><span class="sxs-lookup"><span data-stu-id="86b03-159">Argument passed to TaskCompletionSource constructor should be <xref:System.Threading.Tasks.TaskCreationOptions> enum instead of <xref:System.Threading.Tasks.TaskContinuationOptions></span></span> |

<span data-ttu-id="86b03-160">이러한 규칙의 심각도를 변경 하 여 사용 하지 않도록 설정 하거나 오류를 상승 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-160">You can change the severity of these rules to disable them or elevate them to errors.</span></span>

<span data-ttu-id="86b03-161">사용 가능한 코드 품질 규칙의 전체 목록은 [코드 품질 규칙](quality-rules/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86b03-161">For a full list of available code quality rules, see [Code quality rules](quality-rules/index.md).</span></span>

### <a name="enable-additional-rules"></a><span data-ttu-id="86b03-162">추가 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="86b03-162">Enable additional rules</span></span>

<span data-ttu-id="86b03-163">.NET 5.0 RC2부터 .NET SDK에는 모든 [“CA” 모드 품질 규칙](/visualstudio/code-quality/code-analysis-for-managed-code-warnings)이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-163">Starting with .NET 5.0 RC2, the .NET SDK ships with all of the ["CA" code quality rules](/visualstudio/code-quality/code-analysis-for-managed-code-warnings).</span></span> <span data-ttu-id="86b03-164">각 .NET SDK 버전에 포함 된 규칙의 전체 목록은 [analyzer 릴리스](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86b03-164">For a full list of rules that are included with each .NET SDK version, see [analyzer releases](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).</span></span>

#### <a name="default-analysis-mode"></a><span data-ttu-id="86b03-165">기본 분석 모드</span><span class="sxs-lookup"><span data-stu-id="86b03-165">Default analysis mode</span></span>

<span data-ttu-id="86b03-166">기본 분석 모드에서 일부 규칙은 [기본적으로](#enabled-rules) 빌드 경고로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-166">In the default analysis mode, some rules are [enabled by default](#enabled-rules) as build warnings.</span></span> <span data-ttu-id="86b03-167">일부 다른 규칙은 기본적으로 해당 코드 수정이 있는 Visual Studio IDE 제안 으로만 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-167">Some other rules are enabled by default only as Visual Studio IDE suggestions with corresponding code fixes.</span></span> <span data-ttu-id="86b03-168">나머지 규칙은 기본적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-168">The remaining rules are disabled by default.</span></span> <span data-ttu-id="86b03-169">규칙 [의 전체 목록](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) 에는 규칙의 기본 심각도와 기본 분석 모드에서 규칙을 기본적으로 사용할 수 있는지 여부가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-169">The [full list of rules](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md) includes each rule's default severity and whether or not the rule is enabled by default in the default analysis mode.</span></span>

#### <a name="custom-analysis-mode"></a><span data-ttu-id="86b03-170">사용자 지정 분석 모드</span><span class="sxs-lookup"><span data-stu-id="86b03-170">Custom analysis mode</span></span>

<span data-ttu-id="86b03-171">개별 규칙 또는 규칙 범주를 사용 하거나 사용 하지 않도록 [코드 분석 규칙을 구성할](configuration-options.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-171">You can [configure code analysis rules](configuration-options.md) to enable or disable an individual rule or a category of rules.</span></span> <span data-ttu-id="86b03-172">또한 [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) 속성을 사용 하 여 다음 사용자 지정 분석 모드 중 하나로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-172">Additionally, you can use the [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) property to switch to one of the following custom analysis modes:</span></span>

- <span data-ttu-id="86b03-173">_적극적인_ 또는 _옵트아웃_ 모드: 모든 규칙은 기본적으로 빌드 경고로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-173">_Aggressive_ or _Opt-out_ mode: All rules are enabled by default as build warnings.</span></span> <span data-ttu-id="86b03-174">개별 규칙을 선택적으로 [옵트아웃](configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-174">You can selectively [opt out](configuration-options.md) of individual rules to disable them.</span></span>
- <span data-ttu-id="86b03-175">_보수적인_ 또는 _옵트인_ 모드: 모든 규칙은 기본적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-175">_Conservative_ or _Opt-in_ mode: All rules are disabled by default.</span></span> <span data-ttu-id="86b03-176">개별 규칙을 선택적으로 [옵트인](configuration-options.md)하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-176">You can selectively [opt into](configuration-options.md) individual rules to enable them.</span></span>

### <a name="treat-warnings-as-errors"></a><span data-ttu-id="86b03-177">경고를 오류로 처리</span><span class="sxs-lookup"><span data-stu-id="86b03-177">Treat warnings as errors</span></span>

<span data-ttu-id="86b03-178">프로젝트를 빌드할 때 플래그를 사용 하는 경우 `-warnaserror` 모든 코드 분석 경고도 오류로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-178">If you use the `-warnaserror` flag when you build your projects, all code analysis warnings are also treated as errors.</span></span> <span data-ttu-id="86b03-179">CAxxxx (코드 품질 경고)를의 오류로 처리 하지 않으려는 경우 `-warnaserror` `CodeAnalysisTreatWarningsAsErrors` 프로젝트 파일에서 MSBuild 속성을로 설정할 수 있습니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="86b03-179">If you do not want code quality warnings (CAxxxx) to be treated as errors in presence of `-warnaserror`, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="86b03-180">코드 분석 경고가 계속 표시 되지만 빌드를 중단 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-180">You'll still see any code analysis warnings, but they won't break your build.</span></span>

### <a name="latest-updates"></a><span data-ttu-id="86b03-181">최신 업데이트</span><span class="sxs-lookup"><span data-stu-id="86b03-181">Latest updates</span></span>

<span data-ttu-id="86b03-182">최신 버전의 .NET SDK로 업그레이드 하는 경우 기본적으로 최신 코드 분석 규칙 및 기본 규칙 심각도가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-182">By default, you'll get the latest code analysis rules and default rule severities as you upgrade to newer versions of the .NET SDK.</span></span> <span data-ttu-id="86b03-183">이 동작을 원하지 않는 경우, 예를 들어 새 규칙을 사용 하거나 사용 하지 않도록 설정 하려는 경우 다음 방법 중 하나를 사용 하 여 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-183">If you don't want this behavior, for example, if you want to ensure that no new rules are enabled or disabled, you can override it in one of the following ways:</span></span>

- <span data-ttu-id="86b03-184">`AnalysisLevel`MSBuild 속성을 특정 값으로 설정 하 여 해당 집합에 대 한 경고를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-184">Set the `AnalysisLevel` MSBuild property to a specific value to lock the warnings to that set.</span></span> <span data-ttu-id="86b03-185">최신 SDK로 업그레이드 하는 경우 해당 경고에 대 한 버그 수정이 계속 표시 되지만 새 경고는 사용할 수 없으며, 기존 경고는 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-185">When you upgrade to a newer SDK, you'll still get bug fixes for those warnings, but no new warnings will be enabled and no existing warnings will be disabled.</span></span> <span data-ttu-id="86b03-186">예를 들어 .NET SDK 버전 5.0와 함께 제공 되는 규칙 집합을 잠그려면 프로젝트 파일에 다음 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-186">For example, to lock the set of rules to those that ship with version 5.0 of the .NET SDK, add the following entry to your project file.</span></span>

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > <span data-ttu-id="86b03-187">속성의 기본값은 `AnalysisLevel` 입니다 `latest` . 즉, 최신 버전의 .net SDK로 이동할 때 항상 최신 코드 분석 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-187">The default value for the `AnalysisLevel` property is `latest`, which means you always get the latest code analysis rules as you move to newer versions of the .NET SDK.</span></span>

  <span data-ttu-id="86b03-188">자세한 내용 및 가능한 값 목록을 보려면 [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86b03-188">For more information, and to see a list of possible values, see [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).</span></span>

- <span data-ttu-id="86b03-189">[Microsoft CodeAnalysis NuGet 패키지](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) 를 설치 하 여 .net SDK 업데이트에서 규칙 업데이트를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-189">Install the [Microsoft.CodeAnalysis.NetAnalyzers NuGet package](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) to decouple rule updates from .NET SDK updates.</span></span> <span data-ttu-id="86b03-190">패키지를 설치 하면 기본 제공 SDK 분석기가 해제 되 고 SDK에 NuGet 패키지의 최신 분석기 어셈블리 버전이 포함 되어 있으면 빌드 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-190">Installing the package turns off the built-in SDK analyzers and generates a build warning if the SDK contains a newer analyzer assembly version than that of the NuGet package.</span></span>

## <a name="code-style-analysis"></a><span data-ttu-id="86b03-191">코드 스타일 분석</span><span class="sxs-lookup"><span data-stu-id="86b03-191">Code style analysis</span></span>

<span data-ttu-id="86b03-192">[코드 스타일 분석](/visualstudio/ide/editorconfig-code-style-settings-reference) ("IDExxxx" 규칙)을 사용 하 여 코드 베이스에서 일관 된 코드 스타일을 정의 하 고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-192">[Code style analysis](/visualstudio/ide/editorconfig-code-style-settings-reference) ("IDExxxx" rules) enables you to define and maintain consistent code style in your codebase.</span></span> <span data-ttu-id="86b03-193">기본 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-193">Following are the default settings:</span></span>

- <span data-ttu-id="86b03-194">명령줄 빌드: 명령줄 빌드의 모든 .NET 프로젝트에 대해 코드 스타일 분석이 기본적으로 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-194">Command line build: Code style analysis is disabled, by default, for all .NET projects on command-line builds.</span></span>
- <span data-ttu-id="86b03-195">Visual Studio: 코드 스타일 분석은 기본적으로 Visual Studio 내의 모든 .NET 프로젝트에 대해 [코드 리팩터링 빠른 작업](/visualstudio/ide/code-generation-in-visual-studio)으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-195">Visual Studio: Code style analysis is enabled, by default, for all .NET projects inside Visual Studio as [code refactoring quick actions](/visualstudio/ide/code-generation-in-visual-studio).</span></span>

<span data-ttu-id="86b03-196">.NET 5.0 RC2를 시작 하면 명령줄 및 Visual Studio 내에서 빌드에 대 한 코드 스타일 분석을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-196">Starting .NET 5.0 RC2, you can enable code style analysis on build, both at the command line and inside Visual Studio.</span></span> <span data-ttu-id="86b03-197">코드 스타일 위반은 "IDE" 접두사를 사용 하 여 경고나 오류로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-197">Code style violations appear as warnings or errors with an "IDE" prefix.</span></span> <span data-ttu-id="86b03-198">이렇게 하면 빌드 시 일관 된 코드 스타일을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-198">This enables you to enforce consistent code styles at build time.</span></span>

> [!NOTE]
> <span data-ttu-id="86b03-199">코드 스타일 분석 기능은 실험적 이며 .NET 5와 .NET 6 릴리스 사이에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-199">The code style analysis feature is experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="86b03-200">빌드에서 코드 스타일 분석을 사용 하도록 설정 하는 단계:</span><span class="sxs-lookup"><span data-stu-id="86b03-200">Steps to enable code style analysis on build:</span></span>

1. <span data-ttu-id="86b03-201">MSBuild 속성 [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) 을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-201">Set the MSBuild property [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) to `true`.</span></span>

1. <span data-ttu-id="86b03-202">*Editorconfig* 파일에서 빌드에서 실행 하려는 각 "IDE" 코드 스타일 규칙을 경고나 오류로 [구성](configuration-options.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-202">In an *.editorconfig* file, [configure](configuration-options.md) each "IDE" code style rule that you wish to run on build as a warning or an error.</span></span> <span data-ttu-id="86b03-203">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="86b03-203">For example:</span></span>

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   <span data-ttu-id="86b03-204">또는 기본적으로 전체 "스타일" 범주를 경고 또는 오류로 구성 하 고 빌드 시 실행 하지 않을 규칙을 선택적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-204">Alternatively, you can configure the entire "Style" category to be a warning or error, by default, and then selectively turn off rules that you don't want to run on build.</span></span> <span data-ttu-id="86b03-205">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="86b03-205">For example:</span></span>

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a><span data-ttu-id="86b03-206">경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="86b03-206">Suppress a warning</span></span>

<span data-ttu-id="86b03-207">규칙 위반을 억제 하려면 EditorConfig 파일에서 해당 규칙 ID의 심각도 옵션을로 설정 `none` 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-207">To suppress a rule violation, set the severity option for that rule ID to `none` in an EditorConfig file.</span></span> <span data-ttu-id="86b03-208">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="86b03-208">For example:</span></span>

```ini
dotnet_diagnostic.CA1822.severity = none
```

<span data-ttu-id="86b03-209">Visual Studio에서는 코드 분석 규칙에서 경고를 표시 하지 않도록 하는 추가 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86b03-209">Visual Studio provides additional ways to suppress warnings from code analysis rules.</span></span> <span data-ttu-id="86b03-210">자세한 내용은 [위반 표시 안 함](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86b03-210">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span></span>

<span data-ttu-id="86b03-211">규칙 심각도에 대 한 자세한 내용은 [규칙 심각도 구성](configuration-options.md#severity-level)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86b03-211">For more information about rule severities, see [Configure rule severity](configuration-options.md#severity-level).</span></span>

## <a name="see-also"></a><span data-ttu-id="86b03-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86b03-212">See also</span></span>

- [<span data-ttu-id="86b03-213">코드 품질 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="86b03-213">Code quality analysis rule reference</span></span>](quality-rules/index.md)
- [<span data-ttu-id="86b03-214">코드 스타일 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="86b03-214">Code style analysis rule reference</span></span>](style-rules/index.md)
- [<span data-ttu-id="86b03-215">Visual Studio의 코드 분석</span><span class="sxs-lookup"><span data-stu-id="86b03-215">Code analysis in Visual Studio</span></span>](/visualstudio/code-quality/roslyn-analyzers-overview)
- [<span data-ttu-id="86b03-216">.NET Compiler Platform SDK</span><span class="sxs-lookup"><span data-stu-id="86b03-216">.NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="86b03-217">자습서: 첫 번째 분석기 및 코드 수정 작성</span><span class="sxs-lookup"><span data-stu-id="86b03-217">Tutorial: Write your first analyzer and code fix</span></span>](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
