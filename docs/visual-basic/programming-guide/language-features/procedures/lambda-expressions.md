---
title: 람다 식
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249671"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="ffeaa-102">람다 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffeaa-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="ffeaa-103">*람다 식은* 대리자가 유효한 모든 곳에서 사용할 수 있는 이름이 없는 함수 또는 서브루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="ffeaa-104">Lambda 표현식은 함수 또는 서브루틴일 수 있으며 한 줄 또는 다중 줄이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="ffeaa-105">현재 범위에서 람다 식으로 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="ffeaa-106">문은 `RemoveHandler` 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="ffeaa-107">`RemoveHandler`의 대리자 매개 변수에 대해 람다 식을 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="ffeaa-108">표준 함수 또는 서브루틴을 `Function` 만드는 `Sub` 것처럼 또는 키워드를 사용하여 lambda 식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="ffeaa-109">그러나 람다 식은 문에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="ffeaa-110">다음 예제는 인수를 증분하고 값을 반환하는 lambda 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="ffeaa-111">이 예제에서는 함수에 대한 단일 줄 람다 식 구문과 다중 줄 람다 식 구문을 모두 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="ffeaa-112">다음 예제는 콘솔에 값을 쓰는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="ffeaa-113">이 예제에서는 서브루틴에 대한 단일 줄 람다 식 구문을 모두 보여 주며 다중 줄 람다 식 구문을 모두 보여 주며, 이 두 가지를 모두 보여 주며, 이 두 가지를 보여 주며, 이는 서브루틴에 대한 단일 줄 람다 식 구문을 모두 보여 주며, 이 두 가지를 모두 보여</span><span class="sxs-lookup"><span data-stu-id="ffeaa-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="ffeaa-114">이전 예제에서는 람다 식이 변수 이름에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="ffeaa-115">변수를 참조할 때마다 lambda 식을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="ffeaa-116">다음 예제와 같이 람다 식을 동시에 선언하고 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="ffeaa-117">람다 식은 함수 호출의 값으로 반환되거나(이 항목의 컨텍스트 [섹션의](#context) 예제에 나와 있음) 다음 예제와 같이 대리자 형식을 사용하는 매개 변수에 인수로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="ffeaa-118">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="ffeaa-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="ffeaa-119">람다 식의 구문은 표준 함수 또는 서브루틴의 구문과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="ffeaa-120">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-120">The differences are as follows:</span></span>

- <span data-ttu-id="ffeaa-121">람다 식에는 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="ffeaa-122">Lambda 식에는 또는 `Overloads` `Overrides`와 같은 수정자를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="ffeaa-123">단일 줄 람다 함수는 반환 `As` 형식을 지정하는 절을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="ffeaa-124">대신 형식은 lambda 식의 본문이 평가하는 값에서 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="ffeaa-125">예를 들어 lambda 식의 본문이 `cust.City = "London"`있는 경우 `Boolean`반환 형식은 입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="ffeaa-126">다중 줄 람다 함수에서 `As` 절을 사용하여 return 형식을 지정하거나 반환 형식이 유추되도록 `As` 절을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="ffeaa-127">다중 `As` 줄 람다 함수에 대한 절을 생략하면 반환 형식은 다중 줄 람다 `Return` 함수의 모든 문에서 지배적인 유형으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="ffeaa-128">*지배적인 형식은* 다른 모든 형식이 확장될 수 있는 고유한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="ffeaa-129">이 고유 형식을 확인할 수 없는 경우 주요 형식은 배열의 다른 모든 형식이 좁힐 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="ffeaa-130">이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="ffeaa-131">이 경우 `Option Strict` 컴파일러 오류가 `On`발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="ffeaa-132">예를 `Return` 들어 문에 제공된 식에 형식 `Integer`및 `Long` `Double`의 값이 포함된 경우 결과 `Double`배열은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="ffeaa-133">둘 `Integer` `Long` 다로 `Double` 확대되고 `Double`만 .</span><span class="sxs-lookup"><span data-stu-id="ffeaa-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="ffeaa-134">따라서 기준 형식은 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="ffeaa-135">자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="ffeaa-136">한 줄 함수의 본문은 문이 아닌 값을 반환하는 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="ffeaa-137">한 줄 `Return` 함수에 대한 문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="ffeaa-138">한 줄 함수에서 반환되는 값은 함수 본문에 있는 식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="ffeaa-139">한 줄 서브루틴의 본문은 한 줄 문이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="ffeaa-140">단일 줄 함수 및 서브루틴에는 `End Function` or `End Sub` 문이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="ffeaa-141">`As` 키워드를 사용하여 람다 식 매개 변수의 데이터 형식을 지정하거나 매개 변수의 데이터 형식을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="ffeaa-142">모든 매개 변수에는 지정된 데이터 형식이 있어야 하거나 모두 유추해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="ffeaa-143">`Optional`매개 `Paramarray` 변수는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="ffeaa-144">제네릭 매개 변수는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="ffeaa-145">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="ffeaa-145">Async Lambdas</span></span>

<span data-ttu-id="ffeaa-146">[Async](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드를 사용하여 비동기 처리를 통합하는 lambda 식 및 문을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="ffeaa-147">예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="ffeaa-148">[AddHandler 문에서](../../../../visual-basic/language-reference/statements/addhandler-statement.md)비동기 람다를 사용하여 동일한 이벤트 처리기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="ffeaa-149">이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="ffeaa-150">비동기 메서드를 만들고 사용하는 방법에 대한 자세한 내용은 [비동기 프로그래밍 및 Await를](../../../../visual-basic/programming-guide/concepts/async/index.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="ffeaa-151">Context</span><span class="sxs-lookup"><span data-stu-id="ffeaa-151">Context</span></span>

<span data-ttu-id="ffeaa-152">lambda 식은 해당 컨텍스트를 정의된 범위와 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="ffeaa-153">포함 범위에 기록된 코드와 동일한 액세스 권한을 가짐입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="ffeaa-154">여기에는 멤버 변수, 함수 및 subs, `Me`포함된 범위의 매개 변수 및 로컬 변수에 대한 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="ffeaa-155">포함 범위의 로컬 변수 및 매개 변수에 대한 액세스는 해당 범위의 수명 을 초과하여 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="ffeaa-156">lambda 식을 참조하는 대리자가 가비지 수집에 사용할 수 없는 한 원래 환경의 변수에 대한 액세스는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="ffeaa-157">다음 예제에서 변수는 `target` lambda 식이 `makeTheGame` `playTheGame` 정의 되는 메서드를 로컬로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="ffeaa-158">에 할당된 반환된 lambda 식은 여전히 지역 변수에 `target`액세스할 수 있습니다. `Main` `takeAGuess`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="ffeaa-159">다음 예제에서는 중첩된 lambda 식의 광범위한 액세스 권한을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="ffeaa-160">반환된 lambda 식이 에서 `Main` `aDel`실행되면 다음 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="ffeaa-161">정의된 클래스의 필드:`aField`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="ffeaa-162">정의된 클래스의 속성:`aProp`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="ffeaa-163">메서드가 정의되는 매개 `functionWithNestedLambda`변수:`level1`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="ffeaa-164">다음과 같은 `functionWithNestedLambda`로컬 변수가 있습니다.`localVar`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="ffeaa-165">중첩되는 람다 식의 매개 변수:`level2`</span><span class="sxs-lookup"><span data-stu-id="ffeaa-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="ffeaa-166">대리자 유형으로 변환</span><span class="sxs-lookup"><span data-stu-id="ffeaa-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="ffeaa-167">람다 식은 호환되는 대리자 유형으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="ffeaa-168">호환성에 대한 일반적인 요구 사항에 대한 자세한 내용은 [완화된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="ffeaa-169">예를 들어 다음 코드 예제에서는 암시적으로 `Func(Of Integer, Boolean)` 변환하는 lambda 식 또는 일치하는 대리자 서명을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="ffeaa-170">다음 코드 예제에서는 암시적으로 변환하거나 일치하는 대리자 시그니처를 `Sub(Of Double, String, Double)` 포함하는 lambda 식을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="ffeaa-171">lambda 식을 대리자에게 할당하거나 프로시저에 인수로 전달할 때 매개 변수 이름을 지정하지만 해당 데이터 형식을 생략하여 대리자에서 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="ffeaa-172">예</span><span class="sxs-lookup"><span data-stu-id="ffeaa-172">Examples</span></span>

- <span data-ttu-id="ffeaa-173">다음 예제에서는 nullable 값 형식 `True` 인수에 할당된 값이 있고 `False` 해당 값이 .인 `Nothing`경우 반환하는 lambda 식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="ffeaa-174">다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 lambda 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeaa-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="ffeaa-175">참조</span><span class="sxs-lookup"><span data-stu-id="ffeaa-175">See also</span></span>

- [<span data-ttu-id="ffeaa-176">절차</span><span class="sxs-lookup"><span data-stu-id="ffeaa-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ffeaa-177">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="ffeaa-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ffeaa-178">대리자</span><span class="sxs-lookup"><span data-stu-id="ffeaa-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ffeaa-179">Function 문</span><span class="sxs-lookup"><span data-stu-id="ffeaa-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ffeaa-180">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ffeaa-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ffeaa-181">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="ffeaa-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ffeaa-182">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="ffeaa-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="ffeaa-183">방법: 람다 식 만들기</span><span class="sxs-lookup"><span data-stu-id="ffeaa-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="ffeaa-184">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="ffeaa-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
