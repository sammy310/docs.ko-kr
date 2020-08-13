---
title: switch 식 - C# 참조
description: 패턴 일치 및 기타 데이터 검사에 C# switch 식을 사용하는 방법을 알아봅니다.
ms.date: 03/19/2020
ms.openlocfilehash: 2249afc1ff1cc81e9ad423d910ebb95df8c787d4
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916659"
---
# <a name="switch-expression-c-reference"></a><span data-ttu-id="bb625-103">switch 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bb625-103">switch expression (C# reference)</span></span>

<span data-ttu-id="bb625-104">이 문서에서는 C# 8.0에 도입된 `switch` 식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-104">This article covers the `switch` expression, introduced in C# 8.0.</span></span> <span data-ttu-id="bb625-105">`switch` 문에 대한 자세한 내용은 [문](../keywords/index.md) 섹션의 [`switch` 문](../keywords/switch.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb625-105">For information on the `switch` statement, see the article on the [`switch` statement](../keywords/switch.md) in the [statements](../keywords/index.md) section.</span></span>

## <a name="basic-example"></a><span data-ttu-id="bb625-106">기본 예제</span><span class="sxs-lookup"><span data-stu-id="bb625-106">Basic example</span></span>

<span data-ttu-id="bb625-107">`switch` 식은 식 컨텍스트에서 `switch`와 유사한 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-107">The `switch` expression provides for `switch`-like semantics in an expression context.</span></span> <span data-ttu-id="bb625-108">스위치 암(arm)에서 값을 생성할 때 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-108">It provides a concise syntax when the switch arms produce a value.</span></span> <span data-ttu-id="bb625-109">다음 예제에서는 switch 식의 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-109">The following example shows the structure of a switch expression.</span></span> <span data-ttu-id="bb625-110">온라인 맵의 시각적 방향을 나타내는 `enum`의 값을 해당하는 기본 방향으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-110">It translates values from an `enum` representing visual directions in an online map to the corresponding cardinal direction:</span></span>

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetBasicStructure":::

<span data-ttu-id="bb625-111">위의 샘플에서는 switch 식의 기본 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-111">The preceding sample shows the basic elements of a switch expression:</span></span>

- <span data-ttu-id="bb625-112">*range 식*: 위의 예제에서는 `direction` 변수를 range 식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-112">The *range expression*: The preceding example uses the variable `direction` as the range expression.</span></span>
- <span data-ttu-id="bb625-113">*switch 식 암(arm)* : 각 switch 식 암(arm)에는 *패턴*, 선택적인 *케이스 가드*, `=>` 토큰 및 *식*이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-113">The *switch expression arms*: Each switch expression arm contains a *pattern*, an optional *case guard*, the `=>` token, and an *expression*.</span></span>

<span data-ttu-id="bb625-114">*switch 식*의 결과는 *패턴*이 *range 식*과 일치하고 *케이스 가드*(있는 경우)가 `true`로 평가되는 첫 번째 *switch 식 암(arm)* 의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-114">The result of the *switch expression* is the value of the expression of the first *switch expression arm* whose *pattern* matches the *range expression* and whose *case guard*, if present, evaluates to `true`.</span></span> <span data-ttu-id="bb625-115">`=>` 토큰 오른쪽에 있는 *식*은 식 문이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-115">The *expression* on the right of the `=>` token can't be an expression statement.</span></span>

<span data-ttu-id="bb625-116">*switch 식 암(arm)* 은 텍스트 순서대로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-116">The *switch expression arms* are evaluated in text order.</span></span> <span data-ttu-id="bb625-117">상위 *switch 식 암(arm)* 이 모든 값과 일치하기 때문에 하위 *switch 식 암(arm)* 을 선택할 수 없는 경우 컴파일러에서 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-117">The compiler issues an error when a lower *switch expression arm* can't be chosen because a higher *switch expression arm* matches all its values.</span></span>

## <a name="patterns-and-case-guards"></a><span data-ttu-id="bb625-118">패턴 및 케이스 가드</span><span class="sxs-lookup"><span data-stu-id="bb625-118">Patterns and case guards</span></span>

