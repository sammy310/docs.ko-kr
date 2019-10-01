---
title: 배타적 or 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: d82018a3018e2cf4362b9904ed127c20f56f6f0c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701279"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="7993e-102">배타적 or 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7993e-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="7993e-103">두 개의 `Boolean` 식에 논리 제외를 수행 하거나 두 숫자 식에 비트 제외를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7993e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7993e-104">Syntax</span></span>  
  
```vb  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7993e-105">요소</span><span class="sxs-lookup"><span data-stu-id="7993e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7993e-106">필수.</span><span class="sxs-lookup"><span data-stu-id="7993e-106">Required.</span></span> <span data-ttu-id="7993e-107">@No__t-0 또는 숫자 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="7993e-108">부울 비교의 경우 `result`은 두 `Boolean` 값의 논리적 제외 (배타적 논리적 분리)입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="7993e-109">비트 연산의 경우 `result`은 두 숫자 비트 패턴의 배타적 비트 논리합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="7993e-110">필수.</span><span class="sxs-lookup"><span data-stu-id="7993e-110">Required.</span></span> <span data-ttu-id="7993e-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7993e-112">필수.</span><span class="sxs-lookup"><span data-stu-id="7993e-112">Required.</span></span> <span data-ttu-id="7993e-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7993e-114">설명</span><span class="sxs-lookup"><span data-stu-id="7993e-114">Remarks</span></span>  
 <span data-ttu-id="7993e-115">부울 비교의 경우-0은 `expression1` 및 `expression2` 중 정확히 하나가 `True`로 계산 되는 경우에만-1 @no__t @no__t 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="7993e-116">즉, `expression1` 및 `expression2`이 반대 `Boolean` 값으로 계산 되는 경우에만입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="7993e-117">다음 표에서는 `result`이 결정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="7993e-118">경우 `expression1` 됩니다</span><span class="sxs-lookup"><span data-stu-id="7993e-118">If `expression1` is</span></span>|<span data-ttu-id="7993e-119">및 `expression2` 됩니다</span><span class="sxs-lookup"><span data-stu-id="7993e-119">And `expression2` is</span></span>|<span data-ttu-id="7993e-120">값 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="7993e-121">부울 비교에서 `Xor` 연산자는 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="7993e-122">결과는 항상 두 피연산자를 모두 기반으로 하기 때문에-0에 @no__t에 대 한 단락 대응 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="7993e-123">단락 *논리 연산자* 에 대 한 자세한 내용은 [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) 및 [OrElse operator](../../../visual-basic/language-reference/operators/orelse-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7993e-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="7993e-124">비트 연산의 경우 `Xor` 연산자는 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 다음 표에 따라 `result`의 해당 비트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="7993e-125">@No__t 비트의 경우-0은입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-125">If bit in `expression1` is</span></span>|<span data-ttu-id="7993e-126">및 비트 `expression2`은입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-126">And bit in `expression2` is</span></span>|<span data-ttu-id="7993e-127">비트 `result`은입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="7993e-128">1</span><span class="sxs-lookup"><span data-stu-id="7993e-128">1</span></span>|<span data-ttu-id="7993e-129">1</span><span class="sxs-lookup"><span data-stu-id="7993e-129">1</span></span>|<span data-ttu-id="7993e-130">0</span><span class="sxs-lookup"><span data-stu-id="7993e-130">0</span></span>|  
|<span data-ttu-id="7993e-131">1</span><span class="sxs-lookup"><span data-stu-id="7993e-131">1</span></span>|<span data-ttu-id="7993e-132">0</span><span class="sxs-lookup"><span data-stu-id="7993e-132">0</span></span>|<span data-ttu-id="7993e-133">1</span><span class="sxs-lookup"><span data-stu-id="7993e-133">1</span></span>|  
|<span data-ttu-id="7993e-134">0</span><span class="sxs-lookup"><span data-stu-id="7993e-134">0</span></span>|<span data-ttu-id="7993e-135">1</span><span class="sxs-lookup"><span data-stu-id="7993e-135">1</span></span>|<span data-ttu-id="7993e-136">1</span><span class="sxs-lookup"><span data-stu-id="7993e-136">1</span></span>|  
|<span data-ttu-id="7993e-137">0</span><span class="sxs-lookup"><span data-stu-id="7993e-137">0</span></span>|<span data-ttu-id="7993e-138">0</span><span class="sxs-lookup"><span data-stu-id="7993e-138">0</span></span>|<span data-ttu-id="7993e-139">0</span><span class="sxs-lookup"><span data-stu-id="7993e-139">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7993e-140">논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 실행을 위해 모든 비트 연산을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="7993e-141">예를 들어 5 `Xor` 3은 6입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="7993e-142">이러한 이유를 확인 하려면 5와 3을 이진 표현 101 및 011로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="7993e-143">그런 다음 위의 표를 사용 하 여 101 Xor 011이 110 인지 확인 합니다 .이 값은 10 진수 6의 이진 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="7993e-144">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7993e-144">Data Types</span></span>  
 <span data-ttu-id="7993e-145">피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic `Boolean` 식을 숫자 값으로 변환 하 고 (@no__t-@no__t 2의 경우-1) 비트 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="7993e-146">@No__t-0 비교의 경우 결과의 데이터 형식은-1 @no__t 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="7993e-147">비트 비교의 경우 결과 데이터 형식은 `expression1` 및 `expression2`의 데이터 형식에 적합 한 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="7993e-148">[연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7993e-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7993e-149">오버로딩</span><span class="sxs-lookup"><span data-stu-id="7993e-149">Overloading</span></span>  
 <span data-ttu-id="7993e-150">연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `Xor`</span><span class="sxs-lookup"><span data-stu-id="7993e-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7993e-151">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="7993e-152">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7993e-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7993e-153">예제</span><span class="sxs-lookup"><span data-stu-id="7993e-153">Example</span></span>  
 <span data-ttu-id="7993e-154">다음 예에서는 `Xor` 연산자를 사용 하 여 두 식에서 논리적 제외 (배타적 논리 분리)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="7993e-155">결과는 정확히 한 식의 하나 `True` 인지 여부를 나타내는 0 @no__t 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 <span data-ttu-id="7993e-156">이전 예제에서는 `False`, `True` 및 `False`의 결과를 각각 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7993e-157">예제</span><span class="sxs-lookup"><span data-stu-id="7993e-157">Example</span></span>  
 <span data-ttu-id="7993e-158">다음 예에서는 `Xor` 연산자를 사용 하 여 두 숫자 식의 개별 비트에서 논리적 제외 (배타적 논리 분리)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="7993e-159">피연산자의 해당 비트 중 정확히 하나가 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 <span data-ttu-id="7993e-160">이전 예제에서는 각각 2, 12 및 14의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7993e-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7993e-161">참조</span><span class="sxs-lookup"><span data-stu-id="7993e-161">See also</span></span>

- [<span data-ttu-id="7993e-162">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7993e-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="7993e-163">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="7993e-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7993e-164">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="7993e-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7993e-165">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="7993e-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
