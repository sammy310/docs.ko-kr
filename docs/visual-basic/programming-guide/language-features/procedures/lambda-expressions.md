---
description: '자세한 정보: 람다 식 (Visual Basic)'
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
ms.openlocfilehash: adac7f0d0dbbff575837f691d70c7752eebb39f1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480091"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="b470e-103">람다 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b470e-103">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="b470e-104">*람다 식은* 대리자가 유효한 모든 위치에서 사용할 수 있는 이름이 없는 함수 또는 서브루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-104">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="b470e-105">람다 식은 함수나 서브루틴이 될 수 있으며 한 줄 또는 여러 줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-105">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="b470e-106">현재 범위에서 람다 식으로 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-106">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="b470e-107">`RemoveHandler`문은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-107">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="b470e-108">의 대리자 매개 변수에는 람다 식을 전달할 수 없습니다 `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="b470e-108">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="b470e-109">`Function` `Sub` 표준 함수 또는 서브루틴을 만들 때와 마찬가지로 또는 키워드를 사용 하 여 람다 식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-109">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="b470e-110">그러나 람다 식이 문에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-110">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="b470e-111">다음 예제는 인수를 증가 시키고 값을 반환 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-111">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="b470e-112">이 예제에서는 함수에 대 한 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-112">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="b470e-113">다음 예제는 콘솔에 값을 기록 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="b470e-114">이 예제에서는 서브루틴에 대 한 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="b470e-115">앞의 예제에서 람다 식은 변수 이름에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-115">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="b470e-116">변수를 참조할 때마다 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-116">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="b470e-117">다음 예제와 같이 람다 식을 동시에 선언 하 고 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-117">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="b470e-118">다음 예제와 같이 람다 식을 함수 호출의 값으로 반환 하거나 (이 항목의 뒷부분에 나오는 [컨텍스트](#context) 섹션의 예제에 표시 된 것 처럼), 대리자 형식을 사용 하는 매개 변수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-118">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="b470e-119">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="b470e-119">Lambda Expression Syntax</span></span>

<span data-ttu-id="b470e-120">람다 식의 구문은 표준 함수 또는 서브루틴의 구문과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-120">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="b470e-121">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-121">The differences are as follows:</span></span>

- <span data-ttu-id="b470e-122">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-122">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="b470e-123">람다 식에는 또는와 같은 한정자를 사용할 수 없습니다 `Overloads` `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="b470e-123">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="b470e-124">한 줄 람다 함수는 절을 사용 `As` 하 여 반환 형식을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-124">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="b470e-125">대신 람다 식의 본문이 계산 되는 값에서 형식이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-125">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="b470e-126">예를 들어, 람다 식의 본문이 이면 `cust.City = "London"` 반환 형식은 `Boolean` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-126">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="b470e-127">여러 줄 람다 함수에서 절을 사용 하 여 반환 형식을 지정 `As` 하거나 `As` 반환 형식이 유추 되도록 절을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-127">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="b470e-128">`As`여러 줄 람다 함수에 대해 절이 생략 된 경우 반환 형식은 `Return` 여러 줄 람다 함수에 있는 모든 문의 기준 형식이 되도록 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-128">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="b470e-129">*기준 형식은* 다른 모든 형식이 확장 될 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-129">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="b470e-130">이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식이 축소 될 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-130">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="b470e-131">이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-131">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="b470e-132">이 경우 `Option Strict` 가로 설정 되 면 `On` 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-132">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="b470e-133">예를 들어 문에 제공 된 식이 `Return` , 및 형식의 값을 포함 하는 경우 `Integer` `Long` `Double` 결과 배열은 형식입니다 `Double` .</span><span class="sxs-lookup"><span data-stu-id="b470e-133">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="b470e-134">및는 모두 `Integer` `Long` `Double` 및로만 확대 `Double` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-134">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="b470e-135">따라서 기준 형식은 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-135">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="b470e-136">자세한 내용은 [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b470e-136">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="b470e-137">한 줄 함수의 본문은 문이 아니라 값을 반환 하는 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-137">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="b470e-138">한 `Return` 줄 함수에는 문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-138">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="b470e-139">한 줄 함수에서 반환 되는 값은 함수 본문에 있는 식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-139">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="b470e-140">한 줄로 된 서브루틴의 본문은 한 줄로 된 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-140">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="b470e-141">한 줄 함수 및 서브루틴에는 또는 문이 포함 되지 않습니다 `End Function` `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="b470e-141">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="b470e-142">키워드를 사용 하 여 람다 식 매개 변수의 데이터 형식을 지정 `As` 하거나 매개 변수의 데이터 형식을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-142">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="b470e-143">모든 매개 변수에는 지정 된 데이터 형식이 있어야 합니다. 그렇지 않으면 모두 유추 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-143">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="b470e-144">`Optional` 및 `Paramarray` 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-144">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="b470e-145">제네릭 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-145">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="b470e-146">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="b470e-146">Async Lambdas</span></span>

<span data-ttu-id="b470e-147">[Async](../../../language-reference/modifiers/async.md) 및 [wait 연산자](../../../language-reference/operators/await-operator.md) 키워드를 사용 하 여 비동기 처리를 통합 하는 람다 식과 문을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-147">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../language-reference/modifiers/async.md) and [Await Operator](../../../language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="b470e-148">예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-148">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="b470e-149">[AddHandler 문에](../../../language-reference/statements/addhandler-statement.md)비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-149">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="b470e-150">이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-150">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="b470e-151">비동기 메서드를 만들고 사용 하는 방법에 대 한 자세한 내용은 [async 및 wait를 사용한 비동기 프로그래밍](../../concepts/async/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b470e-151">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="b470e-152">Context</span><span class="sxs-lookup"><span data-stu-id="b470e-152">Context</span></span>

<span data-ttu-id="b470e-153">람다 식은 컨텍스트를 정의 된 범위와 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-153">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="b470e-154">포함 하는 범위에 작성 된 코드와 동일한 액세스 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-154">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="b470e-155">여기에는 포함 하는 범위의 멤버 변수, 함수 및 sub, `Me` 및 매개 변수와 지역 변수에 대 한 액세스 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-155">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="b470e-156">포함 범위의 지역 변수 및 매개 변수에 대 한 액세스는 해당 범위의 수명 이상으로 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-156">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="b470e-157">람다 식을 참조 하는 대리자를 가비지 수집에 사용할 수 없는 경우 원래 환경의 변수에 대 한 액세스가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-157">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="b470e-158">다음 예제에서 변수 `target` 는 `makeTheGame` 람다 식이 정의 된 메서드인에서 로컬입니다 `playTheGame` .</span><span class="sxs-lookup"><span data-stu-id="b470e-158">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="b470e-159">에서에 할당 된 반환 된 람다 식은 `takeAGuess` `Main` 여전히 지역 변수에 액세스할 수 있습니다 `target` .</span><span class="sxs-lookup"><span data-stu-id="b470e-159">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="b470e-160">다음 예제에서는 중첩 된 람다 식의 광범위 한 액세스 권한을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-160">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="b470e-161">반환 된 람다 식이로에서 실행 될 `Main` 때 `aDel` 다음 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-161">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="b470e-162">클래스가 정의 된 클래스의 필드입니다. `aField`</span><span class="sxs-lookup"><span data-stu-id="b470e-162">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="b470e-163">정의 된 클래스의 속성: `aProp`</span><span class="sxs-lookup"><span data-stu-id="b470e-163">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="b470e-164">메서드가 정의 된 메서드의 매개 변수는 `functionWithNestedLambda` 다음과 같습니다. `level1`</span><span class="sxs-lookup"><span data-stu-id="b470e-164">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="b470e-165">의 지역 변수입니다 `functionWithNestedLambda` . `localVar`</span><span class="sxs-lookup"><span data-stu-id="b470e-165">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="b470e-166">중첩 된 람다 식의 매개 변수는 다음과 같습니다. `level2`</span><span class="sxs-lookup"><span data-stu-id="b470e-166">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="b470e-167">대리자 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="b470e-167">Converting to a Delegate Type</span></span>

<span data-ttu-id="b470e-168">람다 식을 호환 되는 대리자 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-168">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="b470e-169">호환성에 대 한 일반 요구 사항에 대 한 자세한 내용은 [완화 된 대리자 변환](../delegates/relaxed-delegate-conversion.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b470e-169">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="b470e-170">예를 들어 다음 코드 예제에서는를 또는 일치 하는 대리자 시그니처로 암시적으로 변환 하는 람다 식을 보여 줍니다 `Func(Of Integer, Boolean)` .</span><span class="sxs-lookup"><span data-stu-id="b470e-170">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="b470e-171">다음 코드 예제에서는를 또는 일치 하는 대리자 시그니처로 암시적으로 변환 하는 람다 식을 보여 줍니다 `Sub(Of Double, String, Double)` .</span><span class="sxs-lookup"><span data-stu-id="b470e-171">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="b470e-172">람다 식을 대리자에 할당 하거나이를 프로시저에 인수로 전달 하는 경우 매개 변수 이름을 지정할 수 있지만 해당 데이터 형식을 생략 하 여 대리자에서 형식을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-172">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="b470e-173">예제</span><span class="sxs-lookup"><span data-stu-id="b470e-173">Examples</span></span>

- <span data-ttu-id="b470e-174">다음 예제에서는 `True` nullable 값 형식 인수에 할당 된 값이 있는 경우를 반환 하 고, `False` 해당 값이 이면를 반환 하는 람다 식을 정의 합니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="b470e-174">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="b470e-175">다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 람다 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b470e-175">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="b470e-176">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b470e-176">See also</span></span>

- [<span data-ttu-id="b470e-177">절차</span><span class="sxs-lookup"><span data-stu-id="b470e-177">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b470e-178">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="b470e-178">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
- [<span data-ttu-id="b470e-179">대리자</span><span class="sxs-lookup"><span data-stu-id="b470e-179">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="b470e-180">Function 문</span><span class="sxs-lookup"><span data-stu-id="b470e-180">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="b470e-181">Sub 문</span><span class="sxs-lookup"><span data-stu-id="b470e-181">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="b470e-182">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="b470e-182">Nullable Value Types</span></span>](../data-types/nullable-value-types.md)
- [<span data-ttu-id="b470e-183">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="b470e-183">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="b470e-184">방법: 람다 식 만들기</span><span class="sxs-lookup"><span data-stu-id="b470e-184">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="b470e-185">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="b470e-185">Relaxed Delegate Conversion</span></span>](../delegates/relaxed-delegate-conversion.md)
