---
description: '다음에 대 한 자세한 정보: If 연산자 (Visual Basic)'
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
ms.openlocfilehash: 3b25ab4b6c5f0d2608644adb6e35ff4ad5128f42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665876"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="b7120-103">If 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7120-103">If Operator (Visual Basic)</span></span>

<span data-ttu-id="b7120-104">는 단락 평가를 사용 하 여 조건에 따라 두 값 중 하나를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-104">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="b7120-105">연산자는 세 개의 인수를 사용 `If` 하거나 두 개의 인수를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-105">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7120-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7120-106">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="b7120-107">세 개의 인수를 사용 하 여 연산자를 호출한 경우</span><span class="sxs-lookup"><span data-stu-id="b7120-107">If operator called with three arguments</span></span>

<span data-ttu-id="b7120-108">`If`세 개의 인수를 사용 하 여를 호출 하는 경우 첫 번째 인수는로 캐스팅할 수 있는 값으로 계산 되어야 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b7120-108">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="b7120-109">이 `Boolean` 값은 평가 되 고 반환 되는 다른 두 인수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-109">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="b7120-110">다음 목록은 `If` 세 인수를 사용 하 여 연산자를 호출 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-110">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="b7120-111">부분</span><span class="sxs-lookup"><span data-stu-id="b7120-111">Parts</span></span>

|<span data-ttu-id="b7120-112">용어</span><span class="sxs-lookup"><span data-stu-id="b7120-112">Term</span></span>|<span data-ttu-id="b7120-113">정의</span><span class="sxs-lookup"><span data-stu-id="b7120-113">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="b7120-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b7120-114">Required.</span></span> <span data-ttu-id="b7120-115">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b7120-115">`Boolean`.</span></span> <span data-ttu-id="b7120-116">평가 하 여 반환할 다른 인수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-116">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="b7120-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b7120-117">Required.</span></span> <span data-ttu-id="b7120-118">`Object`.</span><span class="sxs-lookup"><span data-stu-id="b7120-118">`Object`.</span></span> <span data-ttu-id="b7120-119">가로 계산 되는 경우 평가 되 고 반환 `argument1` `True` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-119">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="b7120-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b7120-120">Required.</span></span> <span data-ttu-id="b7120-121">`Object`.</span><span class="sxs-lookup"><span data-stu-id="b7120-121">`Object`.</span></span> <span data-ttu-id="b7120-122">가로 계산 되는 경우이 계산 및 반환 되 고 `argument1` `False` , `argument1` 가 [](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` [Nothing](../nothing.md)으로 계산 되는 Nullable 변수 이면이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-122">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../nothing.md).</span></span>|

<span data-ttu-id="b7120-123">`If`세 개의 인수를 사용 하 여 호출 되는 연산자는 `IIf` 단락 계산을 사용 한다는 점을 제외 하 고 함수 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-123">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="b7120-124">`IIf`함수는 항상 세 개의 인수를 모두 계산 하는 반면, `If` 세 개의 인수가 있는 연산자는 둘 중 하나만 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-124">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="b7120-125">첫 번째 `If` 인수를 계산 하 고 결과를 `Boolean` 값 또는로 캐스팅 합니다 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="b7120-125">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="b7120-126">값이 이면 `True` `argument2` 가 평가 되 고 해당 값이 반환 되지만 `argument3` 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-126">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="b7120-127">식의 값 `Boolean` 이 인 경우이 `False` `argument3` 평가 되 고 해당 값이 반환 되지만 `argument2` 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-127">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="b7120-128">다음 예에서는 세 개의 인수를 사용 하는 경우를 사용 하는 방법을 보여 줍니다 `If` .</span><span class="sxs-lookup"><span data-stu-id="b7120-128">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="b7120-129">다음 예에서는 단락 계산의 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-129">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="b7120-130">이 예에서는 `number` `divisor` 이 0 인 경우를 제외 하 고 변수를 변수로 나누는 두 시도를 보여 줍니다 `divisor` .</span><span class="sxs-lookup"><span data-stu-id="b7120-130">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="b7120-131">이 경우에는 0이 반환 되어야 하며, 런타임 오류가 발생 하므로 나누기를 수행 하려고 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-131">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="b7120-132">식에서 `If` 단락 계산을 사용 하기 때문에 첫 번째 인수 값에 따라 두 번째 또는 세 번째 인수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-132">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="b7120-133">첫 번째 인수가 true 이면 제수가 0이 아니고 두 번째 인수를 계산 하 여 나누기를 수행 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-133">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="b7120-134">첫 번째 인수가 false 이면 세 번째 인수만 계산 되 고 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-134">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="b7120-135">따라서 제수가 0 이면 나누기를 수행 하지 않고 오류 결과가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-135">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="b7120-136">그러나 `IIf` 는 단락 평가를 사용 하지 않으므로 첫 번째 인수가 false 인 경우에도 두 번째 인수가 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-136">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="b7120-137">이로 인해 런타임 0으로 나누기 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-137">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="b7120-138">두 개의 인수를 사용 하 여 연산자를 호출한 경우</span><span class="sxs-lookup"><span data-stu-id="b7120-138">If operator called with two arguments</span></span>

<span data-ttu-id="b7120-139">에 대 한 첫 번째 인수를 `If` 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-139">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="b7120-140">이렇게 하면 두 개의 인수만 사용 하 여 연산자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-140">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="b7120-141">다음 목록은 `If` 두 개의 인수를 사용 하 여 연산자를 호출 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-141">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="b7120-142">부분</span><span class="sxs-lookup"><span data-stu-id="b7120-142">Parts</span></span>

|<span data-ttu-id="b7120-143">용어</span><span class="sxs-lookup"><span data-stu-id="b7120-143">Term</span></span>|<span data-ttu-id="b7120-144">정의</span><span class="sxs-lookup"><span data-stu-id="b7120-144">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="b7120-145">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b7120-145">Required.</span></span> <span data-ttu-id="b7120-146">`Object`.</span><span class="sxs-lookup"><span data-stu-id="b7120-146">`Object`.</span></span> <span data-ttu-id="b7120-147">참조 또는 nullable 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-147">Must be a reference or nullable value type.</span></span> <span data-ttu-id="b7120-148">이 아닌 값으로 계산 되는 경우 평가 되 고 반환 `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-148">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="b7120-149">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b7120-149">Required.</span></span> <span data-ttu-id="b7120-150">`Object`.</span><span class="sxs-lookup"><span data-stu-id="b7120-150">`Object`.</span></span> <span data-ttu-id="b7120-151">가로 계산 되는 경우 평가 되 고 반환 `argument2` `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-151">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="b7120-152">인수를 `Boolean` 생략 하면 첫 번째 인수는 참조 또는 nullable 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-152">When the `Boolean` argument is omitted, the first argument must be a reference or nullable value type.</span></span> <span data-ttu-id="b7120-153">첫 번째 인수가로 계산 되는 경우 `Nothing` 두 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-153">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="b7120-154">다른 모든 경우에는 첫 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-154">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="b7120-155">다음 예에서는이 평가의 작동 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7120-155">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="b7120-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7120-156">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="b7120-157">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="b7120-157">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="b7120-158">Nothing</span><span class="sxs-lookup"><span data-stu-id="b7120-158">Nothing</span></span>](../nothing.md)
