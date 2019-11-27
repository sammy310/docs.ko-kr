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
ms.openlocfilehash: 6d25519dac31dc91f8560fd3252ba3e2622de370
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331010"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="fad10-102">If 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fad10-102">If Operator (Visual Basic)</span></span>

<span data-ttu-id="fad10-103">는 단락 평가를 사용 하 여 조건에 따라 두 값 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="fad10-104">`If` 연산자는 세 개의 인수를 사용 하거나 두 개의 인수를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-104">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="fad10-105">구문</span><span class="sxs-lookup"><span data-stu-id="fad10-105">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="fad10-106">세 개의 인수를 사용 하 여 연산자를 호출한 경우</span><span class="sxs-lookup"><span data-stu-id="fad10-106">If operator called with three arguments</span></span>

<span data-ttu-id="fad10-107">세 개의 인수를 사용 하 여 `If`를 호출 하는 경우 첫 번째 인수는 `Boolean`으로 캐스팅할 수 있는 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="fad10-108">이 `Boolean` 값은 평가 되 고 반환 되는 다른 두 인수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="fad10-109">다음 목록은 세 인수를 사용 하 여 `If` 연산자를 호출한 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="fad10-110">요소</span><span class="sxs-lookup"><span data-stu-id="fad10-110">Parts</span></span>

|<span data-ttu-id="fad10-111">용어</span><span class="sxs-lookup"><span data-stu-id="fad10-111">Term</span></span>|<span data-ttu-id="fad10-112">정의</span><span class="sxs-lookup"><span data-stu-id="fad10-112">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="fad10-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fad10-113">Required.</span></span> <span data-ttu-id="fad10-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fad10-114">`Boolean`.</span></span> <span data-ttu-id="fad10-115">평가 하 여 반환할 다른 인수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-115">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="fad10-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fad10-116">Required.</span></span> <span data-ttu-id="fad10-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="fad10-117">`Object`.</span></span> <span data-ttu-id="fad10-118">`argument1`이 `True`으로 계산 되는 경우 평가 되 고 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="fad10-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fad10-119">Required.</span></span> <span data-ttu-id="fad10-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="fad10-120">`Object`.</span></span> <span data-ttu-id="fad10-121">`argument1` `False` 계산 되는 경우를 계산 하 고 반환 [됩니다. `argument1`](../../../visual-basic/language-reference/nothing.md)null로 계산 되는 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` 변수인 경우</span><span class="sxs-lookup"><span data-stu-id="fad10-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|

<span data-ttu-id="fad10-122">세 개의 인수를 사용 하 여 호출 되는 `If` 연산자는 단락 계산을 사용 한다는 점을 제외 하 고는 `IIf` 함수 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="fad10-123">`IIf` 함수는 항상 세 개의 인수를 모두 계산 하는 반면, 세 개의 인수가 있는 `If` 연산자는 둘 중 하나만 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="fad10-124">첫 번째 `If` 인수를 계산 하 고 결과를 `Boolean` 값 `True` 또는 `False`로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="fad10-125">값이 `True`이면 `argument2` 평가 되 고 해당 값이 반환 되지만 `argument3`는 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="fad10-126">`Boolean` 식의 값이 `False`경우 `argument3` 계산 되 고 해당 값이 반환 되지만 `argument2`는 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="fad10-127">다음 예에서는 세 개의 인수를 사용 하는 경우 `If`를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="fad10-128">다음 예에서는 단락 계산의 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="fad10-129">이 예에서는 `divisor` 0 인 경우를 제외 하 고 변수 `divisor` 변수 `number`를 나누는 두 시도를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="fad10-130">이 경우에는 0이 반환 되어야 하며, 런타임 오류가 발생 하므로 나누기를 수행 하려고 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="fad10-131">`If` 식은 단락 계산을 사용 하기 때문에 첫 번째 인수 값에 따라 두 번째 또는 세 번째 인수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="fad10-132">첫 번째 인수가 true 이면 제수가 0이 아니고 두 번째 인수를 계산 하 여 나누기를 수행 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="fad10-133">첫 번째 인수가 false 이면 세 번째 인수만 계산 되 고 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="fad10-134">따라서 제수가 0 이면 나누기를 수행 하지 않고 오류 결과가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="fad10-135">그러나 `IIf`는 단락 계산을 사용 하지 않으므로 첫 번째 인수가 false 인 경우에도 두 번째 인수가 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="fad10-136">이로 인해 런타임 0으로 나누기 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-136">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="fad10-137">두 개의 인수를 사용 하 여 연산자를 호출한 경우</span><span class="sxs-lookup"><span data-stu-id="fad10-137">If operator called with two arguments</span></span>

<span data-ttu-id="fad10-138">`If`에 대 한 첫 번째 인수는 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="fad10-139">이렇게 하면 두 개의 인수만 사용 하 여 연산자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="fad10-140">다음 목록은 두 개의 인수를 사용 하 여 `If` 연산자를 호출한 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-140">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="fad10-141">요소</span><span class="sxs-lookup"><span data-stu-id="fad10-141">Parts</span></span>

|<span data-ttu-id="fad10-142">용어</span><span class="sxs-lookup"><span data-stu-id="fad10-142">Term</span></span>|<span data-ttu-id="fad10-143">정의</span><span class="sxs-lookup"><span data-stu-id="fad10-143">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="fad10-144">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fad10-144">Required.</span></span> <span data-ttu-id="fad10-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="fad10-145">`Object`.</span></span> <span data-ttu-id="fad10-146">참조 또는 nullable 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="fad10-147">`Nothing`이외의 값으로 계산 되는 경우 평가 되 고 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="fad10-148">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fad10-148">Required.</span></span> <span data-ttu-id="fad10-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="fad10-149">`Object`.</span></span> <span data-ttu-id="fad10-150">`argument2`이 `Nothing`으로 계산 되는 경우 평가 되 고 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="fad10-151">`Boolean` 인수를 생략 하는 경우 첫 번째 인수는 참조 또는 nullable 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="fad10-152">첫 번째 인수가 `Nothing`로 계산 되는 경우 두 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="fad10-153">다른 모든 경우에는 첫 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="fad10-154">다음 예에서는이 평가의 작동 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fad10-154">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="fad10-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="fad10-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="fad10-156">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="fad10-156">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="fad10-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="fad10-157">Nothing</span></span>](../nothing.md)
