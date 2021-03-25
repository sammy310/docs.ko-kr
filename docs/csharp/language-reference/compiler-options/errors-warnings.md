---
description: 오류 및 경고에 대한 C# 컴파일러 옵션입니다. 이러한 옵션은 경고를 억제하거나 사용하도록 설정하고 경고를 오류로 제어합니다.
title: C# 컴파일러 옵션 - 오류 및 경고
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- WarningLevel compiler option [C#]
- TreatWarningsAsErrors compiler option [C#]
- WarningsAsErrors compiler option [C#]
- WarningsNotAsErrors compiler option [C#]
- DisabledWarnings compiler option [C#]
- CodeAnalysisRuleSet compiler option [C#]
- ErrorLog compiler option [C#]
- ReportAnalyzer compiler option [C#]
ms.openlocfilehash: 2bdda13d6b8b2b75d80c228da678a5b7fbcb8892
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482497"
---
# <a name="c-compiler-options-to-report-errors-and-warnings"></a><span data-ttu-id="dab61-104">오류 및 경고를 보고하는 C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="dab61-104">C# Compiler Options to report errors and warnings</span></span>

<span data-ttu-id="dab61-105">다음 옵션은 컴파일러가 오류 및 경고를 보고하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-105">The following options control how the compiler reports errors and warnings.</span></span> <span data-ttu-id="dab61-106">새 MSBuild 구문은 **굵게** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="dab61-107">이전 *csc.exe* 구문은 `code style`에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-107">The older *csc.exe* syntax is shown in `code style`.</span></span>

- <span data-ttu-id="dab61-108">**WarningLevel** / `-warn`: 경고 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-108">**WarningLevel** / `-warn`: Set warning level.</span></span>
- <span data-ttu-id="dab61-109">**TreatWarningsAsErrors** / `-warnaserror`: 모든 경고를 오류로 처리</span><span class="sxs-lookup"><span data-stu-id="dab61-109">**TreatWarningsAsErrors** / `-warnaserror`: Treat all warnings as errors</span></span>
- <span data-ttu-id="dab61-110">**WarningsAsErrors** / `-warnaserror`: 하나 이상의 경고를 오류로 처리</span><span class="sxs-lookup"><span data-stu-id="dab61-110">**WarningsAsErrors** / `-warnaserror`: Treat one or more warnings as errors</span></span>
- <span data-ttu-id="dab61-111">**WarningsNotAsErrors** / `-warnaserror`: 하나 이상의 경고를 오류로 처리하지 않음</span><span class="sxs-lookup"><span data-stu-id="dab61-111">**WarningsNotAsErrors** / `-warnaserror`: Treat one or more warnings not as errors</span></span>
- <span data-ttu-id="dab61-112">**DisabledWarnings** / `-nowarn`: 비활성화된 경고 목록을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-112">**DisabledWarnings** / `-nowarn`: Set a list of disabled warnings.</span></span>
- <span data-ttu-id="dab61-113">**CodeAnalysisRuleSet** / `-ruleset`: 특정 진단을 비활성화하는 규칙 집합 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-113">**CodeAnalysisRuleSet** / `-ruleset`: Specify a ruleset file that disables specific diagnostics.</span></span>
- <span data-ttu-id="dab61-114">**ErrorLog** / `-errorlog`: 모든 컴파일러와 분석기 진단을 로그할 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-114">**ErrorLog** / `-errorlog`: Specify a file to log all compiler and analyzer diagnostics.</span></span>
- <span data-ttu-id="dab61-115">**ReportAnalyzer** / `-reportanalyzer`: 실행 시간과 같은 추가 분석기 정보를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-115">**ReportAnalyzer** / `-reportanalyzer`:  Report additional analyzer information, such as execution time.</span></span>

## <a name="warninglevel"></a><span data-ttu-id="dab61-116">WarningLevel</span><span class="sxs-lookup"><span data-stu-id="dab61-116">WarningLevel</span></span>

<span data-ttu-id="dab61-117">**WarningLevel** 옵션은 컴파일러에서 표시할 경고 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-117">The **WarningLevel** option specifies the warning level for the compiler to display.</span></span>

```xml
<WarningLevel>3</WarningLevel>
```

<span data-ttu-id="dab61-118">요소 값은 컴파일에 대해 표시할 경고 수준입니다. 숫자가 낮을수록 높은 심각도 경고만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-118">The element value is the warning level you want displayed for the compilation: Lower numbers show only high severity warnings.</span></span> <span data-ttu-id="dab61-119">숫자가 높을수록 더 많은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-119">Higher numbers show more warnings.</span></span> <span data-ttu-id="dab61-120">값은 0 또는 양의 정수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-120">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="dab61-121">경고 수준</span><span class="sxs-lookup"><span data-stu-id="dab61-121">Warning level</span></span>|<span data-ttu-id="dab61-122">의미</span><span class="sxs-lookup"><span data-stu-id="dab61-122">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="dab61-123">0</span><span class="sxs-lookup"><span data-stu-id="dab61-123">0</span></span>|<span data-ttu-id="dab61-124">모든 경고 메시지 내보내기를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-124">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="dab61-125">1</span><span class="sxs-lookup"><span data-stu-id="dab61-125">1</span></span>|<span data-ttu-id="dab61-126">심각한 경고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-126">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="dab61-127">2</span><span class="sxs-lookup"><span data-stu-id="dab61-127">2</span></span>|<span data-ttu-id="dab61-128">수준 1 경고와 덜 심각한 특정 경고(예: 클래스 멤버 숨기기에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-128">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|
|<span data-ttu-id="dab61-129">3</span><span class="sxs-lookup"><span data-stu-id="dab61-129">3</span></span>|<span data-ttu-id="dab61-130">수준 2 경고와 덜 심각한 특정 경고(예: 항상 `true` 또는 `false`로 평가되는 식에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-130">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|
|<span data-ttu-id="dab61-131">4(기본값)</span><span class="sxs-lookup"><span data-stu-id="dab61-131">4 (the default)</span></span>|<span data-ttu-id="dab61-132">모든 수준 3 경고와 정보 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-132">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="dab61-133">5</span><span class="sxs-lookup"><span data-stu-id="dab61-133">5</span></span>|<span data-ttu-id="dab61-134">수준 4 경고와 함께 C# 9.0에 제공된 컴파일러의 [추가 경고](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-134">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="dab61-135">5보다 큼</span><span class="sxs-lookup"><span data-stu-id="dab61-135">Greater than 5</span></span>|<span data-ttu-id="dab61-136">5보다 큰 값은 5로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-136">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="dab61-137">컴파일러가 새 경고 수준으로 업데이트된 경우 항상 모든 경고가 표시되도록 하려면 임의의 큰 값(예: `9999`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-137">To make sure you always have all warnings if the compiler is updated with new warning levels, put an arbitrary large value (for example, `9999`).</span></span>

<span data-ttu-id="dab61-138">오류 또는 경고에 대한 정보를 가져오려면 도움말 색인에서 오류 코드를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-138">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="dab61-139">오류 또는 경고에 대한 정보를 가져오는 다른 방법은 [C# 컴파일러 오류](../compiler-messages/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab61-139">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span> <span data-ttu-id="dab61-140">[**TreatWarningsAsErrors**](#treatwarningsaserrors)를 사용하여 모든 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-140">Use [**TreatWarningsAsErrors**](#treatwarningsaserrors) to treat all warnings as errors.</span></span> <span data-ttu-id="dab61-141">[**DisabledWarnings**](#disabledwarnings)를 사용하여 특정 경고를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-141">Use [**DisabledWarnings**](#disabledwarnings) to disable certain warnings.</span></span>  

## <a name="treatwarningsaserrors"></a><span data-ttu-id="dab61-142">TreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="dab61-142">TreatWarningsAsErrors</span></span>

<span data-ttu-id="dab61-143">**TreatWarningsAsErrors** 옵션은 모든 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-143">The **TreatWarningsAsErrors** option treats all warnings as errors.</span></span> <span data-ttu-id="dab61-144">**TreatWarningsAsErrors** 를 사용하여 일부 경고만 오류로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-144">You can also use the **TreatWarningsAsErrors** to set only some warnings as errors.</span></span> <span data-ttu-id="dab61-145">**TreatWarningsAsErrors** 를 설정한 경우 **TreatWarningsAsErrors** 를 사용하여 오류로 처리하면 안 되는 경고를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-145">If you turn on **TreatWarningsAsErrors**, you can use **TreatWarningsAsErrors** to list warnings that shouldn't be treated as errors.</span></span>

```xml
<TreatWarningsAsErrors></TreatWarningsAsErrors>
```

<span data-ttu-id="dab61-146">대신 모든 경고 메시지가 오류로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-146">All warning messages are instead reported as errors.</span></span> <span data-ttu-id="dab61-147">빌드 프로세스가 중단됩니다(출력 파일이 빌드되지 않음).</span><span class="sxs-lookup"><span data-stu-id="dab61-147">The build process halts (no output files are built).</span></span> <span data-ttu-id="dab61-148">기본적으로 **TreatWarningsAsErrors** 는 적용되지 않습니다. 즉, 경고가 출력 파일을 생성하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-148">By default, **TreatWarningsAsErrors** isn't in effect, which means warnings don't prevent the generation of an output file.</span></span> <span data-ttu-id="dab61-149">필요에 따라 몇 개의 특정 경고만 오류로 처리하려는 경우 오류로 처리할 경고 번호의 쉼표로 구분된 목록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-149">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="dab61-150">모든 Null 허용 여부 경고 집합은 [**Null 허용**](language.md#nullable) 축약형을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-150">The set of all nullability warnings can be specified with the [**Nullable**](language.md#nullable) shorthand.</span></span> <span data-ttu-id="dab61-151">[**WarningLevel**](#warninglevel)을 사용하여 컴파일러에서 표시할 경고 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-151">Use [**WarningLevel**](#warninglevel) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="dab61-152">[**DisabledWarnings**](#disabledwarnings)를 사용하여 특정 경고를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-152">Use [**DisabledWarnings**](#disabledwarnings) to disable certain warnings.</span></span>

## <a name="warningsaserrors-and-warningsnotaserrors"></a><span data-ttu-id="dab61-153">WarningsAsErrors 및 WarningsNotAsErrors</span><span class="sxs-lookup"><span data-stu-id="dab61-153">WarningsAsErrors and WarningsNotAsErrors</span></span>

<span data-ttu-id="dab61-154">**WarningsAsErrors** 및 **WarningsNotAsErrors** 옵션은 경고 목록에 대해 **TreatWarningsAsErrors** 옵션을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-154">The **WarningsAsErrors** and **WarningsNotAsErrors** options override the **TreatWarningsAsErrors** option for a list of warnings.</span></span>

<span data-ttu-id="dab61-155">경고 0219 및 0168을 오류로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-155">Enable warnings 0219 and 0168 as errors:</span></span>

```xml
<WarningsAsErrors>0219,0168</WarningsAsErrors>
```

<span data-ttu-id="dab61-156">오류와 동일한 경고를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-156">Disable the same warnings as errors:</span></span>

```xml
<WarningsNotAsErrors>0219,0168</WarningsNotAsErrors>
```

<span data-ttu-id="dab61-157">**WarningsAsErrors** 를 사용하여 경고 세트를 오류로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-157">You use **WarningsAsErrors** to configure a set of warnings as errors.</span></span> <span data-ttu-id="dab61-158">**WarningsNotAsErrors** 를 사용하여 모든 경고를 오류로 설정한 경우 오류가 아니어야 하는 경고 세트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-158">Use **WarningsNotAsErrors** to configure a set of warnings that should not be errors when you've set all warnings as errors.</span></span>

## <a name="disabledwarnings"></a><span data-ttu-id="dab61-159">DisabledWarnings</span><span class="sxs-lookup"><span data-stu-id="dab61-159">DisabledWarnings</span></span>

<span data-ttu-id="dab61-160">**DisabledWarnings** 옵션을 사용하면 컴파일러에서 하나 이상의 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-160">The **DisabledWarnings** option lets you suppress the compiler from displaying one or more warnings.</span></span> <span data-ttu-id="dab61-161">여러 경고 번호를 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-161">Separate multiple warning numbers with a comma.</span></span>

```xml
<DisabledWarnings>number1, number2</DisabledWarnings>
```

<span data-ttu-id="dab61-162">`number1`, `number2` 컴파일러에서 표시하지 않으려는 경고 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-162">`number1`, `number2` Warning number(s) that you want the compiler to suppress.</span></span> <span data-ttu-id="dab61-163">경고 식별자의 숫자 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-163">You specify the numeric part of the warning identifier.</span></span> <span data-ttu-id="dab61-164">예를 들어 *CS0028* 을 표시하지 않으려면 `<DisabledWarnings>28</DisabledWarnings>`를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-164">For example, if you want to suppress *CS0028*, you could specify `<DisabledWarnings>28</DisabledWarnings>`.</span></span> <span data-ttu-id="dab61-165">컴파일러는 이전 릴리스에서 유효했지만 제거된 **DisabledWarnings** 에 전달된 경고 번호를 자동으로 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-165">The compiler silently ignores warning numbers passed to **DisabledWarnings** that were valid in previous releases, but that have been removed.</span></span> <span data-ttu-id="dab61-166">예를 들어 *CS0679* 는 Visual Studio .NET 2002의 컴파일러에서 유효했지만 이후에 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-166">For example, *CS0679* was valid in the compiler in Visual Studio .NET 2002 but was removed later.</span></span>

 <span data-ttu-id="dab61-167">다음 경고는 **DisabledWarnings** 옵션으로 표시되지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-167">The following warnings cannot be suppressed by the **DisabledWarnings** option:</span></span>

- <span data-ttu-id="dab61-168">컴파일러 경고(수준 1) CS2002</span><span class="sxs-lookup"><span data-stu-id="dab61-168">Compiler Warning (level 1) CS2002</span></span>  
- <span data-ttu-id="dab61-169">컴파일러 경고(수준 1) CS2023</span><span class="sxs-lookup"><span data-stu-id="dab61-169">Compiler Warning (level 1) CS2023</span></span>
- <span data-ttu-id="dab61-170">컴파일러 경고(수준 1) CS2029</span><span class="sxs-lookup"><span data-stu-id="dab61-170">Compiler Warning (level 1) CS2029</span></span>

## <a name="codeanalysisruleset"></a><span data-ttu-id="dab61-171">CodeAnalysisRuleSet</span><span class="sxs-lookup"><span data-stu-id="dab61-171">CodeAnalysisRuleSet</span></span>

<span data-ttu-id="dab61-172">특정 진단을 구성하는 규칙 집합 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-172">Specify a ruleset file that configures specific diagnostics.</span></span>

```xml
<CodeAnalysisRuleSet>MyConfiguration.ruleset</CodeAnalysisRuleSet>
```

<span data-ttu-id="dab61-173">여기서 `MyConfiguration.ruleset`은 규칙 집합 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-173">Where `MyConfiguration.ruleset` is the path to the ruleset file.</span></span> <span data-ttu-id="dab61-174">규칙 집합 사용에 대한 자세한 내용은 [규칙 집합에 대한 Visual Studio 설명서](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules)의 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab61-174">For more information on using rule sets, see the article in the [Visual Studio documentation on Rule sets](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules).</span></span>

## <a name="errorlog"></a><span data-ttu-id="dab61-175">ErrorLog</span><span class="sxs-lookup"><span data-stu-id="dab61-175">ErrorLog</span></span>

<span data-ttu-id="dab61-176">모든 컴파일러와 분석기 진단을 로그할 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-176">Specify a file to log all compiler and analyzer diagnostics.</span></span>

```xml
<ErrorLog>MyConfiguration.ruleset</ErrorLog>
```

<span data-ttu-id="dab61-177">**ErrorLog** 옵션을 사용하면 컴파일러에서 [SARIF(정적 분석 결과 교환 형) 로그](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools)를 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-177">The **ErrorLog** option causes the compiler to output a [Static Analysis Results Interchange Format (SARIF) log](https://github.com/microsoft/sarif-tutorials/blob/main/docs/1-Introduction.md#:~:text=What%20is%20SARIF%3F,for%20use%20by%20simpler%20tools).</span></span> <span data-ttu-id="dab61-178">SARIF 로그는 일반적으로 컴파일러 및 분석기 진단의 결과를 분석하는 도구에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-178">SARIF logs are typically read by tools that analyze the results from compiler and analyzer diagnostics.</span></span>

## <a name="reportanalyzer"></a><span data-ttu-id="dab61-179">ReportAnalyzer</span><span class="sxs-lookup"><span data-stu-id="dab61-179">ReportAnalyzer</span></span>

<span data-ttu-id="dab61-180">실행 시간과 같은 추가적인 분석 정보를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-180">Report additional analyzer information, such as execution time.</span></span>

```xml
<ReportAnalyzer>true</ReportAnalyzer>
```

<span data-ttu-id="dab61-181">**ReportAnalyzer** 옵션을 사용하면 컴파일러가 빌드에서 분석기의 성능 특성을 자세히 설명하는 추가 MSBuild 로그 정보를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-181">The **ReportAnalyzer** option causes the compiler to emit extra MSBuild log information that details the performance characteristics of analyzers in the build.</span></span> <span data-ttu-id="dab61-182">일반적으로 분석기 작성자가 분석기의 유효성을 검사하는 과정에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dab61-182">It's typically used by analyzer authors as part of validating the analyzer.</span></span>
