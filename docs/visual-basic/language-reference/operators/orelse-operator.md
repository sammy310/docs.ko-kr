---
title: OrElse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 8290e642db3ec76a931bdd2febe427309457bc86
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835240"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="a121a-102">OrElse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a121a-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="a121a-103">두 식에 순환이 짧은 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a121a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a121a-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a121a-105">요소</span><span class="sxs-lookup"><span data-stu-id="a121a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a121a-106">필수.</span><span class="sxs-lookup"><span data-stu-id="a121a-106">Required.</span></span> <span data-ttu-id="a121a-107">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a121a-108">필수.</span><span class="sxs-lookup"><span data-stu-id="a121a-108">Required.</span></span> <span data-ttu-id="a121a-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a121a-110">필수.</span><span class="sxs-lookup"><span data-stu-id="a121a-110">Required.</span></span> <span data-ttu-id="a121a-111">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a121a-112">설명</span><span class="sxs-lookup"><span data-stu-id="a121a-112">Remarks</span></span>  
 <span data-ttu-id="a121a-113">컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 무시할 수 있는 경우 논리 연산을 *단락* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="a121a-114">계산 된 첫 번째 식의 결과가 작업의 최종 결과를 결정 하는 경우 최종 결과를 변경할 수 없기 때문에 두 번째 식을 계산할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="a121a-115">생략 된 식이 복잡 하거나 프로시저 호출이 포함 된 경우 단락을 통해 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="a121a-116">두 식 중 하나 또는 둘 다가 `True`으로 평가 되는 경우 `result`은 `True`입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="a121a-117">다음 표에서는 `result`이 결정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a121a-118">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="a121a-118">If `expression1` is</span></span>|<span data-ttu-id="a121a-119">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="a121a-119">And `expression2` is</span></span>|<span data-ttu-id="a121a-120">값 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="a121a-121">(평가 안 함)</span><span class="sxs-lookup"><span data-stu-id="a121a-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="a121a-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a121a-122">Data Types</span></span>  
 <span data-ttu-id="a121a-123">@No__t-0 연산자는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)에 대해서만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="a121a-124">Visual Basic는 식을 계산 하기 전에 필요에 따라 각 피연산자를 `Boolean`으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="a121a-125">숫자 형식에 결과를 할당 하는 경우 Visual Basic은 `Boolean`에서 해당 형식으로 변환 합니다. 즉, `False`이 `0`이 고 `True`이 `-1`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="a121a-126">자세한 내용은 [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a121a-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="a121a-127">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a121a-127">Overloading</span></span>  
 <span data-ttu-id="a121a-128">[Or 연산자](../../../visual-basic/language-reference/operators/or-operator.md) 와 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a121a-129">@No__t-0 및 `IsTrue` 연산자를 오버 로드 하면 `OrElse` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="a121a-130">코드에서-1 @no__t 오버 로드 하는 클래스 또는 구조체에 `OrElse`을 사용 하는 경우 @no__t 다시 정의 된 동작을 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="a121a-131">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a121a-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a121a-132">예제</span><span class="sxs-lookup"><span data-stu-id="a121a-132">Example</span></span>  
 <span data-ttu-id="a121a-133">다음 예에서는 `OrElse` 연산자를 사용 하 여 두 식에 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="a121a-134">결과는 두 식 중 하나가 true 인지 여부를 나타내는 0 @no__t 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="a121a-135">첫 번째 식이 0 @no__t 경우 두 번째 식이 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="a121a-136">앞의 예제에서는 `True`, `True` 및 `False`의 결과를 각각 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="a121a-137">@No__t-0을 계산 하는 경우 첫 번째 식은 이미 `True` 이기 때문에 두 번째 식은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="a121a-138">그러나 두 번째 식은 `secondCheck` 계산에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a121a-139">예제</span><span class="sxs-lookup"><span data-stu-id="a121a-139">Example</span></span>  
 <span data-ttu-id="a121a-140">다음 예에서는 두 개의 프로시저 호출을 포함 하는 `If` `Then` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="a121a-141">첫 번째 호출이 `True`을 반환 하면 두 번째 프로시저가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="a121a-142">이 경우 코드의이 섹션이 실행 될 때 항상 수행 해야 하는 중요 한 작업을 두 번째 절차에서 수행할 경우 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a121a-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="a121a-143">참조</span><span class="sxs-lookup"><span data-stu-id="a121a-143">See also</span></span>

- [<span data-ttu-id="a121a-144">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a121a-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="a121a-145">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a121a-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a121a-146">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a121a-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a121a-147">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="a121a-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="a121a-148">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="a121a-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="a121a-149">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="a121a-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
