---
title: 람다 식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: c43739e098a91d54d300fa7074d1563da179c0e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665795"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="d0255-102">람다 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0255-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="d0255-103">A *람다 식* 은 함수 또는 서브루틴 대리자 유효한 모든 곳에서 사용할 수 있는 이름이 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="d0255-104">람다 식은 함수 또는 서브루틴 수 있으며 한 줄 또는 여러 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="d0255-105">람다 식에는 현재 범위에서 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0255-106">`RemoveHandler` 문은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="d0255-107">람다 식에는 대리자 매개 변수에 전달할 수 없습니다 `RemoveHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="d0255-108">람다 식을 사용 하 여 만든 합니다 `Function` 또는 `Sub` 표준 함수 또는 서브루틴을 만드는 경우와 마찬가지로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="d0255-109">그러나 람다 식 문에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="d0255-110">다음 예제는 해당 인수를 증가 시키고 값을 반환 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="d0255-111">함수에 대 한 모두를 단일 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="d0255-112">다음 예제는 콘솔에 값을 기록 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="d0255-113">모두 단일 줄 및 여러 줄 람다 식 구문은 서브루틴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="d0255-114">앞의 예제에서는 람다 식 변수 이름에 할당 된 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="d0255-115">변수를 참조할 때마다 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="d0255-116">또한 선언 하 고 다음 예와에서 같이 동시에 람다 식을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="d0255-117">람다 식은 함수 호출의 값으로 반환 될 수 있습니다 (예제에 표시 된 대로 합니다 [상황에 맞는](#context) 이 항목의 뒷부분에 나오는 섹션), 다음에 표시 된 대로 대리자 형식을 사용 하는 매개 변수를 인수로 전달 하거나 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="d0255-118">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="d0255-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="d0255-119">람다 식의 구문은 유사 표준 함수 또는 서브루틴의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="d0255-120">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-120">The differences are as follows:</span></span>  
  
- <span data-ttu-id="d0255-121">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-121">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="d0255-122">람다 식은와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="d0255-123">한 줄 람다 함수를 사용 하지 마십시오는 `As` 절 반환 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="d0255-124">대신, 형식 람다 식의 본문으로 계산 되는 값에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="d0255-125">예를 들어, 람다 식의 본문이 `cust.City = "London"`, 해당 반환 형식은 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="d0255-126">여러 줄 람다 함수에 지정할 수 있습니다 하거나 반환 형식을 사용 하 여는 `As` 절을 생략 하거나는 `As` 절 반환 형식을 유추 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="d0255-127">경우는 `As` 여러 줄 람다 함수에 대 한 절을 생략 하면, 반환 형식을 기준 형식 모두로 유추 됩니다를 `Return` 여러 줄 람다 함수에는 문.</span><span class="sxs-lookup"><span data-stu-id="d0255-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="d0255-128">합니다 *기준 형식* 다른 모든 형식을 변환할 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="d0255-129">이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식에 범위를 좁힐 수 있는 고유 형식이입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="d0255-130">이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="d0255-131">이 경우 경우 `Option Strict` 로 설정 된 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="d0255-132">예를 들어 식에 제공 된를 `Return` 형식의 값을 포함 하는 문을 `Integer`, `Long`, 및 `Double`, 결과 배열이 형식의 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="d0255-133">둘 다 `Integer` 하 고 `Long` 변환할 `Double` 만 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="d0255-134">따라서 기준 형식은 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="d0255-135">자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0255-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
- <span data-ttu-id="d0255-136">한 줄 함수의 본문에는 문이 아닌 값을 반환 하는 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="d0255-137">방법이 없는 `Return` 문을 한 줄 함수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="d0255-138">한 줄 함수에서 반환 된 값에는 함수 본문에 있는 식의 값이입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
- <span data-ttu-id="d0255-139">서브루틴을 한 줄의 본문에는 한 줄 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
- <span data-ttu-id="d0255-140">한 줄 함수와 서브루틴이 포함 하지 마십시오는 `End Function` 또는 `End Sub` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="d0255-141">람다 식 매개 변수의 데이터 형식을 사용 하 여 지정할 수 있습니다는 `As` 키워드 또는 매개 변수의 데이터 형식을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="d0255-142">데이터 형식 중 하나 또는 모두를 유추할 수 해야 모든 매개 변수에 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="d0255-143">`Optional` 및 `Paramarray` 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
- <span data-ttu-id="d0255-144">제네릭 매개 변수가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="d0255-145">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="d0255-145">Async Lambdas</span></span>  
 <span data-ttu-id="d0255-146">사용 하 여 비동기 처리를 통합 하는 람다 식과 문을 쉽게 만들 수 있습니다 합니다 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 하 고 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="d0255-147">예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="d0255-148">비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수 있습니다는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="d0255-149">이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="d0255-150">만들기 및 비동기 메서드를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Async 및 Await를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a> <span data-ttu-id="d0255-151">컨텍스트</span><span class="sxs-lookup"><span data-stu-id="d0255-151">Context</span></span>  
 <span data-ttu-id="d0255-152">람다 식 정의 된 범위와 해당 컨텍스트를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="d0255-153">동일한 액세스 권한을 포함 하는 범위에 작성 된 모든 코드에</span><span class="sxs-lookup"><span data-stu-id="d0255-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="d0255-154">여기에 대 한 멤버 변수, 함수 및 sub의 `Me`를 포함 하는 범위에서 지역 변수 및 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="d0255-155">지역 변수 및 매개 변수를 포함 하는 범위에 대 한 액세스는 해당 범위의 수명을 넘어서는 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="d0255-156">으로 참조 하는 람다 식을 대리자를 가비지 컬렉션에 사용할 수 없는 원본 환경에서 변수에 대 한 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="d0255-157">다음 예에서 변수 `target` 로컬인 `makeTheGame`, 메서드는 람다 식 `playTheGame` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="d0255-158">반환 된 람다 식에 할당 하는 참고 `takeAGuess` 에서 `Main`, 여전히 로컬 변수에 대 한 액세스를 권한이 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="d0255-159">다음 예제에서는 광범위 한 중첩 된 람다 식의 액세스 권한 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="d0255-160">반환된 된 람다 식이 실행 되는 시기 `Main` 으로 `aDel`, 이러한 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
- <span data-ttu-id="d0255-161">이전에 정의 된 클래스의 필드: `aField`</span><span class="sxs-lookup"><span data-stu-id="d0255-161">A field of the class in which it is defined: `aField`</span></span>  
  
- <span data-ttu-id="d0255-162">이전에 정의 된 클래스의 속성: `aProp`</span><span class="sxs-lookup"><span data-stu-id="d0255-162">A property of the class in which it is defined: `aProp`</span></span>  
  
- <span data-ttu-id="d0255-163">메서드의 매개 변수 `functionWithNestedLambda`, 정의 됩니다. `level1`</span><span class="sxs-lookup"><span data-stu-id="d0255-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
- <span data-ttu-id="d0255-164">로컬 변수의 `functionWithNestedLambda`: `localVar`</span><span class="sxs-lookup"><span data-stu-id="d0255-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
- <span data-ttu-id="d0255-165">중첩 된 람다 식의 매개 변수: `level2`</span><span class="sxs-lookup"><span data-stu-id="d0255-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="d0255-166">대리자 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d0255-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="d0255-167">람다 식은 호환 되는 대리자 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="d0255-168">호환성에 대 한 일반 요구 사항에 대 한 정보를 참조 하세요 [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="d0255-169">다음 코드 예제를 암시적으로 변환 하는 람다 식을 표시 하는 예를 들어 `Func(Of Integer, Boolean)` 또는 일치 하는 대리자 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="d0255-170">다음 코드 예제에서는 암시적으로 변환 하는 람다 식을 보여 줍니다. `Sub(Of Double, String, Double)` 또는 일치 하는 대리자 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="d0255-171">람다 식을 대리자에 할당 하거나 프로시저에 인수로 전달할 때 매개 변수 이름을 지정할 수 있지만 형식을 가져오도록 수 대리자에서 해당 데이터 형식은 생략 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d0255-172">예제</span><span class="sxs-lookup"><span data-stu-id="d0255-172">Examples</span></span>  
  
- <span data-ttu-id="d0255-173">다음 예제에서는 정의 반환 하는 람다 식 `True` nullable 인수에 값을 할당된 하는 경우 및 `False` 의 값이 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- <span data-ttu-id="d0255-174">다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 람다 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0255-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d0255-175">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0255-175">See also</span></span>

- [<span data-ttu-id="d0255-176">절차</span><span class="sxs-lookup"><span data-stu-id="d0255-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d0255-177">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="d0255-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d0255-178">대리자</span><span class="sxs-lookup"><span data-stu-id="d0255-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="d0255-179">Function 문</span><span class="sxs-lookup"><span data-stu-id="d0255-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d0255-180">Sub 문</span><span class="sxs-lookup"><span data-stu-id="d0255-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d0255-181">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="d0255-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d0255-182">방법: 프로시저에 Visual Basic에서 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="d0255-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="d0255-183">방법: 람다 식 만들기</span><span class="sxs-lookup"><span data-stu-id="d0255-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="d0255-184">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="d0255-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