<span data-ttu-id="bb625-119">switch 식 암(arm)에서는 많은 패턴이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-119">Many patterns are supported in switch expression arms.</span></span> <span data-ttu-id="bb625-120">앞의 예제에서는 ‘상수 패턴’을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-120">The preceding example uses a *constant pattern*.</span></span> <span data-ttu-id="bb625-121">‘상수 패턴’은 range 식을 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-121">A *constant pattern* compares the range expression to a value.</span></span> <span data-ttu-id="bb625-122">이 값은 컴파일 시간 상수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-122">That value must be a compile-time constant.</span></span> <span data-ttu-id="bb625-123">*형식 패턴*은 range 식을 알려진 형식과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-123">The *type pattern* compares the range expression to a known type.</span></span> <span data-ttu-id="bb625-124">다음 예제에서는 시퀀스에서 세 번째 요소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-124">The following example retrieves the third element from a sequence.</span></span> <span data-ttu-id="bb625-125">시퀀스의 형식에 따라 다른 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-125">It uses different methods based on the type of the sequence:</span></span>

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetTypePattern":::

<span data-ttu-id="bb625-126">패턴은 재귀적으로 지정할 수 있습니다. 그러면 패턴이 형식을 테스트하고 해당 형식이 일치하는 경우 패턴이 range 식의 하나 이상의 속성 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-126">Patterns can be recursive, where a pattern tests a type, and if that type matches, the pattern matches one or more property values on the range expression.</span></span> <span data-ttu-id="bb625-127">재귀 패턴을 사용하여 앞의 예제를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-127">You can use recursive patterns to extend the preceding example.</span></span> <span data-ttu-id="bb625-128">요소가 3개 미만인 배열에 대해 switch 식 암(arm)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-128">You add switch expression arms for arrays that have fewer than 3 elements.</span></span> <span data-ttu-id="bb625-129">다음 예제에서는 재귀 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-129">Recursive patterns are shown in the following example:</span></span>

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetRecursivePattern":::

<span data-ttu-id="bb625-130">재귀 패턴은 range 식의 속성을 검사할 수 있지만 임의의 코드를 실행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-130">Recursive patterns can examine properties of the range expression, but can't execute arbitrary code.</span></span> <span data-ttu-id="bb625-131">`when` 절에 지정된 *케이스 가드*를 사용하여 다른 시퀀스 형식에 비슷한 검사를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-131">You can use a *case guard*, specified in a `when` clause, to provide similar checks for other sequence types:</span></span>

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetGuardCase":::

<span data-ttu-id="bb625-132">마지막으로 `_` 패턴과 `null` 패턴을 추가하여 다른 switch 식 암(arm)에서 처리되지 않은 인수를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-132">Finally, you can add the `_` pattern and the `null` pattern to catch arguments that aren't processed by any other switch expression arm.</span></span> <span data-ttu-id="bb625-133">이렇게 하면 switch 식이 range 식의 가능한 값을 모두 처리합니다(*exhaustive*).</span><span class="sxs-lookup"><span data-stu-id="bb625-133">That makes the switch expression *exhaustive*, meaning any possible value of the range expression is handled.</span></span> <span data-ttu-id="bb625-134">다음 예제에서는 이러한 식 암(arm)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-134">The following example adds those expression arms:</span></span>

:::code language="csharp" source="snippets/shared/SwitchExpressions.cs" id="SnippetExhaustive":::

<span data-ttu-id="bb625-135">앞의 예제는 `null` 패턴을 추가하고 `IEnumerable<T>` 형식 패턴을 `_` 패턴으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-135">The preceding example adds a `null` pattern, and changes the `IEnumerable<T>` type pattern to a `_` pattern.</span></span> <span data-ttu-id="bb625-136">`null` 패턴은 switch 식 암(arm)으로 null 검사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-136">The `null` pattern provides a null check as a switch expression arm.</span></span> <span data-ttu-id="bb625-137">해당 암(arm)에 대한 식에서 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-137">The expression for that arm throws an <xref:System.ArgumentNullException>.</span></span> <span data-ttu-id="bb625-138">`_` 패턴은 이전 암(arm)과 일치하지 않은 모든 입력을 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-138">The `_` pattern matches all inputs that haven't been matched by previous arms.</span></span> <span data-ttu-id="bb625-139">`null` 검사 후에 오거나 `null` 입력과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-139">It must come after the `null` check, or it would match `null` inputs.</span></span>

<span data-ttu-id="bb625-140">[재귀 패턴](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression)에 대한 C# 언어 사양 제안에서 자세한 내용을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb625-140">You can read more in the C# language spec proposal for [recursive patterns](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb625-141">참조</span><span class="sxs-lookup"><span data-stu-id="bb625-141">See also</span></span>

- [<span data-ttu-id="bb625-142">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bb625-142">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bb625-143">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="bb625-143">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="bb625-144">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="bb625-144">Pattern matching</span></span>](../../pattern-matching.md)
