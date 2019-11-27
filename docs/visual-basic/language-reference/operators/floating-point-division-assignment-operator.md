---
title: /= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331042"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e26e1-102">/= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e26e1-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="e26e1-103">변수 또는 속성의 값을 식의 값으로 나누고 부동 소수점 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="e26e1-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="e26e1-105">요소</span><span class="sxs-lookup"><span data-stu-id="e26e1-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e26e1-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-106">Required.</span></span> <span data-ttu-id="e26e1-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="e26e1-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-108">Required.</span></span> <span data-ttu-id="e26e1-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e26e1-110">주의</span><span class="sxs-lookup"><span data-stu-id="e26e1-110">Remarks</span></span>  
 <span data-ttu-id="e26e1-111">`/=` 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e26e1-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="e26e1-113">`/=` 연산자는 먼저 연산자의 왼쪽에 있는 변수나 속성의 값을 연산자의 오른쪽에 있는 식의 값을 기준으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="e26e1-114">그런 다음 연산자는 해당 작업의 부동 소수점 결과를 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="e26e1-115">이 문은 왼쪽의 변수 또는 속성에 `Double` 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="e26e1-116">`Option Strict` `On`경우 `variableorproperty` `Double`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="e26e1-117">`Option Strict` `Off`경우 Visual Basic 암시적 변환을 수행 하 고 결과 값을 `variableorproperty`에 할당 합니다 .이 경우 런타임에 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="e26e1-118">자세한 내용은 [확대/축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e26e1-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e26e1-119">오버로드</span><span class="sxs-lookup"><span data-stu-id="e26e1-119">Overloading</span></span>  
 <span data-ttu-id="e26e1-120">[/연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e26e1-121">`/` 연산자를 오버 로드 하면 `/=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="e26e1-122">코드에서 `/`오버 로드 하는 클래스 또는 구조체에 `/=`를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e26e1-123">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e26e1-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e26e1-124">예제</span><span class="sxs-lookup"><span data-stu-id="e26e1-124">Example</span></span>  
 <span data-ttu-id="e26e1-125">다음 예에서는 `/=` 연산자를 사용 하 여 하나의 `Integer` 변수를 초당 나누고 몫을 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26e1-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e26e1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e26e1-126">See also</span></span>

- [<span data-ttu-id="e26e1-127">/연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e26e1-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="e26e1-128">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="e26e1-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="e26e1-129">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="e26e1-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="e26e1-130">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="e26e1-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="e26e1-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="e26e1-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e26e1-132">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="e26e1-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e26e1-133">문</span><span class="sxs-lookup"><span data-stu-id="e26e1-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
