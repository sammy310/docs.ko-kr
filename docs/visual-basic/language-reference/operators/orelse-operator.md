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
ms.openlocfilehash: 02be78c8f2b7529f1fb0e46e9fe610a3c66b0652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860139"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="aff7e-102">OrElse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aff7e-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="aff7e-103">두 식에 포함 논리합을 단락 (short-circuiting)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="aff7e-104">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="aff7e-105">요소</span><span class="sxs-lookup"><span data-stu-id="aff7e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="aff7e-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="aff7e-106">Required.</span></span> <span data-ttu-id="aff7e-107">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="aff7e-108">필수.</span><span class="sxs-lookup"><span data-stu-id="aff7e-108">Required.</span></span> <span data-ttu-id="aff7e-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="aff7e-110">필수.</span><span class="sxs-lookup"><span data-stu-id="aff7e-110">Required.</span></span> <span data-ttu-id="aff7e-111">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aff7e-112">설명</span><span class="sxs-lookup"><span data-stu-id="aff7e-112">Remarks</span></span>  
 <span data-ttu-id="aff7e-113">논리 연산 이라고 *단락 (short-circuiting)* 컴파일된 코드를 다른 식의 결과 따라 하나의 식의 평가 건너뛸 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="aff7e-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="aff7e-114">작업의 최종 결과 결정 하는 계산 되는 첫 번째 식의 결과 경우 두 번째 식을 평가 하지 않아도 최종 결과 변경할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="aff7e-115">단락 (short-circuiting) 바이패스 된 식이 복잡 한 경우 또는 프로시저 호출이 포함 되는 경우 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="aff7e-116">식 중 하나 또는 둘 다로 평가 되 면 `True`, `result` 는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="aff7e-117">다음 표에서 설명 하는 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="aff7e-118">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="aff7e-118">If `expression1` is</span></span>|<span data-ttu-id="aff7e-119">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="aff7e-119">And `expression2` is</span></span>|<span data-ttu-id="aff7e-120">변수의 `result` 는</span><span class="sxs-lookup"><span data-stu-id="aff7e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="aff7e-121">(평가 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="aff7e-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="aff7e-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aff7e-122">Data Types</span></span>  
 <span data-ttu-id="aff7e-123">`OrElse` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="aff7e-124">Visual Basic 변환 필요에 따라 각 피연산자 `Boolean` 식을 계산 하기 전에 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-124">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="aff7e-125">Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식에는 `False` 됩니다 `0` 하 고 `True` 됩니다 `-1`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="aff7e-126">자세한 내용은 참조 하세요. [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)</span><span class="sxs-lookup"><span data-stu-id="aff7e-126">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions)</span></span>
  
## <a name="overloading"></a><span data-ttu-id="aff7e-127">오버로딩</span><span class="sxs-lookup"><span data-stu-id="aff7e-127">Overloading</span></span>  
 <span data-ttu-id="aff7e-128">[또는 연산자](../../../visual-basic/language-reference/operators/or-operator.md) 하며 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 동작에 해당 클래스의 형식 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-128">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="aff7e-129">오버 로드는 `Or` 하 고 `IsTrue` 연산자의 동작에 영향을 줍니다는 `OrElse` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-129">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="aff7e-130">코드를 사용 하는 경우 `OrElse` 클래스 또는 구조체에 오버 로드에서 `Or` 및 `IsTrue`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-130">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="aff7e-131">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff7e-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff7e-132">예제</span><span class="sxs-lookup"><span data-stu-id="aff7e-132">Example</span></span>  
 <span data-ttu-id="aff7e-133">다음 예제에서는 `OrElse` 두 식에 논리 분리를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-133">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="aff7e-134">결과 `Boolean` 나타내는 두 식 중 하나가 true 인지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-134">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="aff7e-135">첫 번째 식이 `True`, 두 번째는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-135">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="aff7e-136">이전 예제의 결과는 `True`하십시오 `True`, 및 `False` 각각.</span><span class="sxs-lookup"><span data-stu-id="aff7e-136">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="aff7e-137">계산에서 `firstCheck`, 첫 번째는 이미 이므로는 두 번째 식은 계산 되지 않습니다 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-137">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="aff7e-138">그러나 두 번째 식 계산에서 계산 됩니다 `secondCheck`합니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-138">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff7e-139">예제</span><span class="sxs-lookup"><span data-stu-id="aff7e-139">Example</span></span>  
 <span data-ttu-id="aff7e-140">다음 예제는 `If`... `Then` 두 프로시저 호출을 포함 하는 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-140">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="aff7e-141">첫 번째 호출에서 반환 하는 경우 `True`, 두 번째 절차는 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-141">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="aff7e-142">두 번째 절차는 코드의이 섹션에서는 실행 될 때 항상 수행 해야 하는 중요 한 작업을 수행 하는 경우 예기치 않은 결과가 발생할 수 있습니다이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff7e-142">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="aff7e-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="aff7e-143">See also</span></span>

- [<span data-ttu-id="aff7e-144">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aff7e-144">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="aff7e-145">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="aff7e-145">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="aff7e-146">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="aff7e-146">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="aff7e-147">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="aff7e-147">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)
- [<span data-ttu-id="aff7e-148">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="aff7e-148">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="aff7e-149">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="aff7e-149">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
