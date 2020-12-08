---
title: .NET의 코드 분석
titleSuffix: ''
description: .NET SDK의 소스 코드 분석에 대해 알아봅니다.
ms.date: 12/04/2020
ms.topic: overview
ms.custom: updateeachrelease
helpviewer_keywords:
- code analysis
- code analyzers
ms.openlocfilehash: 657975742c3efc2985264fe16cb316357b959e73
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851818"
---
# <a name="overview-of-net-source-code-analysis"></a><span data-ttu-id="f4cdb-103">.NET 소스 코드 분석 개요</span><span class="sxs-lookup"><span data-stu-id="f4cdb-103">Overview of .NET source code analysis</span></span>

<span data-ttu-id="f4cdb-104">.NET 컴파일러 플랫폼(Roslyn) 분석기는 C# 또는 Visual Basic 코드를 검사하여 코드 품질 및 코드 스타일 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-104">.NET compiler platform (Roslyn) analyzers inspect your C# or Visual Basic code for code quality and code style issues.</span></span> <span data-ttu-id="f4cdb-105">.NET 5.0부터 이러한 분석기는 .NET SDK에 포함 되어 있으므로 별도로 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-105">Starting in .NET 5.0, these analyzers are included with the .NET SDK and you don't need to install them separately.</span></span> <span data-ttu-id="f4cdb-106">프로젝트가 .NET 5 이상을 대상으로 하는 경우 기본적으로 코드 분석이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-106">If your project targets .NET 5 or later, code analysis is enabled by default.</span></span> <span data-ttu-id="f4cdb-107">프로젝트가 .NET Core, .NET Standard 또는 .NET Framework 같은 다른 .NET 구현을 대상으로 하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을로 설정 하 여 코드 분석을 수동으로 사용 하도록 설정 해야 합니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="f4cdb-107">If your project target a different .NET implementation, for example, .NET Core, .NET Standard, or .NET Framework, you must manually enable code analysis by setting the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to `true`.</span></span>

<span data-ttu-id="f4cdb-108">.NET 5 + SDK로 이동 하지 않거나 NuGet 패키지 기반 모델을 선호 하는 경우에는 [Microsoft CodeAnalysis. Netanalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)에서도 분석기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-108">If you don't want to move to the .NET 5+ SDK or if you prefer a NuGet package-based model, the analyzers are also available in the [Microsoft.CodeAnalysis.NetAnalyzers NuGet package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers).</span></span> <span data-ttu-id="f4cdb-109">주문형 버전 업데이트에 대 한 패키지 기반 모델을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-109">You might prefer a package-based model for on-demand version updates.</span></span>

> [!NOTE]
> <span data-ttu-id="f4cdb-110">.NET 분석기는 대상 프레임 워크에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-110">.NET analyzers are target-framework agnostic.</span></span> <span data-ttu-id="f4cdb-111">즉, 프로젝트에서 특정 .NET 구현을 대상으로 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-111">That is, your project does not need to target a specific .NET implementation.</span></span> <span data-ttu-id="f4cdb-112">분석기는 및와 같은 이전 버전의 .NET을 대상으로 하는 프로젝트에 대해서도 작동 합니다 `net5.0` `netcoreapp3.1` `net472` .</span><span class="sxs-lookup"><span data-stu-id="f4cdb-112">The analyzers work for projects that target `net5.0` as well as earlier .NET versions, such as `netcoreapp3.1` and `net472`.</span></span>

<span data-ttu-id="f4cdb-113">분석기에서 규칙 위반을 발견 하는 경우 각 규칙의 [구성](configuration-options.md)방법에 따라 제안, 경고 또는 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-113">If rule violations are found by an analyzer, they're reported as a suggestion, warning, or error, depending on how each rule is [configured](configuration-options.md).</span></span> <span data-ttu-id="f4cdb-114">코드 분석 위반은 컴파일러 오류와 구별 하기 위해 접두사 "CA" 또는 "IDE"와 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-114">Code analysis violations appear with the prefix "CA" or "IDE" to differentiate them from compiler errors.</span></span>

