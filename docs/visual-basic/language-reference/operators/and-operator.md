---
description: '다음에 대 한 자세한 정보: And 연산자 (Visual Basic)'
title: And 연산자
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
ms.openlocfilehash: 238ef0b2f14f2014da6e65684bfac183e03d963e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774280"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="91c3e-103">And 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91c3e-103">And Operator (Visual Basic)</span></span>

<span data-ttu-id="91c3e-104">두 식에 논리 결합을 수행 `Boolean` 하거나 두 숫자 식에 비트 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-104">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c3e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="91c3e-105">Syntax</span></span>  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="91c3e-106">부분</span><span class="sxs-lookup"><span data-stu-id="91c3e-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="91c3e-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="91c3e-107">Required.</span></span> <span data-ttu-id="91c3e-108">임의의 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-108">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="91c3e-109">부울 비교의 경우 `result` 는 두 값의 논리적 결합입니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="91c3e-109">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="91c3e-110">비트 연산의 경우 `result` 는 두 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-110">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="91c3e-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="91c3e-111">Required.</span></span> <span data-ttu-id="91c3e-112">임의의 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-112">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="91c3e-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="91c3e-113">Required.</span></span> <span data-ttu-id="91c3e-114">임의의 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-114">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91c3e-115">설명</span><span class="sxs-lookup"><span data-stu-id="91c3e-115">Remarks</span></span>  

 <span data-ttu-id="91c3e-116">부울 비교의 경우와 `result` 가 `True` 모두 `expression1` `expression2` 로 계산 되는 경우에만가입니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="91c3e-116">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="91c3e-117">다음 표에서는를 결정 하는 방법을 보여 줍니다 `result` .</span><span class="sxs-lookup"><span data-stu-id="91c3e-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="91c3e-118">`expression1`가 인 경우</span><span class="sxs-lookup"><span data-stu-id="91c3e-118">If `expression1` is</span></span>|<span data-ttu-id="91c3e-119">및 `expression2` 가</span><span class="sxs-lookup"><span data-stu-id="91c3e-119">And `expression2` is</span></span>|<span data-ttu-id="91c3e-120">의 값 `result` 이 인 경우</span><span class="sxs-lookup"><span data-stu-id="91c3e-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> <span data-ttu-id="91c3e-121">부울 비교에서 `And` 연산자는 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-121">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="91c3e-122">[AndAlso 연산자](andalso-operator.md) 는 *단락* 을 수행 합니다. 즉,가 이면 `expression1` 이 `False` `expression2` 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-122">The [AndAlso Operator](andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="91c3e-123">숫자 값에 적용 되는 `And` 연산자는 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 `result` 다음 표에 따라의 해당 비트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-123">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="91c3e-124">비트가 `expression1` 인 경우</span><span class="sxs-lookup"><span data-stu-id="91c3e-124">If bit in `expression1` is</span></span>|<span data-ttu-id="91c3e-125">그리고의 비트 `expression2` 는</span><span class="sxs-lookup"><span data-stu-id="91c3e-125">And bit in `expression2` is</span></span>|<span data-ttu-id="91c3e-126">`result`의 비트는</span><span class="sxs-lookup"><span data-stu-id="91c3e-126">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="91c3e-127">1</span><span class="sxs-lookup"><span data-stu-id="91c3e-127">1</span></span>|<span data-ttu-id="91c3e-128">1</span><span class="sxs-lookup"><span data-stu-id="91c3e-128">1</span></span>|<span data-ttu-id="91c3e-129">1</span><span class="sxs-lookup"><span data-stu-id="91c3e-129">1</span></span>|  
|<span data-ttu-id="91c3e-130">1</span><span class="sxs-lookup"><span data-stu-id="91c3e-130">1</span></span>|<span data-ttu-id="91c3e-131">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-131">0</span></span>|<span data-ttu-id="91c3e-132">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-132">0</span></span>|  
|<span data-ttu-id="91c3e-133">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-133">0</span></span>|<span data-ttu-id="91c3e-134">1</span><span class="sxs-lookup"><span data-stu-id="91c3e-134">1</span></span>|<span data-ttu-id="91c3e-135">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-135">0</span></span>|  
|<span data-ttu-id="91c3e-136">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-136">0</span></span>|<span data-ttu-id="91c3e-137">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-137">0</span></span>|<span data-ttu-id="91c3e-138">0</span><span class="sxs-lookup"><span data-stu-id="91c3e-138">0</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="91c3e-139">논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 결과를 얻으려면 모든 비트 연산을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-139">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="91c3e-140">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="91c3e-140">Data Types</span></span>  

 <span data-ttu-id="91c3e-141">피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic는 `Boolean` 식을 숫자 값으로 변환 하 고 (에 대해-1의 경우 `True` `False` ) 비트 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-141">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="91c3e-142">부울 비교의 경우 결과의 데이터 형식은 `Boolean` 입니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-142">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="91c3e-143">비트 비교의 경우 결과 데이터 형식은 및의 데이터 형식에 적합 한 숫자 형식입니다 `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="91c3e-143">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="91c3e-144">[연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="91c3e-144">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91c3e-145">`And`연산자를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-145">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="91c3e-146">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="91c3e-147">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91c3e-147">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c3e-148">예제</span><span class="sxs-lookup"><span data-stu-id="91c3e-148">Example</span></span>  

 <span data-ttu-id="91c3e-149">다음 예에서는 연산자를 사용 `And` 하 여 두 식에 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-149">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="91c3e-150">결과는 `Boolean` 두 식이 모두 인지 여부를 나타내는 값입니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="91c3e-150">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 <span data-ttu-id="91c3e-151">앞의 예제에서는 `True` 각각 및의 결과 `False` 를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-151">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c3e-152">예제</span><span class="sxs-lookup"><span data-stu-id="91c3e-152">Example</span></span>  

 <span data-ttu-id="91c3e-153">다음 예에서는 연산자를 사용 `And` 하 여 두 숫자 식의 개별 비트에 논리 결합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-153">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="91c3e-154">피연산자의 해당 비트가 둘 다 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-154">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 <span data-ttu-id="91c3e-155">앞의 예제에서는 각각 8, 2 및 0의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c3e-155">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c3e-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91c3e-156">See also</span></span>

- [<span data-ttu-id="91c3e-157">논리/비트 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91c3e-157">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="91c3e-158">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="91c3e-158">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="91c3e-159">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="91c3e-159">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="91c3e-160">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="91c3e-160">AndAlso Operator</span></span>](andalso-operator.md)
- [<span data-ttu-id="91c3e-161">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="91c3e-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
