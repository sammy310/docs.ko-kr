---
description: '자세한 정보: 부울 식 (Visual Basic)'
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
ms.openlocfilehash: 3b752e2146755e1272b261f32931e3022e8ef354
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465316"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="3f498-103">부울 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f498-103">Boolean Expressions (Visual Basic)</span></span>

<span data-ttu-id="3f498-104">*부울 식은* [부울 데이터 형식의](../../../language-reference/data-types/boolean-data-type.md)값 (또는)으로 계산 되는 식입니다. `True` `False`</span><span class="sxs-lookup"><span data-stu-id="3f498-104">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="3f498-105">`Boolean` 식은 여러 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-105">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="3f498-106">가장 간단한 방법은 `Boolean` `Boolean` 다음 예제와 같이 변수의 값을 리터럴로 직접 비교 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-106">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="3f498-107">= 연산자의 두 가지 의미</span><span class="sxs-lookup"><span data-stu-id="3f498-107">Two Meanings of the = Operator</span></span>  

 <span data-ttu-id="3f498-108">대입문은 `newCustomer = True` 위의 예제에서 식과 동일 하지만 다른 함수를 수행 하 고 다르게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-108">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="3f498-109">앞의 예제에서 식은 `newCustomer = True` 부울 값을 나타내고 `=` 부호는 비교 연산자로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-109">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="3f498-110">독립 실행형 문에서 `=` 부호는 대입 연산자로 해석 되 고 오른쪽의 값을 왼쪽의 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-110">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="3f498-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-111">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="3f498-112">자세한 내용은 [값 비교](value-comparisons.md) 및 [문](../../../language-reference/statements/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f498-112">For further information, see [Value Comparisons](value-comparisons.md) and [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="3f498-113">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="3f498-113">Comparison Operators</span></span>  

 <span data-ttu-id="3f498-114">,,,, 및와 같은 비교 연산자는 `=` `<` `>` `<>` `<=` `>=` 연산자의 좌 변에 있는 식을 연산자 우변의 식과 비교 하 고 결과를 또는로 평가 하 여 부울 식을 생성 `True` `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-114">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="3f498-115">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-115">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="3f498-116">42는 81 보다 작으므로 앞의 예제에서 부울 식은로 계산 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="3f498-116">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="3f498-117">이러한 식 종류에 대 한 자세한 내용은 [값 비교](value-comparisons.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f498-117">For more information on this kind of expression, see [Value Comparisons](value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="3f498-118">논리 연산자와 결합 된 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="3f498-118">Comparison Operators Combined with Logical Operators</span></span>  

 <span data-ttu-id="3f498-119">논리 연산자를 사용 하 여 비교 식을 결합 하 여 보다 복잡 한 부울 식을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-119">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="3f498-120">다음 예에서는 비교 연산자를 논리 연산자와 함께 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-120">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="3f498-121">앞의 예제에서 전체 식의 값은 연산자의 양쪽에 있는 식의 값에 따라 달라 집니다 `And` .</span><span class="sxs-lookup"><span data-stu-id="3f498-121">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="3f498-122">두 식이 모두 이면 `True` 전체 식이로 평가 `True` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-122">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="3f498-123">두 식이 모두 이면 `False` 전체 식이로 평가 `False` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-123">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="3f498-124">Short-Circuiting 연산자</span><span class="sxs-lookup"><span data-stu-id="3f498-124">Short-Circuiting Operators</span></span>  

 <span data-ttu-id="3f498-125">논리 연산자 `AndAlso` 및 `OrElse` *표현 동작은 단락* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-125">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="3f498-126">단락 연산자는 왼쪽 피연산자를 먼저 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-126">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="3f498-127">왼쪽 피연산자가 전체 식의 값을 결정 하는 경우 오른쪽 식을 계산 하지 않고 프로그램 실행이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-127">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="3f498-128">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-128">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="3f498-129">앞의 예제에서 연산자는 왼쪽 식를 계산 `45 < 12` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-129">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="3f498-130">왼쪽 식이로 계산 되기 때문에 `False` 전체 논리 식은로 계산 되어야 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="3f498-130">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="3f498-131">따라서 프로그램 실행은 `If` 오른쪽 식를 평가 하지 않고 블록 내에서 코드 실행을 건너뜁니다 `testFunction(3)` .</span><span class="sxs-lookup"><span data-stu-id="3f498-131">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="3f498-132">`testFunction()`왼쪽 식이 전체 식을 falsifies이 예에서는를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-132">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="3f498-133">마찬가지로를 사용 하는 논리 식의 왼쪽 식이 `OrElse` 로 계산 `True` 되 면 왼쪽 식에서 전체 식의 유효성을 이미 검사 했기 때문에 오른쪽 식을 계산 하지 않고 다음 코드 줄로 실행을 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-133">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="3f498-134">단락 이외의 연산자와 비교</span><span class="sxs-lookup"><span data-stu-id="3f498-134">Comparison with Non-Short-Circuiting Operators</span></span>  

 <span data-ttu-id="3f498-135">반면 논리 연산자와는 논리 연산자를 모두 사용할 때 계산 됩니다 `And` `Or` .</span><span class="sxs-lookup"><span data-stu-id="3f498-135">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="3f498-136">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-136">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="3f498-137">앞의 예제에서는 `testFunction()` 왼쪽 식이로 계산 되는 경우에도를 호출 합니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="3f498-137">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="3f498-138">괄호 식</span><span class="sxs-lookup"><span data-stu-id="3f498-138">Parenthetical Expressions</span></span>  

 <span data-ttu-id="3f498-139">괄호를 사용 하 여 부울 식의 계산 순서를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-139">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="3f498-140">괄호로 묶은 식이 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-140">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="3f498-141">여러 중첩 수준에 대해 가장 많이 중첩 된 식에 우선 순위가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-141">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="3f498-142">괄호 안에 연산자 우선 순위 규칙에 따라 계산이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f498-142">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="3f498-143">자세한 내용은 [Visual Basic 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f498-143">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f498-144">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3f498-144">See also</span></span>

- [<span data-ttu-id="3f498-145">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="3f498-145">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="3f498-146">값 비교</span><span class="sxs-lookup"><span data-stu-id="3f498-146">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="3f498-147">문</span><span class="sxs-lookup"><span data-stu-id="3f498-147">Statements</span></span>](../statements.md)
- [<span data-ttu-id="3f498-148">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="3f498-148">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="3f498-149">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="3f498-149">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
- [<span data-ttu-id="3f498-150">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="3f498-150">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="3f498-151">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f498-151">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)
