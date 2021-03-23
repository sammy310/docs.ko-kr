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
ms.openlocfilehash: 1a0b31f7aca6415510ed0fcd08e9f9a0f8f39bf5
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876606"
---
# <a name="overview-of-net-source-code-analysis"></a><span data-ttu-id="e4a6b-103">.NET 소스 코드 분석 개요</span><span class="sxs-lookup"><span data-stu-id="e4a6b-103">Overview of .NET source code analysis</span></span>

<span data-ttu-id="e4a6b-104">.NET Compiler Platform(Roslyn) 분석기는 C# 또는 Visual Basic 코드를 검사하여 코드 품질 및 스타일 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-104">.NET compiler platform (Roslyn) analyzers inspect your C# or Visual Basic code for code quality and style issues.</span></span> <span data-ttu-id="e4a6b-105">.NET 5.0부터는 Roslyn 분석기가 .NET SDK에 포함되므로 별도로 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-105">Starting in .NET 5.0, these analyzers are included with the .NET SDK and you don't need to install them separately.</span></span> <span data-ttu-id="e4a6b-106">프로젝트가 .NET 5 이상을 대상으로 하는 경우 기본적으로 코드 분석이 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-106">If your project targets .NET 5 or later, code analysis is enabled by default.</span></span> <span data-ttu-id="e4a6b-107">프로젝트가 .NET Core, .NET Standard 또는 .NET Framework 같은 다른 .NET 구현을 대상으로 하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 `true`로 설정하여 코드 분석을 사용하도록 수동으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-107">If your project targets a different .NET implementation, for example, .NET Core, .NET Standard, or .NET Framework, you must manually enable code analysis by setting the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to `true`.</span></span>

<span data-ttu-id="e4a6b-108">.NET 5 이상 SDK로 이동하지 않거나, SDK 스타일이 아닌 .NET Framework 프로젝트를 사용하거나, NuGet 패키지 기반 모델을 선호하는 경우 [Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)에서도 분석기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-108">If you don't want to move to the .NET 5+ SDK, have a non-SDK-style .NET Framework project, or prefer a NuGet package-based model, the analyzers are also available in the [Microsoft.CodeAnalysis.NetAnalyzers NuGet package](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers).</span></span> <span data-ttu-id="e4a6b-109">주문형 버전 업데이트에는 패키지 기반 모델을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-109">You might prefer a package-based model for on-demand version updates.</span></span>

> [!NOTE]
> <span data-ttu-id="e4a6b-110">.NET 분석기는 대상 프레임워크에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-110">.NET analyzers are target-framework agnostic.</span></span> <span data-ttu-id="e4a6b-111">즉, 프로젝트에서 특정 .NET 구현을 대상으로 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-111">That is, your project does not need to target a specific .NET implementation.</span></span> <span data-ttu-id="e4a6b-112">분석기는 이전 .NET 버전(예: `netcoreapp3.1` 및 `net472`)뿐만 아니라 `net5.0`을 대상으로 하는 프로젝트에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-112">The analyzers work for projects that target `net5.0` as well as earlier .NET versions, such as `netcoreapp3.1` and `net472`.</span></span> <span data-ttu-id="e4a6b-113">그러나 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 사용하여 코드 분석을 사용하도록 설정하려면 프로젝트에서 [프로젝트 SDK](../../core/project-sdk/overview.md)를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-113">However, to enable code analysis using the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property, your project must reference a [project SDK](../../core/project-sdk/overview.md).</span></span>

<span data-ttu-id="e4a6b-114">분석기에서 규칙 위반이 발생하는 경우 각 규칙이 [구성](configuration-options.md)된 방법에 따라 제안, 경고, 오류로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-114">If rule violations are found by an analyzer, they're reported as a suggestion, warning, or error, depending on how each rule is [configured](configuration-options.md).</span></span> <span data-ttu-id="e4a6b-115">코드 분석 위반은 컴파일러 오류와 구별하기 위해 “CA” 또는 “IDE” 접두사를 사용하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-115">Code analysis violations appear with the prefix "CA" or "IDE" to differentiate them from compiler errors.</span></span>

