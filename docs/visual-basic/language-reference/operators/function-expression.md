---
title: 함수 식
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 454c4e3d926640934a8edc4fcb16e4308a89dd50
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632339"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="1db36-102">함수 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1db36-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="1db36-103">함수 람다 식을 정의 하는 매개 변수 및 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1db36-104">구문</span><span class="sxs-lookup"><span data-stu-id="1db36-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="1db36-105">구성 요소</span><span class="sxs-lookup"><span data-stu-id="1db36-105">Parts</span></span>  
  
|<span data-ttu-id="1db36-106">용어</span><span class="sxs-lookup"><span data-stu-id="1db36-106">Term</span></span>|<span data-ttu-id="1db36-107">정의</span><span class="sxs-lookup"><span data-stu-id="1db36-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="1db36-108">옵션.</span><span class="sxs-lookup"><span data-stu-id="1db36-108">Optional.</span></span> <span data-ttu-id="1db36-109">이 프로시저의 매개 변수를 나타내는 지역 변수 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="1db36-110">목록이 비어 있는 경우에도 괄호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="1db36-111">[매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db36-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="1db36-112">필수</span><span class="sxs-lookup"><span data-stu-id="1db36-112">Required.</span></span> <span data-ttu-id="1db36-113">단일 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-113">A single expression.</span></span> <span data-ttu-id="1db36-114">식의 형식은 함수의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="1db36-115">필수</span><span class="sxs-lookup"><span data-stu-id="1db36-115">Required.</span></span> <span data-ttu-id="1db36-116">`Return` 문을 사용 하 여 값을 반환 하는 문 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="1db36-117">[Return 문](../../../visual-basic/language-reference/statements/return-statement.md)을 참조 하십시오. 반환 되는 값의 형식은 함수의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1db36-118">주의</span><span class="sxs-lookup"><span data-stu-id="1db36-118">Remarks</span></span>  
 <span data-ttu-id="1db36-119">*람다 식은* 값을 계산 하 고 반환 하는 이름이 없는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="1db36-120">`RemoveHandler`에 대 한 인수를 제외 하 고 대리자 형식을 사용할 수 있는 모든 곳에서 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="1db36-121">대리자에 대 한 자세한 내용과 대리자에 람다 식을 사용 하는 방법에 대 한 자세한 내용은 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db36-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="1db36-122">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="1db36-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="1db36-123">람다 식의 구문은 표준 함수의 구문과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="1db36-124">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="1db36-125">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="1db36-126">람다 식에는 `Overloads` 또는 `Overrides`와 같은 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="1db36-127">람다 식은 `As` 절을 사용 하 여 함수의 반환 형식을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="1db36-128">대신, 단일 줄 람다 식의 본문이로 계산 되는 값 또는 여러 줄로 된 람다 식의 반환 값에서 형식이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="1db36-129">예를 들어 한 줄 람다 식의 본문이 `Where cust.City = "London"`이면 반환 형식은 `Boolean`됩니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="1db36-130">한 줄로 된 람다 식의 본문은 문이 아니라 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="1db36-131">본문은 함수 프로시저에 대 한 호출로 구성 될 수 있지만 sub 프로시저에 대 한 호출로 구성 될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="1db36-132">모든 매개 변수에는 지정 된 데이터 형식이 있어야 합니다. 그렇지 않으면 모두 유추 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="1db36-133">선택적 및 Paramarray 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="1db36-134">제네릭 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1db36-135">예</span><span class="sxs-lookup"><span data-stu-id="1db36-135">Example</span></span>  
 <span data-ttu-id="1db36-136">다음 예제에서는 간단한 람다 식을 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="1db36-137">첫 번째에서는 `Dim`를 사용 하 여 함수의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="1db36-138">함수를 호출 하려면 매개 변수의 값으로를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="1db36-139">예</span><span class="sxs-lookup"><span data-stu-id="1db36-139">Example</span></span>  
 <span data-ttu-id="1db36-140">또는 함수를 동시에 선언 하 고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="1db36-141">예</span><span class="sxs-lookup"><span data-stu-id="1db36-141">Example</span></span>  
 <span data-ttu-id="1db36-142">다음은 해당 인수를 증가 하 고 값을 반환 하는 람다 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="1db36-143">이 예제에서는 함수에 대 한 단일 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="1db36-144">더 많은 예제는 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db36-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="1db36-145">예</span><span class="sxs-lookup"><span data-stu-id="1db36-145">Example</span></span>  
 <span data-ttu-id="1db36-146">람다 식은 LINQ (통합 언어 쿼리)에서 많은 쿼리 연산자의 기반이 되며 메서드 기반 쿼리에서 명시적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-146">Lambda expressions underlie many of the query operators in Language-Integrated Query (LINQ), and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="1db36-147">다음 예제에서는 일반적인 LINQ 쿼리를 보여 오고 쿼리를 메서드 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1db36-147">The following example shows a typical LINQ query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="1db36-148">쿼리 메서드에 대 한 자세한 내용은 [쿼리](../../../visual-basic/language-reference/queries/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db36-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="1db36-149">표준 쿼리 연산자에 대 한 자세한 내용은 [표준 쿼리 연산자 개요](../../programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1db36-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db36-150">참조</span><span class="sxs-lookup"><span data-stu-id="1db36-150">See also</span></span>

- [<span data-ttu-id="1db36-151">Function 문</span><span class="sxs-lookup"><span data-stu-id="1db36-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1db36-152">람다 식</span><span class="sxs-lookup"><span data-stu-id="1db36-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="1db36-153">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="1db36-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="1db36-154">문</span><span class="sxs-lookup"><span data-stu-id="1db36-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="1db36-155">값 비교</span><span class="sxs-lookup"><span data-stu-id="1db36-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="1db36-156">부울 식</span><span class="sxs-lookup"><span data-stu-id="1db36-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="1db36-157">If 연산자</span><span class="sxs-lookup"><span data-stu-id="1db36-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="1db36-158">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="1db36-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
