---
title: Not 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 29e2b159e4c6261a62e788b537102b9b457fe0c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955826"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="d5c8c-102">Not 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5c8c-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="d5c8c-103">`Boolean` 식에 논리 부정을 수행 하거나 숫자 식에 비트 부정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5c8c-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d5c8c-105">요소</span><span class="sxs-lookup"><span data-stu-id="d5c8c-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d5c8c-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-106">Required.</span></span> <span data-ttu-id="d5c8c-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="d5c8c-108">필수.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-108">Required.</span></span> <span data-ttu-id="d5c8c-109">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5c8c-110">설명</span><span class="sxs-lookup"><span data-stu-id="d5c8c-110">Remarks</span></span>  
 <span data-ttu-id="d5c8c-111">다음 `Boolean` 표에서는 식의 경우를 결정 `result` 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="d5c8c-112">경우 `expression` 됩니다</span><span class="sxs-lookup"><span data-stu-id="d5c8c-112">If `expression` is</span></span>|<span data-ttu-id="d5c8c-113">의 `result` 값이 인 경우</span><span class="sxs-lookup"><span data-stu-id="d5c8c-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="d5c8c-114">숫자 식의 경우 연산자 `Not` 는 숫자 식의 비트 값을 반전 하 고 다음 표에 따라의 `result` 해당 비트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="d5c8c-115">비트가 `expression` 인 경우</span><span class="sxs-lookup"><span data-stu-id="d5c8c-115">If bit in `expression` is</span></span>|<span data-ttu-id="d5c8c-116">의 `result` 비트는</span><span class="sxs-lookup"><span data-stu-id="d5c8c-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="d5c8c-117">1</span><span class="sxs-lookup"><span data-stu-id="d5c8c-117">1</span></span>|<span data-ttu-id="d5c8c-118">0</span><span class="sxs-lookup"><span data-stu-id="d5c8c-118">0</span></span>|  
|<span data-ttu-id="d5c8c-119">0</span><span class="sxs-lookup"><span data-stu-id="d5c8c-119">0</span></span>|<span data-ttu-id="d5c8c-120">1</span><span class="sxs-lookup"><span data-stu-id="d5c8c-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d5c8c-121">논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 실행을 위해 모든 비트 연산을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="d5c8c-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d5c8c-122">Data Types</span></span>  
 <span data-ttu-id="d5c8c-123">부울 부정의 경우 결과 `Boolean`의 데이터 형식은입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="d5c8c-124">비트 부정의 경우 결과 데이터 형식은의 `expression`경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="d5c8c-125">그러나 expression이 `Decimal`이면 `Long`결과는입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d5c8c-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="d5c8c-126">Overloading</span></span>  
 <span data-ttu-id="d5c8c-127">연산자를 오버 로드할 수 있습니다. 즉, 해당 피연산자의 형식이 해당 클래스 또는 구조체의 형식인 경우 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. `Not`</span><span class="sxs-lookup"><span data-stu-id="d5c8c-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="d5c8c-128">코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d5c8c-129">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c8c-130">예제</span><span class="sxs-lookup"><span data-stu-id="d5c8c-130">Example</span></span>  
 <span data-ttu-id="d5c8c-131">다음 예에서는 `Not` 연산자를 사용 하 여 `Boolean` 식에 논리 부정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="d5c8c-132">결과는 식의 `Boolean` 값을 반대로 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="d5c8c-133">앞의 예제에서는 각각 및 `False` `True`의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c8c-134">예제</span><span class="sxs-lookup"><span data-stu-id="d5c8c-134">Example</span></span>  
 <span data-ttu-id="d5c8c-135">다음 예에서는 `Not` 연산자를 사용 하 여 숫자 식의 개별 비트에 대 한 논리 부정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="d5c8c-136">결과 패턴의 비트는 부호 비트를 포함 하 여 피연산자 패턴에서 해당 비트의 역방향으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="d5c8c-137">앞의 예제에서는 – 11, – 9 및 – 7의 결과를 각각 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c8c-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c8c-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5c8c-138">See also</span></span>

- [<span data-ttu-id="d5c8c-139">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5c8c-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d5c8c-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="d5c8c-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d5c8c-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="d5c8c-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d5c8c-142">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="d5c8c-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
