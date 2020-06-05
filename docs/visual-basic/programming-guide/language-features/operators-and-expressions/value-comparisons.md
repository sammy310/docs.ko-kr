---
title: 값 비교
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
ms.openlocfilehash: 01816b5730cf4fda61f1737ce3ce00ab82f57da8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403397"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="edefb-102">값 비교(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edefb-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="edefb-103">비교 연산자를 사용 하 여 숫자 변수의 값을 비교 하는 식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="edefb-104">이러한 식은 `Boolean` 비교가 true 인지 false 인지에 따라 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="edefb-105">이러한 식의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="edefb-106">`True`45가 26 보다 크므로 첫 번째 식은로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="edefb-107">두 번째 예제는 `False` 26이 45 보다 크지 않기 때문에로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="edefb-108">이러한 방식으로 숫자 식을 비교할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="edefb-109">비교 하는 식은 다음 예제와 같이 복합 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="edefb-110">앞의 복합 식에는 리터럴, 변수 및 함수 호출이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="edefb-111">비교 연산자의 양쪽에 있는 식을 계산 하 고 결과 값을 비교 연산자를 사용 하 여 비교 합니다 `>=` .</span><span class="sxs-lookup"><span data-stu-id="edefb-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="edefb-112">좌 변의 식의 값이 오른쪽 식의 값 보다 크거나 같으면 전체 식이로 계산 되 고 `True` , 그렇지 않으면로 계산 됩니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="edefb-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="edefb-113">값을 비교 하는 식은 `If...Then` 다음 예제와 같이 생성에서 가장 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="edefb-114">`=`부호는 비교 연산자 및 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="edefb-115">비교 연산자로 사용 되는 경우 다음 예제와 같이 왼쪽의 값이 오른쪽의 값과 같은지 여부를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="edefb-116">`Boolean`,, 또는 문과 같이 값이 필요한 경우 `If` `While` `Loop` `ElseIf` 또는 변수에 할당 하거나 값을 변수에 전달할 때 `Boolean` 비교 식을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edefb-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="edefb-117">다음 예에서는 비교 식에서 반환 된 값이 변수에 할당 됩니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="edefb-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="edefb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edefb-118">See also</span></span>

- [<span data-ttu-id="edefb-119">부울 식</span><span class="sxs-lookup"><span data-stu-id="edefb-119">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="edefb-120">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="edefb-120">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="edefb-121">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edefb-121">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="edefb-122">방법: 숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="edefb-122">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="edefb-123">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="edefb-123">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
