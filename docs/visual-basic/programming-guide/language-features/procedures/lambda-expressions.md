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
# <a name="lambda-expressions-visual-basic"></a>람다 식(Visual Basic)

*람다 식은* 대리자가 유효한 모든 곳에서 사용할 수 있는 이름이 없는 함수 또는 서브루틴입니다. Lambda 표현식은 함수 또는 서브루틴일 수 있으며 한 줄 또는 다중 줄이 될 수 있습니다. 현재 범위에서 람다 식으로 값을 전달할 수 있습니다.

> [!NOTE]
> 문은 `RemoveHandler` 예외입니다. `RemoveHandler`의 대리자 매개 변수에 대해 람다 식을 전달할 수 없습니다.

표준 함수 또는 서브루틴을 `Function` 만드는 `Sub` 것처럼 또는 키워드를 사용하여 lambda 식을 만듭니다. 그러나 람다 식은 문에 포함됩니다.

다음 예제는 인수를 증분하고 값을 반환하는 lambda 식입니다. 이 예제에서는 함수에 대한 단일 줄 람다 식 구문과 다중 줄 람다 식 구문을 모두 보여 주며 있습니다.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

다음 예제는 콘솔에 값을 쓰는 람다 식입니다. 이 예제에서는 서브루틴에 대한 단일 줄 람다 식 구문을 모두 보여 주며 다중 줄 람다 식 구문을 모두 보여 주며, 이 두 가지를 모두 보여 주며, 이 두 가지를 보여 주며, 이는 서브루틴에 대한 단일 줄 람다 식 구문을 모두 보여 주며, 이 두 가지를 모두 보여

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

이전 예제에서는 람다 식이 변수 이름에 할당됩니다. 변수를 참조할 때마다 lambda 식을 호출합니다. 다음 예제와 같이 람다 식을 동시에 선언하고 호출할 수도 있습니다.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