## <a name="code-quality-analysis"></a><span data-ttu-id="e4a6b-116">코드 품질 분석</span><span class="sxs-lookup"><span data-stu-id="e4a6b-116">Code quality analysis</span></span>

<span data-ttu-id="e4a6b-117">‘코드 품질 분석’(“CAxxxx”) 규칙은 C# 또는 Visual Basic 코드를 검사하여 보안, 성능, 디자인, 기타 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-117">*Code quality analysis* ("CAxxxx") rules inspect your C# or Visual Basic code for security, performance, design and other issues.</span></span> <span data-ttu-id="e4a6b-118">.NET 5.0 이상을 대상으로 하는 프로젝트의 경우 기본적으로 분석을 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-118">Analysis is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="e4a6b-119">[EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 `true`로 설정하여 이전 버전의 .NET을 대상으로 하는 프로젝트에서 코드 분석을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-119">You can enable code analysis on projects that target earlier .NET versions by setting the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to `true`.</span></span> <span data-ttu-id="e4a6b-120">`EnableNETAnalyzers`를 `false`로 설정하여 프로젝트에서 코드 분석을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-120">You can also disable code analysis for your project by setting `EnableNETAnalyzers` to `false`.</span></span>

> [!TIP]
> <span data-ttu-id="e4a6b-121">Visual Studio를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="e4a6b-121">If you're using Visual Studio:</span></span>
>
> - <span data-ttu-id="e4a6b-122">여러 분석기 규칙에는 문제를 해결하는 데 적용할 수 있는 관련 ‘코드 수정 사항’이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-122">Many analyzer rules have associated *code fixes* that you can apply to correct the problem.</span></span> <span data-ttu-id="e4a6b-123">코드 수정 사항은 전구 아이콘 메뉴에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-123">Code fixes are shown in the light bulb icon menu.</span></span>
> - <span data-ttu-id="e4a6b-124">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** > **코드 분석** 탭 > **.NET 분석기 사용** 을 선택하여 코드 분석을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-124">You can enable or disable code analysis by right-clicking on a project in Solution Explorer and selecting **Properties** > **Code Analysis** tab > **Enable .NET analyzers**.</span></span>

### <a name="enabled-rules"></a><span data-ttu-id="e4a6b-125">사용 가능한 규칙</span><span class="sxs-lookup"><span data-stu-id="e4a6b-125">Enabled rules</span></span>

<span data-ttu-id="e4a6b-126">.NET 5.0에서는 기본적으로 다음 규칙이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-126">The following rules are enabled, by default, in .NET 5.0.</span></span>

