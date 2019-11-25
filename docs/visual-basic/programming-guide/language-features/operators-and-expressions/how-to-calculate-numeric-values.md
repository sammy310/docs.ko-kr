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
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="13f6b-102">방법: 숫자 값 계산(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13f6b-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="13f6b-103">You can calculate numeric values through the use of numeric expressions.</span><span class="sxs-lookup"><span data-stu-id="13f6b-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="13f6b-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span><span class="sxs-lookup"><span data-stu-id="13f6b-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="13f6b-105">Calculating Numeric Values</span><span class="sxs-lookup"><span data-stu-id="13f6b-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="13f6b-106">To calculate a numeric value</span><span class="sxs-lookup"><span data-stu-id="13f6b-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="13f6b-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span><span class="sxs-lookup"><span data-stu-id="13f6b-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="13f6b-108">The following example shows some valid numeric expressions.</span><span class="sxs-lookup"><span data-stu-id="13f6b-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="13f6b-109">The first three lines show a literal, a constant, and a variable.</span><span class="sxs-lookup"><span data-stu-id="13f6b-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="13f6b-110">Each one forms a valid numeric expression by itself.</span><span class="sxs-lookup"><span data-stu-id="13f6b-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="13f6b-111">The final line shows a combination of a variable with two literals.</span><span class="sxs-lookup"><span data-stu-id="13f6b-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="13f6b-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span><span class="sxs-lookup"><span data-stu-id="13f6b-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="13f6b-113">You must use the expression as part of a complete statement.</span><span class="sxs-lookup"><span data-stu-id="13f6b-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="13f6b-114">To store a numeric value</span><span class="sxs-lookup"><span data-stu-id="13f6b-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="13f6b-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span><span class="sxs-lookup"><span data-stu-id="13f6b-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="13f6b-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span><span class="sxs-lookup"><span data-stu-id="13f6b-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="13f6b-117">자세한 내용은 [문](../../../../visual-basic/language-reference/statements/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f6b-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="13f6b-118">Multiple Operators</span><span class="sxs-lookup"><span data-stu-id="13f6b-118">Multiple Operators</span></span>  
 <span data-ttu-id="13f6b-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span><span class="sxs-lookup"><span data-stu-id="13f6b-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="13f6b-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span><span class="sxs-lookup"><span data-stu-id="13f6b-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="13f6b-121">To override normal operator precedence</span><span class="sxs-lookup"><span data-stu-id="13f6b-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="13f6b-122">Use parentheses to enclose the operations you want to be performed first.</span><span class="sxs-lookup"><span data-stu-id="13f6b-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="13f6b-123">The following example shows two different results with the same operands and operators.</span><span class="sxs-lookup"><span data-stu-id="13f6b-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="13f6b-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span><span class="sxs-lookup"><span data-stu-id="13f6b-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="13f6b-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span><span class="sxs-lookup"><span data-stu-id="13f6b-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="13f6b-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="13f6b-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f6b-127">참조</span><span class="sxs-lookup"><span data-stu-id="13f6b-127">See also</span></span>

- [<span data-ttu-id="13f6b-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="13f6b-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="13f6b-129">값 비교</span><span class="sxs-lookup"><span data-stu-id="13f6b-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="13f6b-130">문</span><span class="sxs-lookup"><span data-stu-id="13f6b-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="13f6b-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="13f6b-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="13f6b-132">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="13f6b-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="13f6b-133">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="13f6b-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