## <a name="code-quality-analysis"></a><span data-ttu-id="f4cdb-115">코드 품질 분석</span><span class="sxs-lookup"><span data-stu-id="f4cdb-115">Code quality analysis</span></span>

<span data-ttu-id="f4cdb-116">*코드 품질 분석* ("caxxxx") 규칙은 c # 또는 Visual Basic 코드에서 보안, 성능, 디자인 및 기타 문제를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-116">*Code quality analysis* ("CAxxxx") rules inspect your C# or Visual Basic code for security, performance, design and other issues.</span></span> <span data-ttu-id="f4cdb-117">분석은 기본적으로 .NET 5.0 이상을 대상으로 하는 프로젝트에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-117">Analysis is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="f4cdb-118">[EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을로 설정 하 여 이전 .net 버전을 대상으로 하는 프로젝트에 대해 코드 분석을 사용 하도록 설정할 수 있습니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="f4cdb-118">You can enable code analysis on projects that target earlier .NET versions by setting the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to `true`.</span></span> <span data-ttu-id="f4cdb-119">을로 설정 하 여 프로젝트에 대 한 코드 분석을 사용 하지 않도록 설정할 수도 있습니다 `EnableNETAnalyzers` `false` .</span><span class="sxs-lookup"><span data-stu-id="f4cdb-119">You can also disable code analysis for your project by setting `EnableNETAnalyzers` to `false`.</span></span>

> [!TIP]
> <span data-ttu-id="f4cdb-120">Visual Studio를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f4cdb-120">If you're using Visual Studio:</span></span>
>
> - <span data-ttu-id="f4cdb-121">많은 분석기 규칙에는 문제를 해결 하기 위해 적용할 수 있는 *코드 수정* 이 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-121">Many analyzer rules have associated *code fixes* that you can apply to correct the problem.</span></span> <span data-ttu-id="f4cdb-122">코드 수정이 전구 아이콘 메뉴에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-122">Code fixes are shown in the light bulb icon menu.</span></span>
> - <span data-ttu-id="f4cdb-123">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**  >  **코드 분석** 탭 > **.net 분석기 사용** 을 선택 하 여 코드 분석을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-123">You can enable or disable code analysis by right-clicking on a project in Solution Explorer and selecting **Properties** > **Code Analysis** tab > **Enable .NET analyzers**.</span></span>

### <a name="enabled-rules"></a><span data-ttu-id="f4cdb-124">활성화 된 규칙</span><span class="sxs-lookup"><span data-stu-id="f4cdb-124">Enabled rules</span></span>

<span data-ttu-id="f4cdb-125">다음 규칙은 기본적으로 .NET 5.0에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-125">The following rules are enabled, by default, in .NET 5.0.</span></span>