람다 식은 함수 호출의 값으로 반환되거나(이 항목의 컨텍스트 [섹션의](#context) 예제에 나와 있음) 다음 예제와 같이 대리자 형식을 사용하는 매개 변수에 인수로 전달될 수 있습니다.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>람다 식 구문

람다 식의 구문은 표준 함수 또는 서브루틴의 구문과 유사합니다. 차이점은 다음과 같습니다.

- 람다 식에는 이름이 없습니다.

- Lambda 식에는 또는 `Overloads` `Overrides`와 같은 수정자를 가질 수 없습니다.

- 단일 줄 람다 함수는 반환 `As` 형식을 지정하는 절을 사용하지 않습니다. 대신 형식은 lambda 식의 본문이 평가하는 값에서 유추됩니다. 예를 들어 lambda 식의 본문이 `cust.City = "London"`있는 경우 `Boolean`반환 형식은 입니다.

- 다중 줄 람다 함수에서 `As` 절을 사용하여 return 형식을 지정하거나 반환 형식이 유추되도록 `As` 절을 생략할 수 있습니다. 다중 `As` 줄 람다 함수에 대한 절을 생략하면 반환 형식은 다중 줄 람다 `Return` 함수의 모든 문에서 지배적인 유형으로 유추됩니다. *지배적인 형식은* 다른 모든 형식이 확장될 수 있는 고유한 형식입니다. 이 고유 형식을 확인할 수 없는 경우 주요 형식은 배열의 다른 모든 형식이 좁힐 수 있는 고유 형식입니다. 이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다. 이 경우 `Option Strict` 컴파일러 오류가 `On`발생합니다.

     예를 `Return` 들어 문에 제공된 식에 형식 `Integer`및 `Long` `Double`의 값이 포함된 경우 결과 `Double`배열은 형식입니다. 둘 `Integer` `Long` 다로 `Double` 확대되고 `Double`만 . 따라서 기준 형식은 `Double` 입니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.

- 한 줄 함수의 본문은 문이 아닌 값을 반환하는 식이어야 합니다. 한 줄 `Return` 함수에 대한 문이 없습니다. 한 줄 함수에서 반환되는 값은 함수 본문에 있는 식의 값입니다.

- 한 줄 서브루틴의 본문은 한 줄 문이어야 합니다.

- 단일 줄 함수 및 서브루틴에는 `End Function` or `End Sub` 문이 포함되지 않습니다.

- `As` 키워드를 사용하여 람다 식 매개 변수의 데이터 형식을 지정하거나 매개 변수의 데이터 형식을 유추할 수 있습니다. 모든 매개 변수에는 지정된 데이터 형식이 있어야 하거나 모두 유추해야 합니다.

- `Optional`매개 `Paramarray` 변수는 허용되지 않습니다.

- 제네릭 매개 변수는 허용되지 않습니다.

## <a name="async-lambdas"></a>비동기 람다

[Async](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드를 사용하여 비동기 처리를 통합하는 lambda 식 및 문을 쉽게 만들 수 있습니다. 예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.

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

[AddHandler 문에서](../../../../visual-basic/language-reference/statements/addhandler-statement.md)비동기 람다를 사용하여 동일한 이벤트 처리기를 추가할 수 있습니다. 이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.

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

비동기 메서드를 만들고 사용하는 방법에 대한 자세한 내용은 [비동기 프로그래밍 및 Await를](../../../../visual-basic/programming-guide/concepts/async/index.md)참조하십시오.

## <a name="context"></a>Context

lambda 식은 해당 컨텍스트를 정의된 범위와 공유합니다. 포함 범위에 기록된 코드와 동일한 액세스 권한을 가짐입니다. 여기에는 멤버 변수, 함수 및 subs, `Me`포함된 범위의 매개 변수 및 로컬 변수에 대한 액세스가 포함됩니다.

포함 범위의 로컬 변수 및 매개 변수에 대한 액세스는 해당 범위의 수명 을 초과하여 확장될 수 있습니다. lambda 식을 참조하는 대리자가 가비지 수집에 사용할 수 없는 한 원래 환경의 변수에 대한 액세스는 유지됩니다. 다음 예제에서 변수는 `target` lambda 식이 `makeTheGame` `playTheGame` 정의 되는 메서드를 로컬로 합니다. 에 할당된 반환된 lambda 식은 여전히 지역 변수에 `target`액세스할 수 있습니다. `Main` `takeAGuess`

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

다음 예제에서는 중첩된 lambda 식의 광범위한 액세스 권한을 보여 줍니다. 반환된 lambda 식이 에서 `Main` `aDel`실행되면 다음 요소에 액세스합니다.

- 정의된 클래스의 필드:`aField`

- 정의된 클래스의 속성:`aProp`

- 메서드가 정의되는 매개 `functionWithNestedLambda`변수:`level1`

- 다음과 같은 `functionWithNestedLambda`로컬 변수가 있습니다.`localVar`

- 중첩되는 람다 식의 매개 변수:`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>대리자 유형으로 변환

람다 식은 호환되는 대리자 유형으로 암시적으로 변환할 수 있습니다. 호환성에 대한 일반적인 요구 사항에 대한 자세한 내용은 [완화된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오. 예를 들어 다음 코드 예제에서는 암시적으로 `Func(Of Integer, Boolean)` 변환하는 lambda 식 또는 일치하는 대리자 서명을 보여 주며 있습니다.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

다음 코드 예제에서는 암시적으로 변환하거나 일치하는 대리자 시그니처를 `Sub(Of Double, String, Double)` 포함하는 lambda 식을 보여 주습니다.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

lambda 식을 대리자에게 할당하거나 프로시저에 인수로 전달할 때 매개 변수 이름을 지정하지만 해당 데이터 형식을 생략하여 대리자에서 형식을 사용할 수 있습니다.

## <a name="examples"></a>예

- 다음 예제에서는 nullable 값 형식 `True` 인수에 할당된 값이 있고 `False` 해당 값이 .인 `Nothing`경우 반환하는 lambda 식을 정의합니다.

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- 다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 lambda 식을 정의 합니다.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>참조

- [절차](./index.md)
- [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Nullable 값 형식](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [방법: 람다 식 만들기](./how-to-create-a-lambda-expression.md)
- [완화된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
