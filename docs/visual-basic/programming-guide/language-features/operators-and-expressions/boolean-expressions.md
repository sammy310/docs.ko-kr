---
title: 부울 식
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 8d34eb4c8b14bb4754f2a3cf5b6f9a7601aa4662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388960"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="8ed8b-102">부울 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ed8b-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="8ed8b-103">*부울 식은* [부울 데이터 형식의](../../../language-reference/data-types/boolean-data-type.md)값 (또는)으로 계산 되는 식입니다. `True` `False`</span><span class="sxs-lookup"><span data-stu-id="8ed8b-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="8ed8b-104">`Boolean`식은 여러 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="8ed8b-105">가장 간단한 방법은 `Boolean` `Boolean` 다음 예제와 같이 변수의 값을 리터럴로 직접 비교 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="8ed8b-106">= 연산자의 두 가지 의미</span><span class="sxs-lookup"><span data-stu-id="8ed8b-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="8ed8b-107">대입문은 `newCustomer = True` 위의 예제에서 식과 동일 하지만 다른 함수를 수행 하 고 다르게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="8ed8b-108">앞의 예제에서 식은 `newCustomer = True` 부울 값을 나타내고 `=` 부호는 비교 연산자로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="8ed8b-109">독립 실행형 문에서 `=` 부호는 대입 연산자로 해석 되 고 오른쪽의 값을 왼쪽의 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="8ed8b-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="8ed8b-111">자세한 내용은 [값 비교](value-comparisons.md) 및 [문](../../../language-reference/statements/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-111">For further information, see [Value Comparisons](value-comparisons.md) and [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="8ed8b-112">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="8ed8b-112">Comparison Operators</span></span>  
 <span data-ttu-id="8ed8b-113">,,,, 및와 같은 비교 연산자는 `=` `<` `>` `<>` `<=` `>=` 연산자의 좌 변에 있는 식을 연산자 우변의 식과 비교 하 고 결과를 또는로 평가 하 여 부울 식을 생성 `True` `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="8ed8b-114">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="8ed8b-115">42는 81 보다 작으므로 앞의 예제에서 부울 식은로 계산 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="8ed8b-116">이러한 식 종류에 대 한 자세한 내용은 [값 비교](value-comparisons.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-116">For more information on this kind of expression, see [Value Comparisons](value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="8ed8b-117">논리 연산자와 결합 된 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="8ed8b-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="8ed8b-118">논리 연산자를 사용 하 여 비교 식을 결합 하 여 보다 복잡 한 부울 식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="8ed8b-119">다음 예에서는 비교 연산자를 논리 연산자와 함께 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="8ed8b-120">앞의 예제에서 전체 식의 값은 연산자의 양쪽에 있는 식의 값에 따라 달라 집니다 `And` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="8ed8b-121">두 식이 모두 이면 `True` 전체 식이로 평가 `True` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="8ed8b-122">두 식이 모두 이면 `False` 전체 식이로 평가 `False` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="8ed8b-123">단락 연산자</span><span class="sxs-lookup"><span data-stu-id="8ed8b-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="8ed8b-124">논리 연산자 `AndAlso` 및 `OrElse` *표현 동작은 단락*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="8ed8b-125">단락 연산자는 왼쪽 피연산자를 먼저 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="8ed8b-126">왼쪽 피연산자가 전체 식의 값을 결정 하는 경우 오른쪽 식을 계산 하지 않고 프로그램 실행이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="8ed8b-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="8ed8b-128">앞의 예제에서 연산자는 왼쪽 식를 계산 `45 < 12` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="8ed8b-129">왼쪽 식이로 계산 되기 때문에 `False` 전체 논리 식은로 계산 되어야 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="8ed8b-130">따라서 프로그램 실행은 `If` 오른쪽 식를 평가 하지 않고 블록 내에서 코드 실행을 건너뜁니다 `testFunction(3)` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="8ed8b-131">`testFunction()`왼쪽 식이 전체 식을 falsifies이 예에서는를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="8ed8b-132">마찬가지로를 사용 하는 논리 식의 왼쪽 식이 `OrElse` 로 계산 `True` 되 면 왼쪽 식에서 전체 식의 유효성을 이미 검사 했기 때문에 오른쪽 식을 계산 하지 않고 다음 코드 줄로 실행을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="8ed8b-133">단락 이외의 연산자와 비교</span><span class="sxs-lookup"><span data-stu-id="8ed8b-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="8ed8b-134">반면 논리 연산자와는 논리 연산자를 모두 사용할 때 계산 됩니다 `And` `Or` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="8ed8b-135">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="8ed8b-136">앞의 예제에서는 `testFunction()` 왼쪽 식이로 계산 되는 경우에도를 호출 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="8ed8b-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="8ed8b-137">괄호 식</span><span class="sxs-lookup"><span data-stu-id="8ed8b-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="8ed8b-138">괄호를 사용 하 여 부울 식의 계산 순서를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="8ed8b-139">괄호로 묶은 식이 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="8ed8b-140">여러 중첩 수준에 대해 가장 많이 중첩 된 식에 우선 순위가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="8ed8b-141">괄호 안에 연산자 우선 순위 규칙에 따라 계산이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="8ed8b-142">자세한 내용은 [Visual Basic 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ed8b-142">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed8b-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ed8b-143">See also</span></span>

- [<span data-ttu-id="8ed8b-144">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="8ed8b-144">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="8ed8b-145">값 비교</span><span class="sxs-lookup"><span data-stu-id="8ed8b-145">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="8ed8b-146">문</span><span class="sxs-lookup"><span data-stu-id="8ed8b-146">Statements</span></span>](../statements.md)
- [<span data-ttu-id="8ed8b-147">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="8ed8b-147">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="8ed8b-148">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="8ed8b-148">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
- [<span data-ttu-id="8ed8b-149">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="8ed8b-149">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="8ed8b-150">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8ed8b-150">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)
