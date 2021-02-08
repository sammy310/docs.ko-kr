---
description: '자세한 정보: OrElse 연산자 (Visual Basic)'
title: OrElse 연산자
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
ms.openlocfilehash: 48ccbda1e0cb4f655b28e902b22fbfe0c3e66ac8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795328"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="8ea54-103">OrElse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ea54-103">OrElse Operator (Visual Basic)</span></span>

<span data-ttu-id="8ea54-104">두 식에 순환이 짧은 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-104">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ea54-105">Syntax</span></span>  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="8ea54-106">부분</span><span class="sxs-lookup"><span data-stu-id="8ea54-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="8ea54-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8ea54-107">Required.</span></span> <span data-ttu-id="8ea54-108">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-108">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="8ea54-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8ea54-109">Required.</span></span> <span data-ttu-id="8ea54-110">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-110">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="8ea54-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8ea54-111">Required.</span></span> <span data-ttu-id="8ea54-112">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-112">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ea54-113">설명</span><span class="sxs-lookup"><span data-stu-id="8ea54-113">Remarks</span></span>  

 <span data-ttu-id="8ea54-114">컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 무시할 수 있는 경우 논리 연산을 *단락* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-114">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="8ea54-115">계산 된 첫 번째 식의 결과가 작업의 최종 결과를 결정 하는 경우 최종 결과를 변경할 수 없기 때문에 두 번째 식을 계산할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-115">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="8ea54-116">생략 된 식이 복잡 하거나 프로시저 호출이 포함 된 경우 단락을 통해 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-116">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="8ea54-117">두 식이 모두로 계산 되 면 `True` `result` 는 `True` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-117">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="8ea54-118">다음 표에서는를 결정 하는 방법을 보여 줍니다 `result` .</span><span class="sxs-lookup"><span data-stu-id="8ea54-118">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8ea54-119">`expression1`가 인 경우</span><span class="sxs-lookup"><span data-stu-id="8ea54-119">If `expression1` is</span></span>|<span data-ttu-id="8ea54-120">및 `expression2` 가</span><span class="sxs-lookup"><span data-stu-id="8ea54-120">And `expression2` is</span></span>|<span data-ttu-id="8ea54-121">의 값 `result` 이 인 경우</span><span class="sxs-lookup"><span data-stu-id="8ea54-121">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="8ea54-122">(평가 안 함)</span><span class="sxs-lookup"><span data-stu-id="8ea54-122">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="8ea54-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8ea54-123">Data Types</span></span>  

 <span data-ttu-id="8ea54-124">`OrElse`연산자는 [Boolean 데이터 형식](../data-types/boolean-data-type.md)에 대해서만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-124">The `OrElse` operator is defined only for the [Boolean Data Type](../data-types/boolean-data-type.md).</span></span> <span data-ttu-id="8ea54-125">Visual Basic `Boolean` 는 식을 계산 하기 전에 필요에 따라 각 피연산자를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-125">Visual Basic converts each operand as necessary to `Boolean` before evaluating the expression.</span></span> <span data-ttu-id="8ea54-126">결과를 숫자 형식에 할당 하는 경우 Visual Basic은 해당 `Boolean` 형식으로 변환 하 고가 됩니다 `False` `0` `True` `-1` .</span><span class="sxs-lookup"><span data-stu-id="8ea54-126">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type such that `False` becomes `0` and `True` becomes `-1`.</span></span>
<span data-ttu-id="8ea54-127">자세한 내용은 [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ea54-127">For more information, see [Boolean Type Conversions](../data-types/boolean-data-type.md#type-conversions).</span></span>
  
## <a name="overloading"></a><span data-ttu-id="8ea54-128">오버로딩</span><span class="sxs-lookup"><span data-stu-id="8ea54-128">Overloading</span></span>  

 <span data-ttu-id="8ea54-129">[Or 연산자](or-operator.md) 와 [IsTrue 연산자](istrue-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-129">The [Or Operator](or-operator.md) and the [IsTrue Operator](istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8ea54-130">및 연산자를 오버 로드 하면 `Or` `IsTrue` 연산자의 동작에 영향을 줍니다 `OrElse` .</span><span class="sxs-lookup"><span data-stu-id="8ea54-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="8ea54-131">`OrElse`및를 오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 `Or` 다시 `IsTrue` 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="8ea54-132">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ea54-132">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea54-133">예제</span><span class="sxs-lookup"><span data-stu-id="8ea54-133">Example</span></span>  

 <span data-ttu-id="8ea54-134">다음 예에서는 연산자를 사용 `OrElse` 하 여 두 식에 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="8ea54-135">결과는 `Boolean` 두 식 중 하나가 true 인지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="8ea54-136">첫 번째 식이 인 경우 `True` 두 번째 식이 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 <span data-ttu-id="8ea54-137">앞의 예제에서는 `True` 각각, 및의 결과를 생성 `True` `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="8ea54-138">를 계산할 때 `firstCheck` 첫 번째 식은 이미 이므로 두 번째 식은 계산 되지 않습니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="8ea54-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="8ea54-139">그러나 두 번째 식은 계산에서 계산 됩니다 `secondCheck` .</span><span class="sxs-lookup"><span data-stu-id="8ea54-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ea54-140">예제</span><span class="sxs-lookup"><span data-stu-id="8ea54-140">Example</span></span>  

 <span data-ttu-id="8ea54-141">다음 예에서는 `If` `Then` 두 개의 프로시저 호출을 포함 하는 ... 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="8ea54-142">첫 번째 호출에서을 반환 하는 경우 `True` 두 번째 프로시저가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="8ea54-143">이 경우 코드의이 섹션이 실행 될 때 항상 수행 해야 하는 중요 한 작업을 두 번째 절차에서 수행할 경우 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea54-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="8ea54-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ea54-144">See also</span></span>

- [<span data-ttu-id="8ea54-145">논리/비트 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ea54-145">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="8ea54-146">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="8ea54-146">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8ea54-147">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="8ea54-147">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="8ea54-148">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="8ea54-148">Or Operator</span></span>](or-operator.md)
- [<span data-ttu-id="8ea54-149">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="8ea54-149">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="8ea54-150">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="8ea54-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
