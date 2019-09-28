---
title: And 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: bd6ebbf5f53a7cf187b5d8ce7630080d44d46df2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591624"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="26ae6-102">And 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26ae6-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="26ae6-103">두 개의 `Boolean` 식에 논리 결합을 수행 하거나 두 숫자 식에 비트 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ae6-104">구문</span><span class="sxs-lookup"><span data-stu-id="26ae6-104">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="26ae6-105">요소</span><span class="sxs-lookup"><span data-stu-id="26ae6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="26ae6-106">필수.</span><span class="sxs-lookup"><span data-stu-id="26ae6-106">Required.</span></span> <span data-ttu-id="26ae6-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="26ae6-108">부울 비교의 경우 `result`은 두 `Boolean` 값의 논리적 결합입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="26ae6-109">비트 연산의 경우 `result`은 두 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="26ae6-110">필수.</span><span class="sxs-lookup"><span data-stu-id="26ae6-110">Required.</span></span> <span data-ttu-id="26ae6-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="26ae6-112">필수.</span><span class="sxs-lookup"><span data-stu-id="26ae6-112">Required.</span></span> <span data-ttu-id="26ae6-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26ae6-114">설명</span><span class="sxs-lookup"><span data-stu-id="26ae6-114">Remarks</span></span>  
 <span data-ttu-id="26ae6-115">부울 비교의 경우 `result`은 `expression1`와 `expression2`이 모두 `True`로 계산 되는 경우에만 `True`입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="26ae6-116">다음 표에서는 `result`이 결정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="26ae6-117">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="26ae6-117">If `expression1` is</span></span>|<span data-ttu-id="26ae6-118">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="26ae6-118">And `expression2` is</span></span>|<span data-ttu-id="26ae6-119">값 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="26ae6-120">부울 비교에서 `And` 연산자는 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="26ae6-121">[AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 는 *단락*을 수행 합니다. 즉,-2가-3 @no__t 되 @no__t 면 `expression2`이 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="26ae6-122">@No__t-0 연산자는 숫자 값에 적용 될 때 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 다음 표에 따라 `result`의 해당 비트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="26ae6-123">@No__t 비트의 경우-0은입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-123">If bit in `expression1` is</span></span>|<span data-ttu-id="26ae6-124">및 비트 `expression2`은입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-124">And bit in `expression2` is</span></span>|<span data-ttu-id="26ae6-125">비트 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="26ae6-126">1</span><span class="sxs-lookup"><span data-stu-id="26ae6-126">1</span></span>|<span data-ttu-id="26ae6-127">1</span><span class="sxs-lookup"><span data-stu-id="26ae6-127">1</span></span>|<span data-ttu-id="26ae6-128">1</span><span class="sxs-lookup"><span data-stu-id="26ae6-128">1</span></span>|  
|<span data-ttu-id="26ae6-129">1</span><span class="sxs-lookup"><span data-stu-id="26ae6-129">1</span></span>|<span data-ttu-id="26ae6-130">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-130">0</span></span>|<span data-ttu-id="26ae6-131">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-131">0</span></span>|  
|<span data-ttu-id="26ae6-132">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-132">0</span></span>|<span data-ttu-id="26ae6-133">1</span><span class="sxs-lookup"><span data-stu-id="26ae6-133">1</span></span>|<span data-ttu-id="26ae6-134">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-134">0</span></span>|  
|<span data-ttu-id="26ae6-135">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-135">0</span></span>|<span data-ttu-id="26ae6-136">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-136">0</span></span>|<span data-ttu-id="26ae6-137">0</span><span class="sxs-lookup"><span data-stu-id="26ae6-137">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="26ae6-138">논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 결과를 얻으려면 모든 비트 연산을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="26ae6-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="26ae6-139">Data Types</span></span>  
 <span data-ttu-id="26ae6-140">피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic `Boolean` 식을 숫자 값으로 변환 하 고 (@no__t-@no__t 2의 경우-1) 비트 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="26ae6-141">부울 비교의 경우 결과의 데이터 형식은 `Boolean`입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="26ae6-142">비트 비교의 경우 결과 데이터 형식은 `expression1` 및 `expression2`의 데이터 형식에 적합 한 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="26ae6-143">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26ae6-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26ae6-144">연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `And`</span><span class="sxs-lookup"><span data-stu-id="26ae6-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="26ae6-145">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="26ae6-146">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26ae6-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26ae6-147">예제</span><span class="sxs-lookup"><span data-stu-id="26ae6-147">Example</span></span>  
 <span data-ttu-id="26ae6-148">다음 예에서는 `And` 연산자를 사용 하 여 두 식에 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="26ae6-149">결과는 두 식이 `True` 인지 여부를 나타내는 0 @no__t 값입니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="26ae6-150">앞의 예제에서는 각각 `True` 및 `False`의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26ae6-151">예제</span><span class="sxs-lookup"><span data-stu-id="26ae6-151">Example</span></span>  
 <span data-ttu-id="26ae6-152">다음 예에서는 `And` 연산자를 사용 하 여 두 숫자 식의 개별 비트에 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="26ae6-153">피연산자의 해당 비트가 둘 다 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="26ae6-154">앞의 예제에서는 각각 8, 2 및 0의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ae6-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ae6-155">참조</span><span class="sxs-lookup"><span data-stu-id="26ae6-155">See also</span></span>

- [<span data-ttu-id="26ae6-156">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26ae6-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="26ae6-157">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="26ae6-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="26ae6-158">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="26ae6-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="26ae6-159">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="26ae6-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [<span data-ttu-id="26ae6-160">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="26ae6-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
