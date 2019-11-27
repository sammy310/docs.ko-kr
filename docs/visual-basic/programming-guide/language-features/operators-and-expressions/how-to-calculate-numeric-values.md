---
title: '방법: 숫자 값 계산'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: d213f6b5a4abf8c52d8872ae36e89796183ff27c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348963"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="dd8f2-102">방법: 숫자 값 계산(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd8f2-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="dd8f2-103">숫자 식을 사용 하 여 숫자 값을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="dd8f2-104">*숫자 식은* 숫자 값을 나타내는 리터럴, 상수 및 변수와 해당 값에 대해 작동 하는 연산자를 포함 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="dd8f2-105">숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="dd8f2-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="dd8f2-106">숫자 값을 계산 하려면</span><span class="sxs-lookup"><span data-stu-id="dd8f2-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="dd8f2-107">하나 이상의 숫자 리터럴, 상수 및 변수를 숫자 식으로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="dd8f2-108">다음 예에서는 몇 가지 유효한 숫자 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="dd8f2-109">처음 세 줄은 리터럴, 상수 및 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="dd8f2-110">각 항목은 유효한 숫자 식 자체를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="dd8f2-111">마지막 줄은 두 개의 리터럴이 있는 변수의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="dd8f2-112">숫자 식 만으로는 완전 한 Visual Basic 문을 형성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="dd8f2-113">전체 문의 일부로 식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="dd8f2-114">숫자 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="dd8f2-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="dd8f2-115">다음 예제가 보여 주는 것 처럼 대입문을 사용 하 여 숫자 식으로 표시 된 값을 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="dd8f2-116">위의 예에서는 같음 연산자 (`=`)의 오른쪽에 있는 식의 값이 연산자의 좌 변에 있는 `j` 변수에 할당 되므로 `j` 276로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="dd8f2-117">자세한 내용은 [문](../../../../visual-basic/language-reference/statements/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="dd8f2-118">여러 연산자</span><span class="sxs-lookup"><span data-stu-id="dd8f2-118">Multiple Operators</span></span>  
 <span data-ttu-id="dd8f2-119">숫자 식에 여러 개의 연산자가 포함 된 경우 계산 되는 순서는 연산자 우선 순위 규칙에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="dd8f2-120">연산자 우선 순위 규칙을 재정의 하려면 위 예제와 같이 식을 괄호로 묶습니다. 괄호로 묶인 식이 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="dd8f2-121">일반적인 연산자 우선 순위를 재정의 하려면</span><span class="sxs-lookup"><span data-stu-id="dd8f2-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="dd8f2-122">괄호를 사용 하 여 먼저 수행 하려는 작업을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="dd8f2-123">다음 예에서는 동일한 피연산자와 연산자를 사용 하는 두 개의 다른 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="dd8f2-124">앞의 예제에서 `j`에 대 한 계산은 `(67 + i)`의 괄호가 보통 우선 순위를 재정의 하 고 `j`에 할당 된 값이 276 (4 배 69) 이므로 더하기 연산자 (`+`)를 먼저 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="dd8f2-125">`k` 계산은 일반적인 우선 순위 (`+`이전`*`)에서 연산자를 수행 하 고 `k`에 할당 되는 값은 270 (268 plus 2)입니다.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="dd8f2-126">자세한 내용은 [Visual Basic 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd8f2-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd8f2-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd8f2-127">See also</span></span>

- [<span data-ttu-id="dd8f2-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="dd8f2-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="dd8f2-129">값 비교</span><span class="sxs-lookup"><span data-stu-id="dd8f2-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="dd8f2-130">문</span><span class="sxs-lookup"><span data-stu-id="dd8f2-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="dd8f2-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="dd8f2-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="dd8f2-132">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="dd8f2-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="dd8f2-133">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="dd8f2-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
