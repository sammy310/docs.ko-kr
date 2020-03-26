---
title: If 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249489"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="9fb0f-102">If 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fb0f-102">If Operator (Visual Basic)</span></span>

<span data-ttu-id="9fb0f-103">단락 평가를 사용하여 두 값 중 하나를 조건부로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="9fb0f-104">연산자는 `If` 세 개의 인수 또는 두 개의 인수로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-104">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fb0f-105">구문</span><span class="sxs-lookup"><span data-stu-id="9fb0f-105">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="9fb0f-106">연산자가 세 개의 인수로 호출된 경우</span><span class="sxs-lookup"><span data-stu-id="9fb0f-106">If operator called with three arguments</span></span>

<span data-ttu-id="9fb0f-107">세 `If` 개의 인수를 사용하여 호출되는 경우 첫 번째 인수는 `Boolean`로 캐스팅할 수 있는 값으로 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="9fb0f-108">이 `Boolean` 값은 다른 두 인수 중 평가 및 반환을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="9fb0f-109">다음 목록은 세 개의 `If` 인수를 사용하여 연산자가 호출된 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="9fb0f-110">부분</span><span class="sxs-lookup"><span data-stu-id="9fb0f-110">Parts</span></span>

|<span data-ttu-id="9fb0f-111">용어</span><span class="sxs-lookup"><span data-stu-id="9fb0f-111">Term</span></span>|<span data-ttu-id="9fb0f-112">정의</span><span class="sxs-lookup"><span data-stu-id="9fb0f-112">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="9fb0f-113">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-113">Required.</span></span> <span data-ttu-id="9fb0f-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-114">`Boolean`.</span></span> <span data-ttu-id="9fb0f-115">평가하고 반환할 다른 인수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-115">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="9fb0f-116">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-116">Required.</span></span> <span data-ttu-id="9fb0f-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-117">`Object`.</span></span> <span data-ttu-id="9fb0f-118">를 평가하는 `argument1` 경우 평가 `True`및 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="9fb0f-119">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-119">Required.</span></span> <span data-ttu-id="9fb0f-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-120">`Object`.</span></span> <span data-ttu-id="9fb0f-121">평가하거나 `argument1` `False` [Nothing으로](../../../visual-basic/language-reference/nothing.md)평가하는 `argument1` [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 변수인 경우 평가 및 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|

<span data-ttu-id="9fb0f-122">세 `If` 개의 인수로 호출되는 연산자는 단락 평가를 사용한다는 점을 제외하면 `IIf` 함수처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="9fb0f-123">함수는 `IIf` 항상 세 개의 인수를 모두 평가하는 `If` 반면 세 개의 인수가 있는 연산자는 그 중 두 개만 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="9fb0f-124">첫 `If` 번째 인수가 평가되고 결과가 `Boolean` 값 `True` 또는 `False`으로 캐스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="9fb0f-125">값이 `True`으로 평가되고 `argument2` 해당 값이 반환되지만 `argument3` 평가되지 는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="9fb0f-126">`Boolean` 식의 값이 `False`"을 `argument3` 평가하고 해당 값이 반환되지만 `argument2` 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="9fb0f-127">다음 예제에서는 세 개의 `If` 인수를 사용할 때의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="9fb0f-128">다음 예제에서는 단락 평가의 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="9fb0f-129">이 예제에서는 0을 `number` 제외하고 `divisor` 변수를 `divisor` 변수로 나누려는 두 가지 시도를 보여 주십니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="9fb0f-130">이 경우 0을 반환해야 하며 런타임 오류가 발생하므로 분할을 수행하려고 시도해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="9fb0f-131">식은 `If` 단락 계산을 사용하기 때문에 첫 번째 인수의 값에 따라 두 번째 또는 세 번째 인수를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="9fb0f-132">첫 번째 인수가 true이면 제수는 0이 아니며 두 번째 인수를 평가하고 분할을 수행하는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="9fb0f-133">첫 번째 인수가 false이면 세 번째 인수만 평가되고 0이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="9fb0f-134">따라서 제수0이면 분할을 수행하려고 시도하지 않고 오류 결과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="9fb0f-135">그러나 단락 `IIf` 평가를 사용하지 않으므로 첫 번째 인수가 false인 경우에도 두 번째 인수가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="9fb0f-136">이렇게 하면 런타임을 0으로 나누는 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-136">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="9fb0f-137">연산자가 두 개의 인수로 호출된 경우</span><span class="sxs-lookup"><span data-stu-id="9fb0f-137">If operator called with two arguments</span></span>

<span data-ttu-id="9fb0f-138">첫 번째 `If` 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="9fb0f-139">이렇게 하면 두 개의 인수만 사용하여 연산을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="9fb0f-140">다음 목록은 연산자가 `If` 두 개의 인수로 호출될 때만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-140">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="9fb0f-141">부분</span><span class="sxs-lookup"><span data-stu-id="9fb0f-141">Parts</span></span>

|<span data-ttu-id="9fb0f-142">용어</span><span class="sxs-lookup"><span data-stu-id="9fb0f-142">Term</span></span>|<span data-ttu-id="9fb0f-143">정의</span><span class="sxs-lookup"><span data-stu-id="9fb0f-143">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="9fb0f-144">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-144">Required.</span></span> <span data-ttu-id="9fb0f-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-145">`Object`.</span></span> <span data-ttu-id="9fb0f-146">참조 또는 nullable 값 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-146">Must be a reference or nullable value type.</span></span> <span data-ttu-id="9fb0f-147">평가되고 반환될 때 다른 것으로 `Nothing`평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="9fb0f-148">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-148">Required.</span></span> <span data-ttu-id="9fb0f-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-149">`Object`.</span></span> <span data-ttu-id="9fb0f-150">를 평가하는 `argument2` 경우 평가 `Nothing`및 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="9fb0f-151">`Boolean` 인수를 생략하면 첫 번째 인수는 참조 또는 nullable 값 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable value type.</span></span> <span data-ttu-id="9fb0f-152">첫 번째 인수가 `Nothing`를 평가하는 경우 두 번째 인수의 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="9fb0f-153">다른 모든 경우에는 첫 번째 인수의 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="9fb0f-154">다음 예제에서는 이 평가의 작동 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fb0f-154">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="9fb0f-155">참조</span><span class="sxs-lookup"><span data-stu-id="9fb0f-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="9fb0f-156">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="9fb0f-156">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="9fb0f-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="9fb0f-157">Nothing</span></span>](../nothing.md)
