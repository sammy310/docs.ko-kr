---
title: 값 비교(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818607"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="bc00c-102">값 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc00c-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="bc00c-103">숫자 변수 값을 비교 하는 식을 생성 하려면 비교 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="bc00c-104">이러한 식은 반환을 `Boolean` 비교가 true 인지에 따라 값 false입니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="bc00c-105">이러한 식의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="bc00c-106">첫 번째 식의 결과가 `True`이므로 45 26 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="bc00c-107">두 번째 예에서는 `False`이므로 26 45 보다 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="bc00c-108">또한이 방식으로 숫자 식을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="bc00c-109">비교 식 자체는 다음 예제와 같이 복잡 한 식 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="bc00c-110">이전 복잡 한 식에는 리터럴, 변수 및 함수 호출이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="bc00c-111">비교 연산자의 양쪽에 있는 식을 평가 하 고 결과 값을 사용 하 여 그런 비교는 `>=` 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="bc00c-112">왼쪽에 있는 식의 값 보다 크면 이거나 오른쪽 식의 값과 같으면는 전체 식을 계산 하는 경우 `True`이 고, 그렇지 않으면 결과가 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="bc00c-113">값을 비교 하는 식에서 가장 흔히 사용 됩니다 `If...Then` 다음 예제와 같이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="bc00c-114">`=` 기호는 대입 연산자 뿐만 아니라 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="bc00c-115">비교 연산자로 사용 하는 다음 예제에서와 같이 왼쪽의 값이 오른쪽의 값과 같으면 여부를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="bc00c-116">비교 식을 어디서 나 사용할 수도 있습니다는 `Boolean` 값이 필요한, 예:는 `If`, `While`, `Loop`, 또는 `ElseIf` 문을에 할당 하거나 값을 전달 하는 경우 또는 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="bc00c-117">다음 예제에서는 비교 식에서 반환 된 값에 할당 되는 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bc00c-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="bc00c-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc00c-118">See also</span></span>

- [<span data-ttu-id="bc00c-119">부울 식</span><span class="sxs-lookup"><span data-stu-id="bc00c-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="bc00c-120">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="bc00c-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="bc00c-121">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc00c-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="bc00c-122">방법: 숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="bc00c-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="bc00c-123">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bc00c-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
