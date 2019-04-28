---
title: Visual Basic의 논리 및 비트 연산자
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
ms.openlocfilehash: ac47b6d7fa4861d18646a23f442caccc4062852f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864497"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="b691e-102">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="b691e-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="b691e-103">논리 연산자 비교 `Boolean` 식 및 반환 된 `Boolean` 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="b691e-104">합니다 `And`, `Or`, `AndAlso`, `OrElse`, 및 `Xor` 연산자는 *이진* 하는 동안 두 개의 피연산자를 고려 하기 때문에 `Not` 연산자는 *단항* 단일 피연산자 걸리기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="b691e-105">이러한 연산자 중 일부에 정수 계열 값의 비트 논리 연산을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="b691e-106">단항 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="b691e-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="b691e-107">합니다 [Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md) 논리 수행 *부정* 에 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="b691e-108">피연산자의 논리적 반대를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="b691e-109">식이 계산 되는 경우 `True`, 한 다음 `Not` 반환 `False`같으면 식의 결과가 `False`, 다음 `Not` 반환 `True`.</span><span class="sxs-lookup"><span data-stu-id="b691e-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="b691e-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="b691e-111">이진 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="b691e-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="b691e-112">합니다 [및 연산자](../../../../visual-basic/language-reference/operators/and-operator.md) 논리 수행 *함께* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="b691e-113">두 식이 모두로 평가 되 면 `True`, 한 다음 `And` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="b691e-114">로 평가 되 면 식 중 하나 이상이 `False`, 한 다음 `And` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="b691e-115">합니다 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 논리 수행 *분리* 또는 *포함* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="b691e-116">두 식 중 하나가 경우 `True`, 이거나 두 식이 `True`, 한 다음 `Or` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="b691e-117">두 식이 모두 하는 경우 `True`, `Or` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="b691e-118">합니다 [Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md) 논리 수행 *제외* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="b691e-119">정확히 하나의 식이 `True`, 하지만 둘 다는 아님 `Xor` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="b691e-120">두 식이 모두로 평가 되 면 `True` 이거나 두 식이 `False`를 `Xor` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="b691e-121">다음 예제는 `And`, `Or`, 및 `Xor` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="b691e-122">논리 연산자를 단락 (short-circuiting)</span><span class="sxs-lookup"><span data-stu-id="b691e-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="b691e-123">[AndAlso 연산자](../../../../visual-basic/language-reference/operators/andalso-operator.md) 매우 비슷합니다는 `And` 연산자는 두 대 한 논리 결합을 수행 `Boolean` 식.</span><span class="sxs-lookup"><span data-stu-id="b691e-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="b691e-124">둘 사이의 주요 차이점은 `AndAlso` 보여 *단락 (short-circuiting)* 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="b691e-125">경우 첫 번째 식을 `AndAlso` 식이 `False`, 최종 결과 변경할 수 없습니다 때문에 두 번째 식은 평가 되지 됩니다 하 고 `AndAlso` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="b691e-126">마찬가지로, 합니다 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md) 두 논리 분리를 단락 (short-circuiting) 수행 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="b691e-127">경우 첫 번째 식을 `OrElse` 식이 `True`, 최종 결과 변경할 수 없습니다 때문에 두 번째 식은 평가 되지 됩니다 하 고 `OrElse` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="b691e-128">장단점을 단락 (short-circuiting)</span><span class="sxs-lookup"><span data-stu-id="b691e-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="b691e-129">단락 (short-circuiting) 논리 작업의 결과 변경할 수 없는 식을 계산 하지 않아 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="b691e-130">그러나 해당 식을 추가 작업을 수행 하는 경우 해당 작업을 건너뜁니다 단락 (short-circuiting).</span><span class="sxs-lookup"><span data-stu-id="b691e-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="b691e-131">예를 들어 식에 대 한 호출을 포함 하는 경우는 `Function` 프로시저, 식 대해서는 처리가 단축, 이며 추가 코드에 포함 하는 경우 프로시저 호출 되지 않습니다는 `Function` 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="b691e-132">따라서 함수는 가끔씩만 실행 될 수 있습니다 하 고 올바르게 테스트 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="b691e-133">프로그램 논리의 코드에 따라 달라질 수 있습니다 또는 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="b691e-134">다음 예제에서는 차이점을 보여 줍니다 `And`, `Or`, 및 단락 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="b691e-135">앞의 예제에서는 몇 가지 중요 한 코드 내에서 `checkIfValid()` 호출이 대해서는 처리가 단축 될 때 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="b691e-136">첫 번째 `If` 문 호출 `checkIfValid()` 하더라도 `12 > 45` 반환 `False`이므로 `And` 단락 (short-circuit) 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="b691e-137">두 번째 `If` 호출 하지 않습니다 `checkIfValid()`이므로 때 `12 > 45` 반환 `False`, `AndAlso` 두 번째 식을 단락 (short-circuit).</span><span class="sxs-lookup"><span data-stu-id="b691e-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="b691e-138">세 번째 `If` 문 호출 `checkIfValid()` 하더라도 `12 < 45` 반환 `True`이므로 `Or` 단락 (short-circuit) 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="b691e-139">네 번째 `If` 호출 하지 않습니다 `checkIfValid()`이므로 때 `12 < 45` 반환 `True`, `OrElse` 두 번째 식을 단락 (short-circuit).</span><span class="sxs-lookup"><span data-stu-id="b691e-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="b691e-140">비트 연산</span><span class="sxs-lookup"><span data-stu-id="b691e-140">Bitwise Operations</span></span>  
 <span data-ttu-id="b691e-141">비트 연산의 이진 (밑 2) 형태로 두 정수 값을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="b691e-142">해당 위치의 비트를 비교 하 고 비교를 기반으로 하는 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="b691e-143">다음 예제는 `And` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="b691e-144">값을 설정 하는 앞의 예제 `x` 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="b691e-145">다음과 같은 이유로 현상이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="b691e-146">값은 이진 형식으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="b691e-147">이진 형식에서 3 011 =</span><span class="sxs-lookup"><span data-stu-id="b691e-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="b691e-148">이진 형식에서 5 101 =</span><span class="sxs-lookup"><span data-stu-id="b691e-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="b691e-149">`And` 연산자는 한 번에 하나의 이진 위치 (비트)에서 이진 표현을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="b691e-150">지정된 된 위치에 두 비트가 모두 1 이면 1 결과에 해당 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="b691e-151">두 비트가 모두 0 인 경우 0은 결과에 해당 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="b691e-152">앞의 예제에서이 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="b691e-153">011 (이진 형태로 3)</span><span class="sxs-lookup"><span data-stu-id="b691e-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="b691e-154">101 (이진 형식에서 5)</span><span class="sxs-lookup"><span data-stu-id="b691e-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="b691e-155">001 (이진 형식에서 결과)</span><span class="sxs-lookup"><span data-stu-id="b691e-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="b691e-156">결과 10 진수로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-156">The result is treated as decimal.</span></span> <span data-ttu-id="b691e-157">001 값은 1의 이진 표현 되므로 `x` = 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="b691e-158">비트 `Or` 비교 비트 중 하나 또는 모두 1 이면 결과 비트는 1이 할당 한다는 점을 제외 하면 작업은 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="b691e-159">`Xor` 정확히 하나의 비교 비트 (둘 다)이 1 이면 결과 비트는 1을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="b691e-160">`Not` 단일 피연산자를 사용 하 고 비트를 부호를 포함 하 여 모든 비트를 반전 결과에 해당 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="b691e-161">부호 있는 양수, 즉 `Not` 항상 음수 값을 반환 합니다 및 음수 `Not` 항상 양수 또는 0 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="b691e-162">합니다 `AndAlso` 고 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b691e-163">비트 연산에서 정수 계열 형식 에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="b691e-164">부동 소수점 값 비트 연산을 수행 하려면 먼저 정수 계열 형식으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b691e-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b691e-165">참고자료</span><span class="sxs-lookup"><span data-stu-id="b691e-165">See also</span></span>

- [<span data-ttu-id="b691e-166">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b691e-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="b691e-167">부울 식</span><span class="sxs-lookup"><span data-stu-id="b691e-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="b691e-168">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="b691e-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="b691e-169">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b691e-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="b691e-170">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="b691e-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="b691e-171">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="b691e-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