| <span data-ttu-id="e4a6b-127">진단 ID</span><span class="sxs-lookup"><span data-stu-id="e4a6b-127">Diagnostic ID</span></span> | <span data-ttu-id="e4a6b-128">범주</span><span class="sxs-lookup"><span data-stu-id="e4a6b-128">Category</span></span> | <span data-ttu-id="e4a6b-129">심각도</span><span class="sxs-lookup"><span data-stu-id="e4a6b-129">Severity</span></span> | <span data-ttu-id="e4a6b-130">설명</span><span class="sxs-lookup"><span data-stu-id="e4a6b-130">Description</span></span> |
| - | - | - | - |
| [<span data-ttu-id="e4a6b-131">CA1416</span><span class="sxs-lookup"><span data-stu-id="e4a6b-131">CA1416</span></span>](/visualstudio/code-quality/ca1416) | <span data-ttu-id="e4a6b-132">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-132">Interoperability</span></span> | <span data-ttu-id="e4a6b-133">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-133">Warning</span></span> | <span data-ttu-id="e4a6b-134">플랫폼 호환성 분석기</span><span class="sxs-lookup"><span data-stu-id="e4a6b-134">Platform compatibility analyzer</span></span> |
| [<span data-ttu-id="e4a6b-135">CA1417</span><span class="sxs-lookup"><span data-stu-id="e4a6b-135">CA1417</span></span>](/visualstudio/code-quality/ca1417) | <span data-ttu-id="e4a6b-136">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-136">Interoperability</span></span> | <span data-ttu-id="e4a6b-137">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-137">Warning</span></span> | <span data-ttu-id="e4a6b-138">P/Invokes에 대한 문자열 매개 변수에서 `OutAttribute`를 사용하지 않음</span><span class="sxs-lookup"><span data-stu-id="e4a6b-138">Do not use `OutAttribute` on string parameters for P/Invokes</span></span> |
| [<span data-ttu-id="e4a6b-139">CA1831</span><span class="sxs-lookup"><span data-stu-id="e4a6b-139">CA1831</span></span>](/visualstudio/code-quality/ca1831) | <span data-ttu-id="e4a6b-140">성능</span><span class="sxs-lookup"><span data-stu-id="e4a6b-140">Performance</span></span> | <span data-ttu-id="e4a6b-141">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-141">Warning</span></span> | <span data-ttu-id="e4a6b-142">해당하는 경우 문자열에 범위 기반 인덱서 대신 `AsSpan` 사용</span><span class="sxs-lookup"><span data-stu-id="e4a6b-142">Use `AsSpan` instead of range-based indexers for string when appropriate</span></span> |
| [<span data-ttu-id="e4a6b-143">CA2013</span><span class="sxs-lookup"><span data-stu-id="e4a6b-143">CA2013</span></span>](/visualstudio/code-quality/ca2013) | <span data-ttu-id="e4a6b-144">안정성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-144">Reliability</span></span> | <span data-ttu-id="e4a6b-145">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-145">Warning</span></span> | <span data-ttu-id="e4a6b-146">값 형식에 `ReferenceEquals`를 사용하지 않음</span><span class="sxs-lookup"><span data-stu-id="e4a6b-146">Do not use `ReferenceEquals` with value types</span></span> |
| [<span data-ttu-id="e4a6b-147">CA2014</span><span class="sxs-lookup"><span data-stu-id="e4a6b-147">CA2014</span></span>](/visualstudio/code-quality/ca2014) | <span data-ttu-id="e4a6b-148">안정성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-148">Reliability</span></span> | <span data-ttu-id="e4a6b-149">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-149">Warning</span></span> | <span data-ttu-id="e4a6b-150">루프에서 `stackalloc`을 사용하지 않음</span><span class="sxs-lookup"><span data-stu-id="e4a6b-150">Do not use `stackalloc` in loops</span></span> |
| [<span data-ttu-id="e4a6b-151">CA2015</span><span class="sxs-lookup"><span data-stu-id="e4a6b-151">CA2015</span></span>](/visualstudio/code-quality/ca2015) | <span data-ttu-id="e4a6b-152">안정성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-152">Reliability</span></span> | <span data-ttu-id="e4a6b-153">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-153">Warning</span></span> | <span data-ttu-id="e4a6b-154"><xref:System.Buffers.MemoryManager%601>에서 파생된 형식에 대해 종료자를 정의하지 않음</span><span class="sxs-lookup"><span data-stu-id="e4a6b-154">Do not define finalizers for types derived from <xref:System.Buffers.MemoryManager%601></span></span> |
| [<span data-ttu-id="e4a6b-155">CA2200</span><span class="sxs-lookup"><span data-stu-id="e4a6b-155">CA2200</span></span>](/visualstudio/code-quality/ca2200) | <span data-ttu-id="e4a6b-156">사용량</span><span class="sxs-lookup"><span data-stu-id="e4a6b-156">Usage</span></span> | <span data-ttu-id="e4a6b-157">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-157">Warning</span></span> | <span data-ttu-id="e4a6b-158">스택 정보를 유지하도록 다시 throw하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-158">Rethrow to preserve stack details</span></span>
| [<span data-ttu-id="e4a6b-159">CA2247</span><span class="sxs-lookup"><span data-stu-id="e4a6b-159">CA2247</span></span>](/visualstudio/code-quality/ca2247) | <span data-ttu-id="e4a6b-160">사용량</span><span class="sxs-lookup"><span data-stu-id="e4a6b-160">Usage</span></span> | <span data-ttu-id="e4a6b-161">경고</span><span class="sxs-lookup"><span data-stu-id="e4a6b-161">Warning</span></span> | <span data-ttu-id="e4a6b-162">TaskCompletionSource 생성자에 전달되는 인수는 <xref:System.Threading.Tasks.TaskContinuationOptions>가 아닌 <xref:System.Threading.Tasks.TaskCreationOptions> 열거형이어야 함</span><span class="sxs-lookup"><span data-stu-id="e4a6b-162">Argument passed to TaskCompletionSource constructor should be <xref:System.Threading.Tasks.TaskCreationOptions> enum instead of <xref:System.Threading.Tasks.TaskContinuationOptions></span></span> |

