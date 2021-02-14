---
description: '자세한 정보: 논리 및 비트 연산자 Visual Basic'
title: 논리 및 비트 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 55d9567813a9114573e1e3f70fe181cb8621b350
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472724"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="47dd9-103">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="47dd9-103">Logical and Bitwise Operators in Visual Basic</span></span>

<span data-ttu-id="47dd9-104">논리 연산자 `Boolean` 는 식을 비교 하 고 `Boolean` 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-104">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="47dd9-105">`And`,, `Or` `AndAlso` , `OrElse` 및 연산자는 `Xor` 두 개의 피연산자를 사용 하는 반면 *이항* 는 `Not` 단일 피연산자를 사용 하기 때문에 *단항* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-105">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="47dd9-106">이러한 연산자 중 일부는 정수 값에 대해 비트 논리적 연산을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-106">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="47dd9-107">단항 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="47dd9-107">Unary Logical Operator</span></span>  

 <span data-ttu-id="47dd9-108">[Not 연산자](../../../language-reference/operators/not-operator.md) 는 식에 논리 *부정을* 수행 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-108">The [Not Operator](../../../language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="47dd9-109">피연산자와 반대 되는 논리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-109">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="47dd9-110">식이로 계산 되 면 `True` 를 반환 하 고, `Not` `False` 식이로 계산 되 면를 반환 `False` `Not` `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-110">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="47dd9-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-111">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="47dd9-112">이항 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="47dd9-112">Binary Logical Operators</span></span>  

 <span data-ttu-id="47dd9-113">[And 연산자](../../../language-reference/operators/and-operator.md) 는 두 식에 논리 *결합* 을 수행 `Boolean` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-113">The [And Operator](../../../language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="47dd9-114">두 식이 모두로 계산 `True` 되 면를 `And` 반환 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-114">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="47dd9-115">식 중 하나 이상이로 평가 `False` 되 면를 `And` 반환 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-115">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="47dd9-116">[Or 연산자](../../../language-reference/operators/or-operator.md) 는 두 식  에 논리합  연산을 수행 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-116">The [Or Operator](../../../language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="47dd9-117">두 식이 모두로 계산 `True` 되거나 모두로 계산 `True` 되 면이 `Or` 반환 `True` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-117">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="47dd9-118">식이로 계산 되지 않는 경우 `True` 는을 `Or` 반환 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-118">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="47dd9-119">[Xor 연산자](../../../language-reference/operators/xor-operator.md) 는 두 식에 대해 논리적 *제외* 를 수행 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-119">The [Xor Operator](../../../language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="47dd9-120">정확히 하나의 식이로 계산 `True` 되지만 둘 다로 계산 되지 않는 경우는를 `Xor` 반환 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-120">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="47dd9-121">두 식이 모두로 계산 `True` 되거나 모두로 계산 `False` 되는 경우는를 `Xor` 반환 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-121">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="47dd9-122">다음 예에서는 `And` , 및 연산자를 보여 줍니다 `Or` `Xor` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-122">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="47dd9-123">Short-Circuiting 논리 작업</span><span class="sxs-lookup"><span data-stu-id="47dd9-123">Short-Circuiting Logical Operations</span></span>  

 <span data-ttu-id="47dd9-124">[AndAlso 연산자](../../../language-reference/operators/andalso-operator.md) 는 `And` 두 식에서 논리적 결합도 수행 한다는 점에서 연산자와 매우 비슷합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-124">The [AndAlso Operator](../../../language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="47dd9-125">둘 사이의 주요 차이점은 `AndAlso` *단락* 동작을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-125">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="47dd9-126">식의 첫 번째 식이 `AndAlso` 로 계산 되는 경우 `False` 최종 결과를 변경할 수 없고를 반환할 수 없으므로 두 번째 식이 계산 되지 않습니다 `AndAlso` `False` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-126">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="47dd9-127">마찬가지로 [OrElse 연산자](../../../language-reference/operators/orelse-operator.md) 는 두 식에 순환이 짧은 논리 분리를 수행 `Boolean` 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-127">Similarly, the [OrElse Operator](../../../language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="47dd9-128">식의 첫 번째 식이 `OrElse` 로 계산 되는 경우 `True` 최종 결과를 변경할 수 없고를 반환할 수 없으므로 두 번째 식이 계산 되지 않습니다 `OrElse` `True` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-128">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="47dd9-129">Short-Circuiting Trade-Offs</span><span class="sxs-lookup"><span data-stu-id="47dd9-129">Short-Circuiting Trade-Offs</span></span>  

 <span data-ttu-id="47dd9-130">단락을 통해 논리 연산의 결과를 변경할 수 없는 식을 계산 하지 않고 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-130">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="47dd9-131">그러나 해당 식에서 추가 작업을 수행 하는 경우 단락에서는 이러한 작업을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-131">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="47dd9-132">예를 들어 식에 프로시저에 대 한 호출이 포함 된 경우 `Function` 식이 short short-circuit 경우 해당 프로시저는 호출 되지 않으며에 포함 된 추가 코드는 `Function` 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-132">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="47dd9-133">따라서 함수는 가끔씩만 실행 될 수 있으며 제대로 테스트 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-133">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="47dd9-134">또는 프로그램 논리는의 코드에 따라 달라질 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-134">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="47dd9-135">다음 예제에서는 `And` , 및의 단락에 대 한 차이점을 보여 줍니다 `Or` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-135">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="47dd9-136">앞의 예제에서 내부의 일부 중요 한 코드는 `checkIfValid()` 호출이 단기 short-circuit 때 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-136">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="47dd9-137">`If` `checkIfValid()` `12 > 45` `False` 가 short 회로를 포함 하지 않기 때문에 첫 번째 문은를 반환 합니다 `And` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-137">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="47dd9-138">두 번째 `If` 문은가를 `checkIfValid()` `12 > 45` 반환할 때 `False` `AndAlso` 두 번째 식을 short 회로 하므로를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-138">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="47dd9-139">`If` `checkIfValid()` `12 < 45` `True` 이 짧은 회로를 포함 하지 않으므로 세 번째 문은를 반환 하지만를 호출 합니다 `Or` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-139">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="47dd9-140">가를 `If` `checkIfValid()` `12 < 45` 반환 하면 `True` `OrElse` 두 번째 식을 short 회로 하므로 네 번째 문은를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-140">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="47dd9-141">비트 연산</span><span class="sxs-lookup"><span data-stu-id="47dd9-141">Bitwise Operations</span></span>  

 <span data-ttu-id="47dd9-142">비트 연산은 이진 (기본 2) 형식으로 두 개의 정수 값을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-142">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="47dd9-143">해당 위치의 비트를 비교한 다음 비교에 따라 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-143">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="47dd9-144">다음 예에서는 연산자를 보여 줍니다 `And` .</span><span class="sxs-lookup"><span data-stu-id="47dd9-144">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="47dd9-145">앞의 예제에서는의 값을 `x` 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-145">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="47dd9-146">이 문제는 다음과 같은 이유로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-146">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="47dd9-147">값은 binary로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-147">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="47dd9-148">3 이진 형식 = 011</span><span class="sxs-lookup"><span data-stu-id="47dd9-148">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="47dd9-149">5 이진 형식 = 101</span><span class="sxs-lookup"><span data-stu-id="47dd9-149">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="47dd9-150">`And`연산자는 한 번에 하나의 이진 위치 (비트)를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-150">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="47dd9-151">지정 된 위치에 있는 두 비트가 모두 1 이면 결과의 해당 위치에 1이 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-151">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="47dd9-152">두 비트가 모두 0 인 경우 결과의 해당 위치에 0이 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-152">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="47dd9-153">위의 예제에서는 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-153">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="47dd9-154">011 (이진 형식의 경우 3)</span><span class="sxs-lookup"><span data-stu-id="47dd9-154">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="47dd9-155">101 (이진 형식의 5)</span><span class="sxs-lookup"><span data-stu-id="47dd9-155">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="47dd9-156">001 (이진 형식으로 된 결과)</span><span class="sxs-lookup"><span data-stu-id="47dd9-156">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="47dd9-157">결과는 10 진수로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-157">The result is treated as decimal.</span></span> <span data-ttu-id="47dd9-158">값 001은 1의 이진 표현 이므로 `x` = 1입니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-158">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="47dd9-159">비교 하는 비트 `Or` 중 하나 또는 둘 다가 1 이면 결과 비트에 1이 할당 된다는 점을 제외 하 고 비트 연산은 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-159">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="47dd9-160">`Xor` 비교 된 비트 (둘 다) 중 정확히 하나가 1 이면 결과 비트에 1을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-160">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="47dd9-161">`Not` 단일 피연산자를 사용 하 고 부호 비트를 포함 하 여 모든 비트를 반전 하 고 결과에 해당 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-161">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="47dd9-162">즉, 부호 있는 양수의 경우 `Not` 항상 음수 값을 반환 하 고 음수에 대해는 `Not` 항상 양수 또는 0 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-162">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="47dd9-163">`AndAlso`및 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-163">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47dd9-164">비트 연산은 정수 계열 형식에 대해서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-164">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="47dd9-165">비트 연산을 계속 하려면 부동 소수점 값을 정수 계열 형식으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47dd9-165">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47dd9-166">추가 정보</span><span class="sxs-lookup"><span data-stu-id="47dd9-166">See also</span></span>

- [<span data-ttu-id="47dd9-167">논리/비트 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47dd9-167">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="47dd9-168">부울 식</span><span class="sxs-lookup"><span data-stu-id="47dd9-168">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="47dd9-169">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="47dd9-169">Arithmetic Operators in Visual Basic</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="47dd9-170">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47dd9-170">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="47dd9-171">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="47dd9-171">Concatenation Operators in Visual Basic</span></span>](concatenation-operators.md)
- [<span data-ttu-id="47dd9-172">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="47dd9-172">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
