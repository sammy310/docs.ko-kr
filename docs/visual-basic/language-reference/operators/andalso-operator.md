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
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859893"
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="5d54a-102">AndAlso 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d54a-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="5d54a-103">두 식에 논리 결합을 단락 (short-circuiting)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d54a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d54a-104">Syntax</span></span>  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="5d54a-105">요소</span><span class="sxs-lookup"><span data-stu-id="5d54a-105">Parts</span></span>  
  
|<span data-ttu-id="5d54a-106">용어</span><span class="sxs-lookup"><span data-stu-id="5d54a-106">Term</span></span>|<span data-ttu-id="5d54a-107">정의</span><span class="sxs-lookup"><span data-stu-id="5d54a-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="5d54a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5d54a-108">Required.</span></span> <span data-ttu-id="5d54a-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-109">Any `Boolean` expression.</span></span> <span data-ttu-id="5d54a-110">결과 `Boolean` 두 식의 비교의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="5d54a-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5d54a-111">Required.</span></span> <span data-ttu-id="5d54a-112">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="5d54a-113">필수.</span><span class="sxs-lookup"><span data-stu-id="5d54a-113">Required.</span></span> <span data-ttu-id="5d54a-114">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d54a-115">설명</span><span class="sxs-lookup"><span data-stu-id="5d54a-115">Remarks</span></span>  
 <span data-ttu-id="5d54a-116">논리 연산 이라고 *단락 (short-circuiting)* 컴파일된 코드를 다른 식의 결과 따라 하나의 식의 평가 건너뛸 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="5d54a-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="5d54a-117">작업의 최종 결과 결정 하는 계산 되는 첫 번째 식의 결과 경우 두 번째 식을 평가 하지 않아도 최종 결과 변경할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="5d54a-118">단락 (short-circuiting) 바이패스 된 식이 복잡 한 경우 또는 프로시저 호출이 포함 되는 경우 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="5d54a-119">두 식이 모두로 평가 되 면 `True`, `result` 는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="5d54a-120">다음 표에서 설명 하는 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="5d54a-121">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="5d54a-121">If `expression1` is</span></span>|<span data-ttu-id="5d54a-122">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="5d54a-122">And `expression2` is</span></span>|<span data-ttu-id="5d54a-123">변수의 `result` 는</span><span class="sxs-lookup"><span data-stu-id="5d54a-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="5d54a-124">(평가 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="5d54a-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="5d54a-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5d54a-125">Data Types</span></span>  
 <span data-ttu-id="5d54a-126">`AndAlso` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="5d54a-127">Visual Basic 변환 필요에 따라 각 피연산자 `Boolean` 식을 계산 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-127">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="5d54a-128">Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식에는 `False` 됩니다 `0` 하 고 `True` 됩니다 `-1`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="5d54a-129">자세한 내용은 참조 하세요. [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="5d54a-129">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="5d54a-130">오버로딩</span><span class="sxs-lookup"><span data-stu-id="5d54a-130">Overloading</span></span>  
 <span data-ttu-id="5d54a-131">[및 연산자](../../../visual-basic/language-reference/operators/and-operator.md) 하며 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md) 일 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 동작의 형식에 클래스 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-131">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5d54a-132">오버 로드는 `And` 하 고 `IsFalse` 연산자의 동작에 영향을 줍니다는 `AndAlso` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-132">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="5d54a-133">코드를 사용 하는 경우 `AndAlso` 클래스 또는 구조체에 오버 로드에서 `And` 및 `IsFalse`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-133">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="5d54a-134">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d54a-134">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d54a-135">예제</span><span class="sxs-lookup"><span data-stu-id="5d54a-135">Example</span></span>  
 <span data-ttu-id="5d54a-136">다음 예제에서는 `AndAlso` 두 식에 논리 결합을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-136">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="5d54a-137">결과 `Boolean` 전체 식이 있는지 여부를 나타내는 값이 true입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-137">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="5d54a-138">첫 번째 식이 `False`, 두 번째는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-138">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 <span data-ttu-id="5d54a-139">앞의 예제 결과 생성 `True`, `False`, 및 `False`, 각각.</span><span class="sxs-lookup"><span data-stu-id="5d54a-139">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="5d54a-140">계산에서 `secondCheck`, 첫 번째는 이미 이므로는 두 번째 식은 계산 되지 않습니다 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-140">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="5d54a-141">그러나 두 번째 식 계산에서 계산 됩니다 `thirdCheck`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-141">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d54a-142">예제</span><span class="sxs-lookup"><span data-stu-id="5d54a-142">Example</span></span>  
 <span data-ttu-id="5d54a-143">다음 예제와 `Function` 배열의 요소 중에서 지정 된 값을 검색 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-143">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="5d54a-144">배열이 비어 있는 경우 또는 배열 길이 초과 하는 경우는 `While` 문은 검색 값을 비교 하 여 배열 요소를 테스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d54a-144">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a><span data-ttu-id="5d54a-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d54a-145">See also</span></span>

- [<span data-ttu-id="5d54a-146">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d54a-146">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="5d54a-147">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="5d54a-147">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5d54a-148">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="5d54a-148">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5d54a-149">And 연산자</span><span class="sxs-lookup"><span data-stu-id="5d54a-149">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)
- [<span data-ttu-id="5d54a-150">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="5d54a-150">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="5d54a-151">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="5d54a-151">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
