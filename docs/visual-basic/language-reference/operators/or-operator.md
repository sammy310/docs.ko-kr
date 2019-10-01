---
title: Or 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701229"
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="49ea6-102">Or 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ea6-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="49ea6-103">두 개의 `Boolean` 식에 논리 분리를 수행 하거나 두 숫자 식에 비트 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ea6-104">구문</span><span class="sxs-lookup"><span data-stu-id="49ea6-104">Syntax</span></span>  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="49ea6-105">요소</span><span class="sxs-lookup"><span data-stu-id="49ea6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="49ea6-106">필수.</span><span class="sxs-lookup"><span data-stu-id="49ea6-106">Required.</span></span> <span data-ttu-id="49ea6-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="49ea6-108">@No__t 0 비교의 경우-1 @no__t 두 @no__t 값의 포함 논리 분리입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="49ea6-109">비트 연산의 경우 `result`은 두 숫자 비트 패턴의 포함 비트 논리합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="49ea6-110">필수.</span><span class="sxs-lookup"><span data-stu-id="49ea6-110">Required.</span></span> <span data-ttu-id="49ea6-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="49ea6-112">필수.</span><span class="sxs-lookup"><span data-stu-id="49ea6-112">Required.</span></span> <span data-ttu-id="49ea6-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49ea6-114">설명</span><span class="sxs-lookup"><span data-stu-id="49ea6-114">Remarks</span></span>  
 <span data-ttu-id="49ea6-115">@No__t-0을 비교 하는 경우 `expression1`과 `expression2`가 모두 `False` 인 경우에만-1 @no__t `False`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="49ea6-116">다음 표에서는 `result`이 결정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="49ea6-117">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="49ea6-117">If `expression1` is</span></span>|<span data-ttu-id="49ea6-118">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="49ea6-118">And `expression2` is</span></span>|<span data-ttu-id="49ea6-119">값 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="49ea6-120">@No__t-0 비교에서 `Or` 연산자는 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="49ea6-121">[OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md) 는 *단락*을 수행 합니다. 즉, `expression1`가 `True` 이면 `expression2`가 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="49ea6-122">비트 연산의 경우 `Or` 연산자는 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 다음 표에 따라 `result`의 해당 비트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="49ea6-123">@No__t 비트의 경우-0은입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-123">If bit in `expression1` is</span></span>|<span data-ttu-id="49ea6-124">및 비트 `expression2`은입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-124">And bit in `expression2` is</span></span>|<span data-ttu-id="49ea6-125">비트 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="49ea6-126">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-126">1</span></span>|<span data-ttu-id="49ea6-127">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-127">1</span></span>|<span data-ttu-id="49ea6-128">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-128">1</span></span>|  
|<span data-ttu-id="49ea6-129">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-129">1</span></span>|<span data-ttu-id="49ea6-130">0</span><span class="sxs-lookup"><span data-stu-id="49ea6-130">0</span></span>|<span data-ttu-id="49ea6-131">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-131">1</span></span>|  
|<span data-ttu-id="49ea6-132">0</span><span class="sxs-lookup"><span data-stu-id="49ea6-132">0</span></span>|<span data-ttu-id="49ea6-133">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-133">1</span></span>|<span data-ttu-id="49ea6-134">1</span><span class="sxs-lookup"><span data-stu-id="49ea6-134">1</span></span>|  
|<span data-ttu-id="49ea6-135">0</span><span class="sxs-lookup"><span data-stu-id="49ea6-135">0</span></span>|<span data-ttu-id="49ea6-136">0</span><span class="sxs-lookup"><span data-stu-id="49ea6-136">0</span></span>|<span data-ttu-id="49ea6-137">0</span><span class="sxs-lookup"><span data-stu-id="49ea6-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="49ea6-138">논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 실행을 위해 모든 비트 연산을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="49ea6-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="49ea6-139">Data Types</span></span>  
 <span data-ttu-id="49ea6-140">피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic `Boolean` 식을 숫자 값으로 변환 하 고 (@no__t-@no__t 2의 경우-1) 비트 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="49ea6-141">@No__t-0 비교의 경우 결과의 데이터 형식은-1 @no__t 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="49ea6-142">비트 비교의 경우 결과 데이터 형식은 `expression1` 및 `expression2`의 데이터 형식에 적합 한 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="49ea6-143">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49ea6-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="49ea6-144">오버로딩</span><span class="sxs-lookup"><span data-stu-id="49ea6-144">Overloading</span></span>  
 <span data-ttu-id="49ea6-145">연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `Or`</span><span class="sxs-lookup"><span data-stu-id="49ea6-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="49ea6-146">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="49ea6-147">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49ea6-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ea6-148">예제</span><span class="sxs-lookup"><span data-stu-id="49ea6-148">Example</span></span>  
 <span data-ttu-id="49ea6-149">다음 예에서는 `Or` 연산자를 사용 하 여 두 식에 대 한 포함 논리 분리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="49ea6-150">결과는 두 식 중 하나 `True` 인지 여부를 나타내는 0 @no__t 값입니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 <span data-ttu-id="49ea6-151">앞의 예제에서는 `True`, `True` 및 `False`의 결과를 각각 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ea6-152">예제</span><span class="sxs-lookup"><span data-stu-id="49ea6-152">Example</span></span>  
 <span data-ttu-id="49ea6-153">다음 예에서는 `Or` 연산자를 사용 하 여 두 숫자 식의 개별 비트에 대 한 포괄적 논리합 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="49ea6-154">피연산자의 해당 비트 중 하나가 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 <span data-ttu-id="49ea6-155">앞의 예제에서는 각각 10, 14 및 14의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="49ea6-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ea6-156">참조</span><span class="sxs-lookup"><span data-stu-id="49ea6-156">See also</span></span>

- [<span data-ttu-id="49ea6-157">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ea6-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="49ea6-158">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="49ea6-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="49ea6-159">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="49ea6-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="49ea6-160">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="49ea6-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [<span data-ttu-id="49ea6-161">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="49ea6-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
