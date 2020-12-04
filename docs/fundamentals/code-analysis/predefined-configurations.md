---
title: 미리 정의 된 구성 파일 (코드 분석)
description: 미리 정의 된 editorconfig 및 규칙 집합 파일을 사용 하 여 특정 유형의 코드 분석을 대상으로 지정 하는 방법에 대해 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "96593136"
---
# <a name="predefined-configuration-files"></a><span data-ttu-id="ecce5-103">미리 정의 된 구성 파일</span><span class="sxs-lookup"><span data-stu-id="ecce5-103">Predefined configuration files</span></span>

<span data-ttu-id="ecce5-104">미리 정의 된 EditorConfig 및 [규칙 집합](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) 파일을 사용 하 여 보안 또는 디자인 규칙과 같은 코드 품질 규칙의 범주를 빠르고 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-104">Predefined EditorConfig and [rule set](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) files are available that make it quick and easy to enable a category of code quality rules, such as security or design rules.</span></span> <span data-ttu-id="ecce5-105">규칙의 특정 범주를 사용 하도록 설정 하면 대상 문제 및 특정 조건을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-105">By enabling a specific category of rules, you can identify targeted issues and specific conditions.</span></span> <span data-ttu-id="ecce5-106">이러한 미리 정의 된 파일에 액세스 하려면 [Microsoft CodeAnalysis](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-106">To access these predefined files, install the [Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer package.</span></span>

<span data-ttu-id="ecce5-107">[Microsoft CodeAnalysis .Net 분석기](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) 에는 다음 규칙 범주에 대 한 미리 정의 된 editorconfig 파일 및 규칙 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-107">[Microsoft.CodeAnalysis.NetAnalyzers](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) includes predefined EditorConfig files and rule sets for the following rule categories:</span></span>

- <span data-ttu-id="ecce5-108">모든 규칙</span><span class="sxs-lookup"><span data-stu-id="ecce5-108">All rules</span></span>
- <span data-ttu-id="ecce5-109">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="ecce5-109">Dataflow</span></span>
- <span data-ttu-id="ecce5-110">디자인</span><span class="sxs-lookup"><span data-stu-id="ecce5-110">Design</span></span>
- <span data-ttu-id="ecce5-111">설명서</span><span class="sxs-lookup"><span data-stu-id="ecce5-111">Documentation</span></span>
- <span data-ttu-id="ecce5-112">전역화</span><span class="sxs-lookup"><span data-stu-id="ecce5-112">Globalization</span></span>
- <span data-ttu-id="ecce5-113">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ecce5-113">Interoperability</span></span>
- <span data-ttu-id="ecce5-114">유지 관리</span><span class="sxs-lookup"><span data-stu-id="ecce5-114">Maintainability</span></span>
- <span data-ttu-id="ecce5-115">이름 지정</span><span class="sxs-lookup"><span data-stu-id="ecce5-115">Naming</span></span>
- <span data-ttu-id="ecce5-116">성능</span><span class="sxs-lookup"><span data-stu-id="ecce5-116">Performance</span></span>
- <span data-ttu-id="ecce5-117">FxCop에서 이식</span><span class="sxs-lookup"><span data-stu-id="ecce5-117">Ported from FxCop</span></span>
- <span data-ttu-id="ecce5-118">안정성</span><span class="sxs-lookup"><span data-stu-id="ecce5-118">Reliability</span></span>
- <span data-ttu-id="ecce5-119">보안</span><span class="sxs-lookup"><span data-stu-id="ecce5-119">Security</span></span>
- <span data-ttu-id="ecce5-120">사용</span><span class="sxs-lookup"><span data-stu-id="ecce5-120">Usage</span></span>

<span data-ttu-id="ecce5-121">이러한 각 규칙 범주에는 다음에 대 한 EditorConfig 또는 rule set 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-121">Each of those categories of rules has an EditorConfig or rule set file to:</span></span>

- <span data-ttu-id="ecce5-122">범주에 있는 모든 규칙을 사용 하도록 설정 하 고 다른 모든 규칙을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-122">Enable all the rules in the category (and disable all other rules)</span></span>
- <span data-ttu-id="ecce5-123">각 규칙의 기본 심각도를 사용 하 고 기본적으로 사용 하도록 설정 (및 다른 모든 규칙 사용 안 함)</span><span class="sxs-lookup"><span data-stu-id="ecce5-123">Use each rule's default severity and enabled by default setting (and disable all other rules)</span></span>

> [!TIP]
> <span data-ttu-id="ecce5-124">"모든 규칙" 범주에는 모든 규칙을 사용 하지 않도록 설정 하는 추가 EditorConfig 또는 규칙 집합 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-124">The "all rules" category has an additional EditorConfig or rule set file to disable all rules.</span></span> <span data-ttu-id="ecce5-125">이 파일을 사용 하 여 프로젝트에서 분석기 경고 또는 오류를 신속 하 게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-125">Use this file to quickly get rid of any analyzer warnings or errors in a project.</span></span>

## <a name="predefined-editorconfig-files"></a><span data-ttu-id="ecce5-126">미리 정의 된 EditorConfig 파일</span><span class="sxs-lookup"><span data-stu-id="ecce5-126">Predefined EditorConfig files</span></span>

<span data-ttu-id="ecce5-127">Microsoft CodeAnalysis. NetAnalyzers 분석기 패키지에 대해 미리 정의 된 EditorConfig 파일은 NuGet 패키지가 설치 된 *EditorConfig* 하위 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-127">The predefined EditorConfig files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *editorconfig* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="ecce5-128">예를 들어 모든 보안 규칙을 사용 하도록 설정 하는 EditorConfig 파일은 *editorconfig/Securityrules enabled/.* e n t config에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-128">For example, the EditorConfig file to enable all security rules is located at *editorconfig/SecurityRulesEnabled/.editorconfig*.</span></span>

<span data-ttu-id="ecce5-129">선택한 *editorconfig* 파일을 프로젝트의 루트 디렉터리에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-129">Copy the chosen *.editorconfig* file to your project's root directory.</span></span>

## <a name="predefined-rule-sets"></a><span data-ttu-id="ecce5-130">미리 정의된 규칙 집합</span><span class="sxs-lookup"><span data-stu-id="ecce5-130">Predefined rule sets</span></span>

<span data-ttu-id="ecce5-131">Microsoft CodeAnalysis. NetAnalyzers 분석기 패키지에 대 한 미리 정의 된 규칙 집합 파일은 NuGet 패키지가 설치 된 *의 규칙 집합 하위 디렉터리* 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-131">The predefined rule set files for the Microsoft.CodeAnalysis.NetAnalyzers analyzer package are located in the *rulesets* subdirectory of where the NuGet package was installed.</span></span> <span data-ttu-id="ecce5-132">예를 들어 모든 보안 규칙을 사용 하도록 설정 하는 규칙 집합 파일은 규칙 집합/보안 규칙 *사용.* 규칙 집합에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-132">For example, the rule set file to enable all security rules is located at *rulesets/SecurityRulesEnabled.ruleset*.</span></span> <span data-ttu-id="ecce5-133">하나 이상의 규칙 집합을 복사 하 여 프로젝트를 포함 하는 디렉터리에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ecce5-133">Copy one or more of the rule sets and paste them in the directory that contains your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecce5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecce5-134">See also</span></span>

- [<span data-ttu-id="ecce5-135">분석기 구성</span><span class="sxs-lookup"><span data-stu-id="ecce5-135">Analyzer configuration</span></span>](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [<span data-ttu-id="ecce5-136">EditorConfig에 대 한 .NET 코드 스타일 규칙 옵션</span><span class="sxs-lookup"><span data-stu-id="ecce5-136">.NET code style rule options for EditorConfig</span></span>](code-style-rule-options.md)
