---
title: If 연산자(Visual Basic)
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
ms.openlocfilehash: 9ab01755d75c91ce87acf83e7f406b26c466aef6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834637"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="ae3fd-102">If 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae3fd-102">If Operator (Visual Basic)</span></span>
<span data-ttu-id="ae3fd-103">사용 조건에 따라 두 값 중 하나를 반환 하는 평가 단락 (short-circuit).</span><span class="sxs-lookup"><span data-stu-id="ae3fd-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="ae3fd-104">`If` 세 개의 인수를 사용 하 여 또는 두 개의 인수를 사용 하 여 연산자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-104">The `If` operator can be called with three arguments or with two arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3fd-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae3fd-105">Syntax</span></span>  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="ae3fd-106">세 개의 인수를 사용 하 여 호출 연산자</span><span class="sxs-lookup"><span data-stu-id="ae3fd-106">If Operator Called with Three Arguments</span></span>  
 <span data-ttu-id="ae3fd-107">때 `If` 라고 세 개의 인수를 사용 하 여 첫 번째 인수도 캐스팅 될 수 있는 값으로 계산 되어야 합니다는 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="ae3fd-108">`Boolean` 계산 되어 반환 되는 다른 두 인수의 값이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="ae3fd-109">다음과 같은 경우에만 적용 되는 `If` 세 개의 인수를 사용 하 여 연산자 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="ae3fd-110">요소</span><span class="sxs-lookup"><span data-stu-id="ae3fd-110">Parts</span></span>  
  
|<span data-ttu-id="ae3fd-111">용어</span><span class="sxs-lookup"><span data-stu-id="ae3fd-111">Term</span></span>|<span data-ttu-id="ae3fd-112">정의</span><span class="sxs-lookup"><span data-stu-id="ae3fd-112">Definition</span></span>|  
|---|---|  
|`argument1`|<span data-ttu-id="ae3fd-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-113">Required.</span></span> <span data-ttu-id="ae3fd-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-114">`Boolean`.</span></span> <span data-ttu-id="ae3fd-115">다른 인수는 평가 및 반환할 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-115">Determines which of the other arguments to evaluate and return.</span></span>|  
|`argument2`|<span data-ttu-id="ae3fd-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-116">Required.</span></span> <span data-ttu-id="ae3fd-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-117">`Object`.</span></span> <span data-ttu-id="ae3fd-118">평가 되 고 반환 된 경우 `argument1` 로 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|  
|`argument3`|<span data-ttu-id="ae3fd-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-119">Required.</span></span> <span data-ttu-id="ae3fd-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-120">`Object`.</span></span> <span data-ttu-id="ae3fd-121">평가 되 고 반환 된 경우 `argument1` 로 `False` 이거나 `argument1` 은 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 계산 되는 변수 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|  
  
 <span data-ttu-id="ae3fd-122">`If` 처럼 작동 하는 세 개의 인수를 사용 하 여 호출 되는 연산자는 `IIf` 함수를 사용 한다는 점을 제외 하 고 단락 (short-circuit) 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="ae3fd-123">`IIf` 함수는 항상 해당 인수의 모든 세를 계산 하지만 `If` 세 개의 인수가 있는 연산자 중 두 개만 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="ae3fd-124">첫 번째 `If` 인수가 계산 되 고로 캐스팅 결과 `Boolean` 값을 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="ae3fd-125">값이 `True`, `argument2` 가 평가 하 고 해당 값이 반환 하지만 `argument3` 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="ae3fd-126">경우 값을 `Boolean` 식이 `False`, `argument3` 는 평가 하 고 해당 값이 반환 하지만 `argument2` 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="ae3fd-127">다음 예제에서는 사용법을 보여 줍니다. `If` 세 개의 인수를 사용 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ae3fd-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 <span data-ttu-id="ae3fd-128">값을 보여 주는 다음 예제에서는 평가 단락 (short-circuit).</span><span class="sxs-lookup"><span data-stu-id="ae3fd-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="ae3fd-129">이 예제에서는 변수를 나누는 데 두 시도 보여 줍니다 `number` 변수로 `divisor` 경우를 제외 하 고 `divisor` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="ae3fd-130">이런 경우 0이 반환 되어야 합니다 및 하지 수행 되도록 하면 런타임 오류가 발생 하 게 됩니다 나누기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="ae3fd-131">때문에 `If` 사용 되는 식 평가 단락 (short-circuit), 두 번째 또는 첫 번째 인수의 값에 따라 세 번째 인수를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="ae3fd-132">첫 번째 인수가 true 이면 제 수 0이 아니면 및 두 번째 인수를 평가 하 고 나누기를 수행 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="ae3fd-133">첫 번째 인수가 false 이면 세 번째 인수에만 평가 되 고 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="ae3fd-134">따라서 제 수 0 인 경우 하지 나누기 하지 않으며 오류가 발생 하는 데 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="ae3fd-135">그러나 때문에 `IIf` 사용 하지 않는 평가 단락 (short-circuit), 두 번째 인수는 첫 번째 인수가 false 인 경우에 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="ae3fd-136">이 런타임에 0으로 나누기 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-136">This causes a run-time divide-by-zero error.</span></span>  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="ae3fd-137">연산자는 두 개의 인수를 사용 하 여 호출 하는 경우</span><span class="sxs-lookup"><span data-stu-id="ae3fd-137">If Operator Called with Two Arguments</span></span>  
 <span data-ttu-id="ae3fd-138">첫 번째 인수 `If` 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="ae3fd-139">이 연산자를를 두 개의 인수를 사용 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="ae3fd-140">다음과 같은 경우에만 적용 되는 `If` 연산자는 두 개의 인수를 사용 하 여 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-140">The following list applies only when the `If` operator is called with two arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="ae3fd-141">요소</span><span class="sxs-lookup"><span data-stu-id="ae3fd-141">Parts</span></span>  
  
|<span data-ttu-id="ae3fd-142">용어</span><span class="sxs-lookup"><span data-stu-id="ae3fd-142">Term</span></span>|<span data-ttu-id="ae3fd-143">정의</span><span class="sxs-lookup"><span data-stu-id="ae3fd-143">Definition</span></span>|  
|---|---|  
|`argument2`|<span data-ttu-id="ae3fd-144">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-144">Required.</span></span> <span data-ttu-id="ae3fd-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-145">`Object`.</span></span> <span data-ttu-id="ae3fd-146">참조 또는 nullable 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="ae3fd-147">계산 되 고 이외의 값으로 계산 될 때 반환 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|  
|`argument3`|<span data-ttu-id="ae3fd-148">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-148">Required.</span></span> <span data-ttu-id="ae3fd-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-149">`Object`.</span></span> <span data-ttu-id="ae3fd-150">평가 되 고 반환 된 경우 `argument2` 로 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|  
  
 <span data-ttu-id="ae3fd-151">경우는 `Boolean` 인수를 생략 하면, 첫 번째 인수는 참조 또는 nullable 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="ae3fd-152">첫 번째 인수를 평가 하는 경우 `Nothing`, 두 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="ae3fd-153">다른 모든 경우에 첫 번째 인수의 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="ae3fd-154">다음 예제에서는이 평가 작동 원리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae3fd-154">The following example illustrates how this evaluation works.</span></span>  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="ae3fd-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae3fd-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="ae3fd-156">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="ae3fd-156">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ae3fd-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="ae3fd-157">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
