---
title: '호환성이 손상되는 변경: CA2014: 루프에 stackalloc를 사용하지 마세요.'
description: 코드 분석 규칙 CA2014 사용으로 발생하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: 7ad6203c0edd930bbbe43cdb8df0413cba833d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759579"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="bd1cc-103">경고 CA2014: 루프에 stackalloc를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-103">Warning CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="bd1cc-104">.NET 코드 분석기 규칙 [CA2014](/visualstudio/code-quality/ca2014)는 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-104">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="bd1cc-105">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) 식이 루프 내에서 사용되는 모든 C# 코드에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-105">It produces a build warning for any C# code where a [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

## <a name="change-description"></a><span data-ttu-id="bd1cc-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="bd1cc-106">Change description</span></span>

<span data-ttu-id="bd1cc-107">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-107">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="bd1cc-108">[CA2014](/visualstudio/code-quality/ca2014)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-108">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="bd1cc-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="bd1cc-110">규칙 CA2014는 [stackalloc 식](../../../../csharp/language-reference/operators/stackalloc.md)이 루프 내에서 사용되는 C# 코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-110">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="bd1cc-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md)는 현재 스택 프레임에서 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="bd1cc-112">현재 메서드 호출이 반환될 때까지 메모리가 해제되지 않아 스택 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-112">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="bd1cc-113">스택 오버플로 예외를 catch할 수 없기 때문에 스택 오버플로가 발생할 경우 앱이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-113">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bd1cc-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bd1cc-114">Version introduced</span></span>

<span data-ttu-id="bd1cc-115">5.0</span><span class="sxs-lookup"><span data-stu-id="bd1cc-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bd1cc-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bd1cc-116">Recommended action</span></span>

- <span data-ttu-id="bd1cc-117">루프 내에서 [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md)를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-117">Avoid using [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="bd1cc-118">루프 외부에서 메모리 블록을 할당하고 루프 내부에서 재사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-118">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="bd1cc-119">자세한 내용은 [CA2014](/visualstudio/code-quality/ca2014)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-119">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="bd1cc-120">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="bd1cc-121">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bd1cc-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bd1cc-122">Affected APIs</span></span>

<span data-ttu-id="bd1cc-123">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cc-123">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
