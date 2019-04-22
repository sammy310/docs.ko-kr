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
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824215"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="52fc1-102">Not 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52fc1-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="52fc1-103">논리 부정 연산을 수행 하는 `Boolean` 식 또는 숫자 식에 비트 부정을 합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52fc1-104">구문</span><span class="sxs-lookup"><span data-stu-id="52fc1-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="52fc1-105">요소</span><span class="sxs-lookup"><span data-stu-id="52fc1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="52fc1-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="52fc1-106">Required.</span></span> <span data-ttu-id="52fc1-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="52fc1-108">필수.</span><span class="sxs-lookup"><span data-stu-id="52fc1-108">Required.</span></span> <span data-ttu-id="52fc1-109">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52fc1-110">설명</span><span class="sxs-lookup"><span data-stu-id="52fc1-110">Remarks</span></span>  
 <span data-ttu-id="52fc1-111">에 대 한 `Boolean` 식에 다음 표에서 설명 하는 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="52fc1-112">경우 `expression` 됩니다</span><span class="sxs-lookup"><span data-stu-id="52fc1-112">If `expression` is</span></span>|<span data-ttu-id="52fc1-113">변수의 `result` 는</span><span class="sxs-lookup"><span data-stu-id="52fc1-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="52fc1-114">숫자 식에 대 한 합니다 `Not` 연산자는 숫자 식의 비트 값을 반전 하 고의 해당 비트를 설정 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="52fc1-115">경우에 비트 `expression` 됩니다</span><span class="sxs-lookup"><span data-stu-id="52fc1-115">If bit in `expression` is</span></span>|<span data-ttu-id="52fc1-116">비트 `result` 됩니다</span><span class="sxs-lookup"><span data-stu-id="52fc1-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="52fc1-117">1</span><span class="sxs-lookup"><span data-stu-id="52fc1-117">1</span></span>|<span data-ttu-id="52fc1-118">0</span><span class="sxs-lookup"><span data-stu-id="52fc1-118">0</span></span>|  
|<span data-ttu-id="52fc1-119">0</span><span class="sxs-lookup"><span data-stu-id="52fc1-119">0</span></span>|<span data-ttu-id="52fc1-120">1</span><span class="sxs-lookup"><span data-stu-id="52fc1-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="52fc1-121">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="52fc1-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="52fc1-122">Data Types</span></span>  
 <span data-ttu-id="52fc1-123">데이터 형식의 결과 부울 부정, `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="52fc1-124">비트 부정 결과 데이터 형식이 동일와 `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="52fc1-125">그러나 식이 `Decimal`, 결과 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="52fc1-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="52fc1-126">Overloading</span></span>  
 <span data-ttu-id="52fc1-127">합니다 `Not` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="52fc1-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="52fc1-128">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="52fc1-129">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52fc1-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52fc1-130">예제</span><span class="sxs-lookup"><span data-stu-id="52fc1-130">Example</span></span>  
 <span data-ttu-id="52fc1-131">다음 예제에서는 합니다 `Not` 의 논리 부정 연산을 수행 하는 연산자는 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="52fc1-132">결과 `Boolean` 역순으로 식의 값을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="52fc1-133">앞의 예제 결과 생성 `False` 고 `True`, 각각.</span><span class="sxs-lookup"><span data-stu-id="52fc1-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52fc1-134">예제</span><span class="sxs-lookup"><span data-stu-id="52fc1-134">Example</span></span>  
 <span data-ttu-id="52fc1-135">다음 예제에서는 `Not` 연산자는 숫자 식의 개별 비트 논리 부정 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="52fc1-136">결과 패턴의 비트가 부호 비트를 포함 하 여 피연산자 패턴에 해당 비트의 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="52fc1-137">앞의 예제는 각각 – 11 고 –9,-7, 결과 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="52fc1-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fc1-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="52fc1-138">See also</span></span>

- [<span data-ttu-id="52fc1-139">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52fc1-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="52fc1-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="52fc1-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="52fc1-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="52fc1-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="52fc1-142">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="52fc1-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
