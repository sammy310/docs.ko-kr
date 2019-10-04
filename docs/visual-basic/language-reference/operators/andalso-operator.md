---
title: AndAlso 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835221"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="c73d5-102">AndAlso 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c73d5-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="c73d5-103">두 식에 순환이 짧은 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c73d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="c73d5-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c73d5-105">요소</span><span class="sxs-lookup"><span data-stu-id="c73d5-105">Parts</span></span>  
  
|<span data-ttu-id="c73d5-106">용어</span><span class="sxs-lookup"><span data-stu-id="c73d5-106">Term</span></span>|<span data-ttu-id="c73d5-107">정의</span><span class="sxs-lookup"><span data-stu-id="c73d5-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="c73d5-108">필수.</span><span class="sxs-lookup"><span data-stu-id="c73d5-108">Required.</span></span> <span data-ttu-id="c73d5-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-109">Any `Boolean` expression.</span></span> <span data-ttu-id="c73d5-110">결과는 두 식을 비교한 결과 0 @no__t입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="c73d5-111">필수.</span><span class="sxs-lookup"><span data-stu-id="c73d5-111">Required.</span></span> <span data-ttu-id="c73d5-112">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="c73d5-113">필수.</span><span class="sxs-lookup"><span data-stu-id="c73d5-113">Required.</span></span> <span data-ttu-id="c73d5-114">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c73d5-115">설명</span><span class="sxs-lookup"><span data-stu-id="c73d5-115">Remarks</span></span>  
 <span data-ttu-id="c73d5-116">컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 무시할 수 있는 경우 논리 연산을 *단락* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="c73d5-117">계산 된 첫 번째 식의 결과가 작업의 최종 결과를 결정 하는 경우 최종 결과를 변경할 수 없기 때문에 두 번째 식을 계산할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="c73d5-118">생략 된 식이 복잡 하거나 프로시저 호출이 포함 된 경우 단락을 통해 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="c73d5-119">두 식이 모두 `True`으로 계산 되는 경우-1 @no__t `True`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="c73d5-120">다음 표에서는 `result`이 결정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c73d5-121">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="c73d5-121">If `expression1` is</span></span>|<span data-ttu-id="c73d5-122">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="c73d5-122">And `expression2` is</span></span>|<span data-ttu-id="c73d5-123">값 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="c73d5-124">(평가 안 함)</span><span class="sxs-lookup"><span data-stu-id="c73d5-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="c73d5-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c73d5-125">Data Types</span></span>  
 <span data-ttu-id="c73d5-126">@No__t-0 연산자는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)에 대해서만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="c73d5-127">Visual Basic는 식을 계산 하기 전에 필요에 따라 각 피연산자를 `Boolean`으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="c73d5-128">숫자 형식에 결과를 할당 하는 경우 Visual Basic은 `Boolean`에서 해당 형식으로 변환 합니다. 즉, `False`이 `0`이 고 `True`이 `-1`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="c73d5-129">자세한 내용은 [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c73d5-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="c73d5-130">오버로딩</span><span class="sxs-lookup"><span data-stu-id="c73d5-130">Overloading</span></span>  
 <span data-ttu-id="c73d5-131">[And 연산자](../../../visual-basic/language-reference/operators/and-operator.md) 와 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c73d5-132">@No__t-0 및 `IsFalse` 연산자를 오버 로드 하면 `AndAlso` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="c73d5-133">코드에서-1 @no__t 오버 로드 하는 클래스 또는 구조체에 `AndAlso`을 사용 하는 경우 @no__t 다시 정의 된 동작을 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="c73d5-134">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c73d5-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c73d5-135">예제</span><span class="sxs-lookup"><span data-stu-id="c73d5-135">Example</span></span>  
 <span data-ttu-id="c73d5-136">다음 예에서는 `AndAlso` 연산자를 사용 하 여 두 식에 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c73d5-137">결과는 전체 앞쪽 식이 true 인지 여부를 나타내는 0 @no__t 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="c73d5-138">첫 번째 식이 0 @no__t 경우 두 번째 식이 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="c73d5-139">앞의 예제에서는 `True`, `False` 및 `False`의 결과를 각각 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="c73d5-140">@No__t-0을 계산 하는 경우 첫 번째 식은 이미 `False` 이기 때문에 두 번째 식은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="c73d5-141">그러나 두 번째 식은 `thirdCheck` 계산에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c73d5-142">예제</span><span class="sxs-lookup"><span data-stu-id="c73d5-142">Example</span></span>  
 <span data-ttu-id="c73d5-143">다음 예제에서는 배열 요소 중에서 지정 된 값을 검색 하는 `Function` 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="c73d5-144">배열이 비어 있거나 배열 길이가 초과 된 경우 `While` 문은 검색 값에 대해 배열 요소를 테스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c73d5-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="c73d5-145">참조</span><span class="sxs-lookup"><span data-stu-id="c73d5-145">See also</span></span>

- [<span data-ttu-id="c73d5-146">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c73d5-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="c73d5-147">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="c73d5-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c73d5-148">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="c73d5-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c73d5-149">And 연산자</span><span class="sxs-lookup"><span data-stu-id="c73d5-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="c73d5-150">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="c73d5-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="c73d5-151">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="c73d5-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