<span data-ttu-id="e4a6b-163">이러한 규칙의 심각도를 변경하여 사용하지 않도록 설정하거나 오류로 수준을 올릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-163">You can change the severity of these rules to disable them or elevate them to errors.</span></span> <span data-ttu-id="e4a6b-164">[더 많은 규칙을 사용하도록 설정](#enable-additional-rules)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-164">You can also [enable more rules](#enable-additional-rules).</span></span>

- <span data-ttu-id="e4a6b-165">각 .NET SDK 버전에 포함된 규칙 목록은 [분석기 릴리스](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-165">For a list of rules that are included with each .NET SDK version, see [Analyzer releases](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).</span></span>
- <span data-ttu-id="e4a6b-166">모든 코드 품질 규칙 목록은 [코드 품질 규칙](quality-rules/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-166">For a list of all the code quality rules, see [Code quality rules](quality-rules/index.md).</span></span>

### <a name="enable-additional-rules"></a><span data-ttu-id="e4a6b-167">추가 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="e4a6b-167">Enable additional rules</span></span>

<span data-ttu-id="e4a6b-168">‘분석 모드’는 사용하도록 설정된 규칙이 없거나 일부 또는 모든 규칙이 사용하도록 설정된 미리 정의된 코드 분석 구성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-168">*Analysis mode* refers to a predefined code analysis configuration where none, some, or all rules are enabled.</span></span> <span data-ttu-id="e4a6b-169">기본 분석 모드에서는 적은 수의 규칙만 [빌드 경고로 사용하도록 설정](#enabled-rules)됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-169">In the default analysis mode, only a small number of rules are [enabled as build warnings](#enabled-rules).</span></span> <span data-ttu-id="e4a6b-170">프로젝트 파일에서 [\<AnalysisMode>](../../core/project-sdk/msbuild-props.md#analysismode) 속성을 설정하여 프로젝트의 분석 모드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-170">You can change the analysis mode for your project by setting the [\<AnalysisMode>](../../core/project-sdk/msbuild-props.md#analysismode) property in the project file.</span></span> <span data-ttu-id="e4a6b-171">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-171">The allowable values are:</span></span>

| <span data-ttu-id="e4a6b-172">값</span><span class="sxs-lookup"><span data-stu-id="e4a6b-172">Value</span></span> | <span data-ttu-id="e4a6b-173">설명</span><span class="sxs-lookup"><span data-stu-id="e4a6b-173">Description</span></span> |
| - | - |
| `AllDisabledByDefault` | <span data-ttu-id="e4a6b-174">가장 보수적인 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-174">This is the most conservative mode.</span></span> <span data-ttu-id="e4a6b-175">기본적으로 모든 규칙이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-175">All rules are disabled by default.</span></span> <span data-ttu-id="e4a6b-176">개별 규칙을 선택적으로 [옵트인](configuration-options.md)하여 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-176">You can selectively [opt into](configuration-options.md) individual rules to enable them.</span></span><br /><br />`<AnalysisMode>AllDisabledByDefault</AnalysisMode>` |
| `AllEnabledByDefault` | <span data-ttu-id="e4a6b-177">가장 적극적인 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-177">This is the most aggressive mode.</span></span> <span data-ttu-id="e4a6b-178">모든 규칙이 빌드 경고로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-178">All rules are enabled as build warnings.</span></span> <span data-ttu-id="e4a6b-179">개별 규칙을 선택적으로 [옵트아웃](configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-179">You can selectively [opt out of](configuration-options.md) individual rules to disable them.</span></span><br /><br />`<AnalysisMode>AllEnabledByDefault</AnalysisMode>` |
| `Default` | <span data-ttu-id="e4a6b-180">기본 모드로, 몇 가지 규칙은 경고로 사용하도록 설정되고 다른 규칙은 해당하는 코드 수정 사항이 있는 Visual Studio IDE 제안으로만 사용하도록 설정되며 나머지는 완전히 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-180">The default mode, where a handful of rules are enabled as warnings, others are enabled only as Visual Studio IDE suggestions with corresponding code fixes, and the rest are disabled completely.</span></span> <span data-ttu-id="e4a6b-181">개별 규칙을 선택적으로 [옵트인 또는 옵트아웃](configuration-options.md)하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-181">You can selectively [opt into or out of](configuration-options.md) individual rules to disable them.</span></span><br /><br />`<AnalysisMode>Default</AnalysisMode>` |

<span data-ttu-id="e4a6b-182">사용할 수 있는 각 규칙의 기본 심각도와 기본 분석 모드에서 규칙을 사용할 수 있는지를 확인하려면 [규칙 전체 목록](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-182">To find the default severity for each available rule and whether or not the rule is enabled in the default analysis mode, see the [full list of rules](https://github.com/dotnet/roslyn-analyzers/blob/main/src/NetAnalyzers/Core/AnalyzerReleases.Shipped.md).</span></span>

### <a name="treat-warnings-as-errors"></a><span data-ttu-id="e4a6b-183">경고를 오류로 처리</span><span class="sxs-lookup"><span data-stu-id="e4a6b-183">Treat warnings as errors</span></span>

<span data-ttu-id="e4a6b-184">프로젝트를 빌드할 때 `-warnaserror` 플래그를 사용하면 모든 코드 분석 경고도 오류로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-184">If you use the `-warnaserror` flag when you build your projects, all code analysis warnings are also treated as errors.</span></span> <span data-ttu-id="e4a6b-185">`-warnaserror`가 있을 경우 코드 품질 경고(CAxxxx)가 오류로 처리되지 않도록 하려면 프로젝트 파일에서 `CodeAnalysisTreatWarningsAsErrors` MSBuild 속성을 `false`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-185">If you do not want code quality warnings (CAxxxx) to be treated as errors in presence of `-warnaserror`, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="e4a6b-186">코드 분석 경고는 계속 표시되지만 빌드를 중단하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-186">You'll still see any code analysis warnings, but they won't break your build.</span></span>

### <a name="latest-updates"></a><span data-ttu-id="e4a6b-187">최신 업데이트</span><span class="sxs-lookup"><span data-stu-id="e4a6b-187">Latest updates</span></span>

<span data-ttu-id="e4a6b-188">기본적으로 최신 버전의 .NET SDK로 업그레이드하면 최신 코드 분석 규칙 및 기본 규칙 심각도가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-188">By default, you'll get the latest code analysis rules and default rule severities as you upgrade to newer versions of the .NET SDK.</span></span> <span data-ttu-id="e4a6b-189">새 규칙을 사용하거나 사용하지 않도록 설정하지 않으려는 경우처럼 이 동작을 원하지 않는 경우 다음 방법 중 하나를 사용하여 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-189">If you don't want this behavior, for example, if you want to ensure that no new rules are enabled or disabled, you can override it in one of the following ways:</span></span>

- <span data-ttu-id="e4a6b-190">`AnalysisLevel` MSBuild 속성을 특정 값으로 설정하여 해당 집합에 대한 경고를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-190">Set the `AnalysisLevel` MSBuild property to a specific value to lock the warnings to that set.</span></span> <span data-ttu-id="e4a6b-191">최신 SDK로 업그레이드하는 경우 해당 경고에 대한 버그 수정이 계속 표시되지만 새 경고는 사용하도록 설정되지 않고 기존 경고는 사용하지 않도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-191">When you upgrade to a newer SDK, you'll still get bug fixes for those warnings, but no new warnings will be enabled and no existing warnings will be disabled.</span></span> <span data-ttu-id="e4a6b-192">예를 들어 규칙 세트를 .NET SDK 버전 5.0과 함께 제공되는 규칙으로 잠그려면 프로젝트 파일에 다음 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-192">For example, to lock the set of rules to those that ship with version 5.0 of the .NET SDK, add the following entry to your project file.</span></span>

  ```xml
  <PropertyGroup>
    <AnalysisLevel>5.0</AnalysisLevel>
  </PropertyGroup>
  ```

  > [!TIP]
  > <span data-ttu-id="e4a6b-193">`AnalysisLevel` 속성의 기본값은 `latest`입니다. 즉, 최신 버전의 .NET SDK로 이동하면 항상 최신 코드 분석 규칙이 제공된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-193">The default value for the `AnalysisLevel` property is `latest`, which means you always get the latest code analysis rules as you move to newer versions of the .NET SDK.</span></span>

  <span data-ttu-id="e4a6b-194">자세한 내용 및 가능한 값 목록은 [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-194">For more information, and to see a list of possible values, see [AnalysisLevel](../../core/project-sdk/msbuild-props.md#analysislevel).</span></span>

- <span data-ttu-id="e4a6b-195">[Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers)를 설치하여 .NET SDK 업데이트에서 규칙 업데이트를 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-195">Install the [Microsoft.CodeAnalysis.NetAnalyzers NuGet package](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) to decouple rule updates from .NET SDK updates.</span></span> <span data-ttu-id="e4a6b-196">.NET 5 이상을 대상으로 하는 프로젝트에서는 패키지를 설치하면 기본 제공 SDK 분석기가 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-196">For projects that target .NET 5+, installing the package turns off the built-in SDK analyzers.</span></span> <span data-ttu-id="e4a6b-197">SDK에 NuGet 패키지 버전보다 최신인 분석기 어셈블리 버전이 포함되어 있으면 빌드 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-197">You'll get a build warning if the SDK contains a newer analyzer assembly version than that of the NuGet package.</span></span> <span data-ttu-id="e4a6b-198">이 경고를 사용하지 않도록 설정하려면 `_SkipUpgradeNetAnalyzersNuGetWarning` 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-198">To disable the warning, set the `_SkipUpgradeNetAnalyzersNuGetWarning` property to `true`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e4a6b-199">Microsoft.CodeAnalysis.NetAnalyzers NuGet 패키지를 설치하는 경우 [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) 속성을 프로젝트 파일이나 *Directory.Build.props* 파일에 추가하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-199">If you install the Microsoft.CodeAnalysis.NetAnalyzers NuGet package, you should not add the [EnableNETAnalyzers](../../core/project-sdk/msbuild-props.md#enablenetanalyzers) property to either your project file or a *Directory.Build.props* file.</span></span> <span data-ttu-id="e4a6b-200">NuGet 패키지를 설치하고 `EnableNETAnalyzers` 속성을 `true`로 설정하면 빌드 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-200">When the NuGet package is installed and the `EnableNETAnalyzers` property is set to `true`, a build warning is generated.</span></span>

## <a name="code-style-analysis"></a><span data-ttu-id="e4a6b-201">코드 스타일 분석</span><span class="sxs-lookup"><span data-stu-id="e4a6b-201">Code-style analysis</span></span>

<span data-ttu-id="e4a6b-202">‘코드 스타일 분석’(“IDExxxx”) 규칙을 사용하면 코드베이스에서 일관된 코드 스타일을 정의하고 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-202">*Code-style analysis* ("IDExxxx") rules enable you to define and maintain consistent code style in your codebase.</span></span> <span data-ttu-id="e4a6b-203">기본 사용 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-203">The default enablement settings are:</span></span>

- <span data-ttu-id="e4a6b-204">명령줄 빌드: 코드 스타일 분석은 명령줄 빌드의 모든 .NET 프로젝트에 대해 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-204">Command-line build: Code-style analysis is disabled, by default, for all .NET projects on command-line builds.</span></span>

  <span data-ttu-id="e4a6b-205">.NET 5.0부터 명령줄 및 Visual Studio 내에서 [빌드에서 코드 스타일 분석을 사용하도록 설정](#enable-on-build)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-205">Starting in .NET 5.0, you can [enable code-style analysis on build](#enable-on-build), both at the command line and inside Visual Studio.</span></span> <span data-ttu-id="e4a6b-206">코드 스타일 위반은 “IDE” 접두사를 사용하는 경고 또는 오류로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-206">Code style violations appear as warnings or errors with an "IDE" prefix.</span></span> <span data-ttu-id="e4a6b-207">이렇게 하면 빌드 시 일관된 코드 스타일을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-207">This enables you to enforce consistent code styles at build time.</span></span>

- <span data-ttu-id="e4a6b-208">Visual Studio: 코드 스타일 분석은 기본적으로 Visual Studio 내의 모든 .NET 프로젝트에 대해 [코드 리팩터링 빠른 작업](/visualstudio/ide/code-generation-in-visual-studio)으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-208">Visual Studio: Code-style analysis is enabled, by default, for all .NET projects inside Visual Studio as [code refactoring quick actions](/visualstudio/ide/code-generation-in-visual-studio).</span></span>

<span data-ttu-id="e4a6b-209">코드 스타일 분석 규칙의 전체 목록은 [코드 스타일 규칙](style-rules/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-209">For a full list of code-style analysis rules, see [Code style rules](style-rules/index.md).</span></span>

### <a name="enable-on-build"></a><span data-ttu-id="e4a6b-210">빌드 시 사용</span><span class="sxs-lookup"><span data-stu-id="e4a6b-210">Enable on build</span></span>

<span data-ttu-id="e4a6b-211">.NET 5.0 SDK 이상 버전에서는 명령줄 및 Visual Studio에서 빌드할 때 코드 스타일 분석을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-211">With the .NET 5.0 SDK and later versions, you can enable code-style analysis when building from the command-line and in Visual Studio.</span></span> <span data-ttu-id="e4a6b-212">그러나 성능상의 이유로 [몇 가지 코드 스타일 규칙](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95)은 Visual Studio IDE에서만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-212">(However, for performance reasons, [a handful of code-style rules](https://github.com/dotnet/roslyn/blob/9f87b444da9c48a4d492b19f8337339056bf2b95/src/Analyzers/Core/Analyzers/EnforceOnBuildValues.cs#L95) will still apply only in the Visual Studio IDE.)</span></span>

<span data-ttu-id="e4a6b-213">빌드 시 코드 스타일 분석을 사용하도록 설정하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-213">Follow these steps to enable code-style analysis on build:</span></span>

1. <span data-ttu-id="e4a6b-214">MSBuild 속성 [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild)를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-214">Set the MSBuild property [EnforceCodeStyleInBuild](../../core/project-sdk/msbuild-props.md#enforcecodestyleinbuild) to `true`.</span></span>

1. <span data-ttu-id="e4a6b-215">*.editorconfig* 파일에서 빌드 시 실행하려는 각 “IDE” 코드 스타일 규칙을 경고 또는 오류로 [구성](configuration-options.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-215">In an *.editorconfig* file, [configure](configuration-options.md) each "IDE" code style rule that you wish to run on build as a warning or an error.</span></span> <span data-ttu-id="e4a6b-216">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-216">For example:</span></span>

   ```ini
   [*.{cs,vb}]
   # IDE0040: Accessibility modifiers required (escalated to a build warning)
   dotnet_diagnostic.IDE0040.severity = warning
   ```

   <span data-ttu-id="e4a6b-217">또는 기본적으로 전체 범주를 경고 또는 오류로 구성한 다음, 해당 범주에서 빌드 시 실행하지 않으려는 규칙을 선택적으로 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-217">Alternatively, you can configure an entire category to be a warning or error, by default, and then selectively turn off rules in that category that you don't want to run on build.</span></span> <span data-ttu-id="e4a6b-218">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-218">For example:</span></span>

   ```ini
   [*.{cs,vb}]

   # Default severity for analyzer diagnostics with category 'Style' (escalated to build warnings)
   dotnet_analyzer_diagnostic.category-Style.severity = warning

   # IDE0040: Accessibility modifiers required (disabled on build)
   dotnet_diagnostic.IDE0040.severity = silent
   ```

> [!NOTE]
> <span data-ttu-id="e4a6b-219">코드 스타일 분석 기능은 시험용으로 제공되며 .NET 5 릴리스와 .NET 6 릴리스 사이에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-219">The code-style analysis feature is experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

## <a name="suppress-a-warning"></a><span data-ttu-id="e4a6b-220">경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="e4a6b-220">Suppress a warning</span></span>

<span data-ttu-id="e4a6b-221">규칙 위반을 표시하지 않는 한 가지 방법은 EditorConfig 파일에서 해당 규칙 ID에 대한 심각도 옵션을 `none`으로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-221">One way to suppress a rule violation is to set the severity option for that rule ID to `none` in an EditorConfig file.</span></span> <span data-ttu-id="e4a6b-222">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-222">For example:</span></span>

```ini
dotnet_diagnostic.CA1822.severity = none
```

<span data-ttu-id="e4a6b-223">경고를 표시하지 않는 다른 방법 및 자세한 내용은 [코드 분석 경고를 표시하지 않는 방법](suppress-warnings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-223">For more information and other ways to suppress warnings, see [How to suppress code analysis warnings](suppress-warnings.md).</span></span>

## <a name="third-party-analyzers"></a><span data-ttu-id="e4a6b-224">타사 분석기</span><span class="sxs-lookup"><span data-stu-id="e4a6b-224">Third-party analyzers</span></span>

<span data-ttu-id="e4a6b-225">공식 .NET 분석기 외에 [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [XUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/), [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/) 등의 타사 분석기도 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4a6b-225">In addition to the official .NET analyzers, you can also install third party analyzers, such as [StyleCop](https://www.nuget.org/packages/StyleCop.Analyzers/), [Roslynator](https://www.nuget.org/packages/Roslynator.Analyzers/), [XUnit Analyzers](https://www.nuget.org/packages/xunit.analyzers/), and [Sonar Analyzer](https://www.nuget.org/packages/SonarAnalyzer.CSharp/).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4a6b-226">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4a6b-226">See also</span></span>

- [<span data-ttu-id="e4a6b-227">코드 품질 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="e4a6b-227">Code quality analysis rule reference</span></span>](quality-rules/index.md)
- [<span data-ttu-id="e4a6b-228">코드 스타일 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="e4a6b-228">Code style analysis rule reference</span></span>](style-rules/index.md)
- [<span data-ttu-id="e4a6b-229">Visual Studio의 코드 분석</span><span class="sxs-lookup"><span data-stu-id="e4a6b-229">Code analysis in Visual Studio</span></span>](/visualstudio/code-quality/roslyn-analyzers-overview)
- [<span data-ttu-id="e4a6b-230">.NET Compiler Platform SDK</span><span class="sxs-lookup"><span data-stu-id="e4a6b-230">.NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="e4a6b-231">자습서: 첫 번째 분석기 및 코드 수정 작성</span><span class="sxs-lookup"><span data-stu-id="e4a6b-231">Tutorial: Write your first analyzer and code fix</span></span>](../../csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix.md)