| <span data-ttu-id="f4cdb-126">진단 ID</span><span class="sxs-lookup"><span data-stu-id="f4cdb-126">Diagnostic ID</span></span> | <span data-ttu-id="f4cdb-127">범주</span><span class="sxs-lookup"><span data-stu-id="f4cdb-127">Category</span></span> | <span data-ttu-id="f4cdb-128">심각도</span><span class="sxs-lookup"><span data-stu-id="f4cdb-128">Severity</span></span> | <span data-ttu-id="f4cdb-129">설명</span><span class="sxs-lookup"><span data-stu-id="f4cdb-129">Description</span></span> |
| - | - | - | - |
| [<span data-ttu-id="f4cdb-130">CA1416</span><span class="sxs-lookup"><span data-stu-id="f4cdb-130">CA1416</span></span>](/visualstudio/code-quality/ca1416) | <span data-ttu-id="f4cdb-131">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-131">Interoperability</span></span> | <span data-ttu-id="f4cdb-132">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-132">Warning</span></span> | <span data-ttu-id="f4cdb-133">플랫폼 호환성 분석기</span><span class="sxs-lookup"><span data-stu-id="f4cdb-133">Platform compatibility analyzer</span></span> |
| [<span data-ttu-id="f4cdb-134">CA1417</span><span class="sxs-lookup"><span data-stu-id="f4cdb-134">CA1417</span></span>](/visualstudio/code-quality/ca1417) | <span data-ttu-id="f4cdb-135">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-135">Interoperability</span></span> | <span data-ttu-id="f4cdb-136">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-136">Warning</span></span> | <span data-ttu-id="f4cdb-137">`OutAttribute`P/invoke에 문자열 매개 변수를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-137">Do not use `OutAttribute` on string parameters for P/Invokes</span></span> |
| [<span data-ttu-id="f4cdb-138">CA1831</span><span class="sxs-lookup"><span data-stu-id="f4cdb-138">CA1831</span></span>](/visualstudio/code-quality/ca1831) | <span data-ttu-id="f4cdb-139">성능</span><span class="sxs-lookup"><span data-stu-id="f4cdb-139">Performance</span></span> | <span data-ttu-id="f4cdb-140">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-140">Warning</span></span> | <span data-ttu-id="f4cdb-141">`AsSpan`적절 한 경우 문자열에 범위 기반 인덱서 대신을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-141">Use `AsSpan` instead of range-based indexers for string when appropriate</span></span> |
| [<span data-ttu-id="f4cdb-142">CA2013</span><span class="sxs-lookup"><span data-stu-id="f4cdb-142">CA2013</span></span>](/visualstudio/code-quality/ca2013) | <span data-ttu-id="f4cdb-143">안정성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-143">Reliability</span></span> | <span data-ttu-id="f4cdb-144">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-144">Warning</span></span> | <span data-ttu-id="f4cdb-145">값 형식과 함께 사용 하지 마십시오. `ReferenceEquals`</span><span class="sxs-lookup"><span data-stu-id="f4cdb-145">Do not use `ReferenceEquals` with value types</span></span> |
| [<span data-ttu-id="f4cdb-146">CA2014</span><span class="sxs-lookup"><span data-stu-id="f4cdb-146">CA2014</span></span>](/visualstudio/code-quality/ca2014) | <span data-ttu-id="f4cdb-147">안정성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-147">Reliability</span></span> | <span data-ttu-id="f4cdb-148">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-148">Warning</span></span> | <span data-ttu-id="f4cdb-149">루프에 사용 하지 마십시오. `stackalloc`</span><span class="sxs-lookup"><span data-stu-id="f4cdb-149">Do not use `stackalloc` in loops</span></span> |
| [<span data-ttu-id="f4cdb-150">CA2015</span><span class="sxs-lookup"><span data-stu-id="f4cdb-150">CA2015</span></span>](/visualstudio/code-quality/ca2015) | <span data-ttu-id="f4cdb-151">안정성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-151">Reliability</span></span> | <span data-ttu-id="f4cdb-152">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-152">Warning</span></span> | <span data-ttu-id="f4cdb-153">에서 파생 된 형식에 대해 종료자를 정의 하지 마십시오. <xref:System.Buffers.MemoryManager%601></span><span class="sxs-lookup"><span data-stu-id="f4cdb-153">Do not define finalizers for types derived from <xref:System.Buffers.MemoryManager%601></span></span> |
| [<span data-ttu-id="f4cdb-154">CA2200</span><span class="sxs-lookup"><span data-stu-id="f4cdb-154">CA2200</span></span>](/visualstudio/code-quality/ca2200) | <span data-ttu-id="f4cdb-155">사용</span><span class="sxs-lookup"><span data-stu-id="f4cdb-155">Usage</span></span> | <span data-ttu-id="f4cdb-156">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-156">Warning</span></span> | <span data-ttu-id="f4cdb-157">스택 정보를 유지하도록 다시 throw하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-157">Rethrow to preserve stack details</span></span>
| [<span data-ttu-id="f4cdb-158">CA2247</span><span class="sxs-lookup"><span data-stu-id="f4cdb-158">CA2247</span></span>](/visualstudio/code-quality/ca2247) | <span data-ttu-id="f4cdb-159">사용</span><span class="sxs-lookup"><span data-stu-id="f4cdb-159">Usage</span></span> | <span data-ttu-id="f4cdb-160">Warning</span><span class="sxs-lookup"><span data-stu-id="f4cdb-160">Warning</span></span> | <span data-ttu-id="f4cdb-161">TaskCompletionSource 생성자에 전달 된 인수는 <xref:System.Threading.Tasks.TaskCreationOptions> 대신 열거형 이어야 합니다. <xref:System.Threading.Tasks.TaskContinuationOptions></span><span class="sxs-lookup"><span data-stu-id="f4cdb-161">Argument passed to TaskCompletionSource constructor should be <xref:System.Threading.Tasks.TaskCreationOptions> enum instead of <xref:System.Threading.Tasks.TaskContinuationOptions></span></span> |

