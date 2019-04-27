---
title: '방법: 숫자 값 (Visual Basic)를 계산 합니다.'
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
ms.openlocfilehash: 33184d9be275f5e777ffd79c6dd4e3182d865de7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864684"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="1942f-102">방법: 숫자 값 (Visual Basic)를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="1942f-103">숫자 식 사용 하 여 숫자 값을 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="1942f-104">A *숫자 식* 리터럴, 상수 및 숫자 값을 나타내는 변수를 포함 하는 식과 해당 값에 대해 작동 하는 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="1942f-105">숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="1942f-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="1942f-106">숫자 값을 계산 하기</span><span class="sxs-lookup"><span data-stu-id="1942f-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="1942f-107">숫자 식에 하나 이상의 숫자 리터럴, 상수 및 변수를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="1942f-108">다음 예에서는 유효한 숫자 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="1942f-109">처음 세 줄에는 리터럴, 상수 및 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="1942f-110">각각 자체는 유효한 숫자 식을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="1942f-111">마지막 줄에는 두 개의 리터럴을 사용 하 여 변수 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="1942f-112">숫자 식이 자체적으로 전체 Visual Basic 문을 구성 하지 않는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="1942f-113">식 문이 종결의 일부로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="1942f-114">숫자 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="1942f-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="1942f-115">다음 예제에서는 숫자 식에 변수를 나타내는 값을 할당 하는 대입문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="1942f-116">이전 예제에서는 같음 연산자의 오른쪽에 있는 식의 값 (`=`)를 변수에 할당 됩니다 `j` 연산자의 좌 변에 있는 하므로 `j` 276으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="1942f-117">자세한 내용은 [문](../../../../visual-basic/language-reference/statements/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1942f-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="1942f-118">여러 연산자</span><span class="sxs-lookup"><span data-stu-id="1942f-118">Multiple Operators</span></span>  
 <span data-ttu-id="1942f-119">숫자 식 이상의 연산자를 포함 하는 경우 평가 되는 순서는 연산자 우선 순위 규칙에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="1942f-120">식을 위의 예와; 괄호로 묶습니다 있습니다 연산자 우선 순위 규칙을 재정의 하려면 괄호 안의 식이 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="1942f-121">일반 연산자 우선 순위를 재정의 하려면</span><span class="sxs-lookup"><span data-stu-id="1942f-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="1942f-122">괄호를 사용 하 여 먼저 수행 하려는 작업을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="1942f-123">다음 예제에서는 피연산자와 연산자를 사용 하 여 두 개의 서로 다른 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="1942f-124">앞의 예제에 대 한 계산에 `j` 더하기 연산자를 수행 합니다. (`+`) 첫 번째 때문에 괄호로 `(67 + i)` 일반 우선 순위 및 할당 된 값을 재정의 `j` 은 276 (4 회 69).</span><span class="sxs-lookup"><span data-stu-id="1942f-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="1942f-125">에 대 한 계산 `k` 일반 우선 순위 연산자 수행 (`*` 하기 전에 `+`), 및 할당 된 값 `k` 은 270 (268 + 2).</span><span class="sxs-lookup"><span data-stu-id="1942f-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="1942f-126">자세한 내용은 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1942f-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1942f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="1942f-127">See also</span></span>

- [<span data-ttu-id="1942f-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="1942f-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="1942f-129">값 비교</span><span class="sxs-lookup"><span data-stu-id="1942f-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="1942f-130">문(C++)</span><span class="sxs-lookup"><span data-stu-id="1942f-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="1942f-131">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="1942f-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1942f-132">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="1942f-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="1942f-133">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="1942f-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