<span data-ttu-id="f4cdb-162">이러한 규칙의 심각도를 변경 하 여 사용 하지 않도록 설정 하거나 오류를 상승 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-162">You can change the severity of these rules to disable them or elevate them to errors.</span></span> <span data-ttu-id="f4cdb-163">[추가 규칙을 사용 하도록 설정할](#enable-additional-rules)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-163">You can also [enable more rules](#enable-additional-rules).</span></span>

- <span data-ttu-id="f4cdb-164">각 .NET SDK 버전에 포함 된 규칙 목록은 [Analyzer 릴리스](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-164">For a list of rules that are included with each .NET SDK version, see [Analyzer releases](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).</span></span>
- <span data-ttu-id="f4cdb-165">모든 코드 품질 규칙의 목록은 [코드 품질 규칙](quality-rules/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-165">For a list of all the code quality rules, see [Code quality rules](quality-rules/index.md).</span></span>

### <a name="enable-additional-rules"></a><span data-ttu-id="f4cdb-166">추가 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="f4cdb-166">Enable additional rules</span></span>

<span data-ttu-id="f4cdb-167">*분석 모드* 는 none, some 또는 all 규칙이 설정 된 미리 정의 된 코드 분석 구성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-167">*Analysis mode* refers to a predefined code analysis configuration where none, some, or all rules are enabled.</span></span> <span data-ttu-id="f4cdb-168">기본 분석 모드에서는 적은 수의 규칙만 [빌드 경고로 설정](#enabled-rules)됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-168">In the default analysis mode, only a small number of rules are [enabled as build warnings](#enabled-rules).</span></span> <span data-ttu-id="f4cdb-169">프로젝트 파일에서 [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) 속성을 설정 하 여 프로젝트에 대 한 분석 모드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-169">You can change the analysis mode for your project by setting the [AnalysisMode](../../core/project-sdk/msbuild-props.md#analysismode) property in the project file.</span></span> <span data-ttu-id="f4cdb-170">허용 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-170">The allowable values are:</span></span>

| <span data-ttu-id="f4cdb-171">값</span><span class="sxs-lookup"><span data-stu-id="f4cdb-171">Value</span></span> | <span data-ttu-id="f4cdb-172">설명</span><span class="sxs-lookup"><span data-stu-id="f4cdb-172">Description</span></span> |
| - | - |
| `AllDisabledByDefault` | <span data-ttu-id="f4cdb-173">이는 가장 보수적인 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-173">This is the most conservative mode.</span></span> <span data-ttu-id="f4cdb-174">모든 규칙은 기본적으로 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-174">All rules are disabled by default.</span></span> <span data-ttu-id="f4cdb-175">개별 규칙을 선택적으로 [옵트인](configuration-options.md)하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-175">You can selectively [opt into](configuration-options.md) individual rules to enable them.</span></span><br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | <span data-ttu-id="f4cdb-176">이는 가장 적극적인 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-176">This is the most aggressive mode.</span></span> <span data-ttu-id="f4cdb-177">모든 규칙은 빌드 경고로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-177">All rules are enabled as build warnings.</span></span> <span data-ttu-id="f4cdb-178">개별적으로 사용 하지 않도록 설정 하는 규칙을 선택적으로 [옵트아웃 (opt out](configuration-options.md) ) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-178">You can selectively [opt out of](configuration-options.md) individual rules to disable them.</span></span><br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | <span data-ttu-id="f4cdb-179">기본 모드에서는 몇 가지 규칙을 경고로 사용 하 고, 다른 규칙은 해당 코드 수정이 있는 Visual Studio IDE 제안 으로만 활성화 되며, 나머지는 완전히 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-179">The default mode, where a handful of rules are enabled as warnings, others are enabled only as Visual Studio IDE suggestions with corresponding code fixes, and the rest are disabled completely.</span></span> <span data-ttu-id="f4cdb-180">개별 규칙을 선택적 [으로 옵트인 또는 옵트아웃](configuration-options.md) 하 여 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-180">You can selectively [opt into or out of](configuration-options.md) individual rules to disable them.</span></span><br /><br />`<AnalysisMode>Default</AnalysisMode>` |

<span data-ttu-id="f4cdb-181">사용할 수 있는 각 규칙의 기본 심각도와 규칙을 기본 분석 모드에서 사용할 수 있는지 여부를 확인 하려면 [규칙의 전체 목록을](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-181">To find the default severity for each available rule and whether or not the rule is enabled in the default analysis mode, see the [full list of rules](https://github.com/dotnet/roslyn-analyzers/blob/master/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).</span></span>

### <a name="treat-warnings-as-errors"></a><span data-ttu-id="f4cdb-182">경고를 오류로 처리</span><span class="sxs-lookup"><span data-stu-id="f4cdb-182">Treat warnings as errors</span></span>

<span data-ttu-id="f4cdb-183">프로젝트를 빌드할 때 플래그를 사용 하는 경우 `-warnaserror` 모든 코드 분석 경고도 오류로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-183">If you use the `-warnaserror` flag when you build your projects, all code analysis warnings are also treated as errors.</span></span> <span data-ttu-id="f4cdb-184">CAxxxx (코드 품질 경고)를의 오류로 처리 하지 않으려는 경우 `-warnaserror` `CodeAnalysisTreatWarningsAsErrors` 프로젝트 파일에서 MSBuild 속성을로 설정할 수 있습니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="f4cdb-184">If you do not want code quality warnings (CAxxxx) to be treated as errors in presence of `-warnaserror`, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="f4cdb-185">코드 분석 경고가 계속 표시 되지만 빌드를 중단 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-185">You'll still see any code analysis warnings, but they won't break your build.</span></span>

### <a name="latest-updates"></a><span data-ttu-id="f4cdb-186">최신 업데이트</span><span class="sxs-lookup"><span data-stu-id="f4cdb-186">Latest updates</span></span>

<span data-ttu-id="f4cdb-187">최신 버전의 .NET SDK로 업그레이드 하는 경우 기본적으로 최신 코드 분석 규칙 및 기본 규칙 심각도가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-187">By default, you'll get the latest code analysis rules and default rule severities as you upgrade to newer versions of the .NET SDK.</span></span> <span data-ttu-id="f4cdb-188">이 동작을 원하지 않는 경우, 예를 들어 새 규칙을 사용 하거나 사용 하지 않도록 설정 하려는 경우 다음 방법 중 하나를 사용 하 여 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-188">If you don't want this behavior, for example, if you want to ensure that no new rules are enabled or disabled, you can override it in one of the following ways:</span></span>

- <span data-ttu-id="f4cdb-189">`AnalysisLevel`MSBuild 속성을 특정 값으로 설정 하 여 해당 집합에 대 한 경고를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-189">Set the `AnalysisLevel` MSBuild property to a specific value to lock the warnings to that set.</span></span> <span data-ttu-id="f4cdb-190">최신 SDK로 업그레이드 하는 경우 해당 경고에 대 한 버그 수정이 계속 표시 되지만 새 경고는 사용할 수 없으며, 기존 경고는 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-190">When you upgrade to a newer SDK, you'll still get bug fixes for those warnings, but no new warnings will be enabled and no existing warnings will be disabled.</span></span> <span data-ttu-id="f4cdb-191">예를 들어 .NET SDK 버전 5.0와 함께 제공 되는 규칙 집합을 잠그려면 프로젝트 파일에 다음 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-191">For example, to lock the set of rules to those that ship with version 5.0 of the .NET SDK, add the following entry to your project file.</span></span>

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > <span data-ttu-id="f4cdb-192">속성의 기본값은 `AnalysisLevel` 입니다 `latest` . 즉, 최신 버전의 .net SDK로 이동할 때 항상 최신 코드 분석 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-192">The default value for the `AnalysisLevel` property is `latest`, which means you always get the latest code analysis rules as you move to newer versions of the .NET SDK.</span></span>

  <span data-ttu-id="f4cdb-193">자세한 내용 및 가능한 값 목록을 보려면 [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-193">For more information, and to see a list of possible values, see [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).</span></span>

- <span data-ttu-id="f4cdb-194">[Microsoft CodeAnalysis NuGet 패키지](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) 를 설치 하 여 .net SDK 업데이트에서 규칙 업데이트를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-194">Install the [Microsoft.CodeAnalysis.NetAnalyzers NuGet package](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) to decouple rule updates from .NET SDK updates.</span></span> <span data-ttu-id="f4cdb-195">패키지를 설치 하면 기본 제공 SDK 분석기가 해제 되 고 SDK에 NuGet 패키지의 최신 분석기 어셈블리 버전이 포함 되어 있으면 빌드 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-195">Installing the package turns off the built-in SDK analyzers and generates a build warning if the SDK contains a newer analyzer assembly version than that of the NuGet package.</span></span>

## <a name="code-style-analysis"></a><span data-ttu-id="f4cdb-196">코드 스타일 분석</span><span class="sxs-lookup"><span data-stu-id="f4cdb-196">Code style analysis</span></span>

<span data-ttu-id="f4cdb-197">*코드 스타일 분석* ("IDExxxx") 규칙을 사용 하 여 코드 베이스에서 일관 된 코드 스타일을 정의 하 고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-197">*Code style analysis* ("IDExxxx") rules enable you to define and maintain consistent code style in your codebase.</span></span> <span data-ttu-id="f4cdb-198">기본 설정 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-198">The default enablement settings are:</span></span>

- <span data-ttu-id="f4cdb-199">명령줄 빌드: 명령줄 빌드의 모든 .NET 프로젝트에 대해 코드 스타일 분석이 기본적으로 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-199">Command line build: Code style analysis is disabled, by default, for all .NET projects on command-line builds.</span></span>
- <span data-ttu-id="f4cdb-200">Visual Studio: 코드 스타일 분석은 기본적으로 Visual Studio 내의 모든 .NET 프로젝트에 대해 [코드 리팩터링 빠른 작업](/visualstudio/ide/code-generation-in-visual-studio)으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-200">Visual Studio: Code style analysis is enabled, by default, for all .NET projects inside Visual Studio as [code refactoring quick actions](/visualstudio/ide/code-generation-in-visual-studio).</span></span>

<span data-ttu-id="f4cdb-201">.NET 5.0를 시작 하면 명령줄 및 Visual Studio 내에서 빌드에 대 한 코드 스타일 분석을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-201">Starting .NET 5.0, you can enable code style analysis on build, both at the command line and inside Visual Studio.</span></span> <span data-ttu-id="f4cdb-202">코드 스타일 위반은 "IDE" 접두사를 사용 하 여 경고나 오류로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-202">Code style violations appear as warnings or errors with an "IDE" prefix.</span></span> <span data-ttu-id="f4cdb-203">이렇게 하면 빌드 시 일관 된 코드 스타일을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-203">This enables you to enforce consistent code styles at build time.</span></span>

<span data-ttu-id="f4cdb-204">코드 스타일 분석 규칙의 전체 목록은 [코드 스타일 규칙](style-rules/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-204">For a full list of code-style analysis rules, see [Code style rules](style-rules/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f4cdb-205">코드 스타일 분석 기능은 실험적 이며 .NET 5와 .NET 6 릴리스 사이에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-205">The code style analysis feature is experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="f4cdb-206">빌드에서 코드 스타일 분석을 사용 하도록 설정 하는 단계:</span><span class="sxs-lookup"><span data-stu-id="f4cdb-206">Steps to enable code style analysis on build:</span></span>

1. <span data-ttu-id="f4cdb-207">MSBuild 속성 [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) 을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-207">Set the MSBuild property [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) to `true`.</span></span>

1. <span data-ttu-id="f4cdb-208">*Editorconfig* 파일에서 빌드에서 실행 하려는 각 "IDE" 코드 스타일 규칙을 경고나 오류로 [구성](configuration-options.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-208">In an *.editorconfig* file, [configure](configuration-options.md) each "IDE" code style rule that you wish to run on build as a warning or an error.</span></span> <span data-ttu-id="f4cdb-209">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f4cdb-209">For example:</span></span>

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   <span data-ttu-id="f4cdb-210">또는 기본적으로 전체 "스타일" 범주를 경고 또는 오류로 구성 하 고 빌드 시 실행 하지 않을 규칙을 선택적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-210">Alternatively, you can configure the entire "Style" category to be a warning or error, by default, and then selectively turn off rules that you don't want to run on build.</span></span> <span data-ttu-id="f4cdb-211">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f4cdb-211">For example:</span></span>

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

## <a name="suppress-a-warning"></a><span data-ttu-id="f4cdb-212">경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="f4cdb-212">Suppress a warning</span></span>

<span data-ttu-id="f4cdb-213">규칙 위반을 억제 하려면 EditorConfig 파일에서 해당 규칙 ID의 심각도 옵션을로 설정 `none` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-213">To suppress a rule violation, set the severity option for that rule ID to `none` in an EditorConfig file.</span></span> <span data-ttu-id="f4cdb-214">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f4cdb-214">For example:</span></span>

```ini
dotnet_diagnostic.CA1822.severity = none
```

<span data-ttu-id="f4cdb-215">Visual Studio에서는 코드 분석 규칙에서 경고를 표시 하지 않도록 하는 추가 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-215">Visual Studio provides additional ways to suppress warnings from code analysis rules.</span></span> <span data-ttu-id="f4cdb-216">자세한 내용은 [위반 표시 안 함](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-216">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span></span>

<span data-ttu-id="f4cdb-217">규칙 심각도에 대 한 자세한 내용은 [규칙 심각도 구성](configuration-options.md#severity-level)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-217">For more information about rule severities, see [Configure rule severity](configuration-options.md#severity-level).</span></span>

## <a name="third-party-analyzers"></a><span data-ttu-id="f4cdb-218">타사 분석기</span><span class="sxs-lookup"><span data-stu-id="f4cdb-218">Third-party analyzers</span></span>

<span data-ttu-id="f4cdb-219">공식 .NET 분석기 외에도 [StyleCop,](https://www.nuget.org/packages/StyleCop.Analyzers/) [rosl](https://www.nuget.org/packages/Roslynator.Analyzers/), [Xunit 분석기](https://www.nuget.org/packages/xunit.analyzers/)및 [sonar.projectname) Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/)와 같은 타사 분석기를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4cdb-219">In addition to the official .NET analyzers, you can also install third party analyzers, such as [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [XUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/), and [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4cdb-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4cdb-220">See also</span></span>

- [<span data-ttu-id="f4cdb-221">코드 품질 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="f4cdb-221">Code quality analysis rule reference</span></span>](quality-rules/index.md)
- [<span data-ttu-id="f4cdb-222">코드 스타일 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="f4cdb-222">Code style analysis rule reference</span></span>](style-rules/index.md)
- [<span data-ttu-id="f4cdb-223">Visual Studio의 코드 분석</span><span class="sxs-lookup"><span data-stu-id="f4cdb-223">Code analysis in Visual Studio</span></span>](/visualstudio/code-quality/roslyn-analyzers-overview)
- [<span data-ttu-id="f4cdb-224">.NET Compiler Platform SDK</span><span class="sxs-lookup"><span data-stu-id="f4cdb-224">.NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="f4cdb-225">자습서: 첫 번째 분석기 및 코드 수정 작성</span><span class="sxs-lookup"><span data-stu-id="f4cdb-225">Tutorial: Write your first analyzer and code fix</span></span>](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
