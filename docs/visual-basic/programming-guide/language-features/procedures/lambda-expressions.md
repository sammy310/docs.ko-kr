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
ms.openlocfilehash: 54a9c0cf275a67c77748c32771c3c5dcbdb916d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406705"
---
# <a name="lambda-expressions-visual-basic"></a>람다 식(Visual Basic)

*람다 식은* 대리자가 유효한 모든 위치에서 사용할 수 있는 이름이 없는 함수 또는 서브루틴입니다. 람다 식은 함수나 서브루틴이 될 수 있으며 한 줄 또는 여러 줄을 사용할 수 있습니다. 현재 범위에서 람다 식으로 값을 전달할 수 있습니다.

> [!NOTE]
> `RemoveHandler`문은 예외입니다. 의 대리자 매개 변수에는 람다 식을 전달할 수 없습니다 `RemoveHandler` .

`Function` `Sub` 표준 함수 또는 서브루틴을 만들 때와 마찬가지로 또는 키워드를 사용 하 여 람다 식을 만들 수 있습니다. 그러나 람다 식이 문에 포함 됩니다.

다음 예제는 인수를 증가 시키고 값을 반환 하는 람다 식입니다. 이 예제에서는 함수에 대 한 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

다음 예제는 콘솔에 값을 기록 하는 람다 식입니다. 이 예제에서는 서브루틴에 대 한 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

앞의 예제에서 람다 식은 변수 이름에 할당 됩니다. 변수를 참조할 때마다 람다 식을 호출 합니다. 다음 예제와 같이 람다 식을 동시에 선언 하 고 호출할 수도 있습니다.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

다음 예제와 같이 람다 식을 함수 호출의 값으로 반환 하거나 (이 항목의 뒷부분에 나오는 [컨텍스트](#context) 섹션의 예제에 표시 된 것 처럼), 대리자 형식을 사용 하는 매개 변수에 인수로 전달할 수 있습니다.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>람다 식 구문

람다 식의 구문은 표준 함수 또는 서브루틴의 구문과 유사 합니다. 차이점은 다음과 같습니다.

- 람다 식에 이름이 없습니다.

- 람다 식에는 또는와 같은 한정자를 사용할 수 없습니다 `Overloads` `Overrides` .

- 한 줄 람다 함수는 절을 사용 `As` 하 여 반환 형식을 지정 하지 않습니다. 대신 람다 식의 본문이 계산 되는 값에서 형식이 유추 됩니다. 예를 들어, 람다 식의 본문이 이면 `cust.City = "London"` 반환 형식은 `Boolean` 입니다.

- 여러 줄 람다 함수에서 절을 사용 하 여 반환 형식을 지정 `As` 하거나 `As` 반환 형식이 유추 되도록 절을 생략할 수 있습니다. `As`여러 줄 람다 함수에 대해 절이 생략 된 경우 반환 형식은 `Return` 여러 줄 람다 함수에 있는 모든 문의 기준 형식이 되도록 유추 됩니다. *기준 형식은* 다른 모든 형식이 확장 될 수 있는 고유 형식입니다. 이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식이 축소 될 수 있는 고유 형식입니다. 이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다. 이 경우 `Option Strict` 가로 설정 되 면 `On` 컴파일러 오류가 발생 합니다.

     예를 들어 문에 제공 된 식이 `Return` , 및 형식의 값을 포함 하는 경우 `Integer` `Long` `Double` 결과 배열은 형식입니다 `Double` . 및는 모두 `Integer` `Long` `Double` 및로만 확대 `Double` 됩니다. 따라서 기준 형식은 `Double` 입니다. 자세한 내용은 [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)을 참조하세요.

- 한 줄 함수의 본문은 문이 아니라 값을 반환 하는 식 이어야 합니다. 한 `Return` 줄 함수에는 문이 없습니다. 한 줄 함수에서 반환 되는 값은 함수 본문에 있는 식의 값입니다.

- 한 줄로 된 서브루틴의 본문은 한 줄로 된 문 이어야 합니다.

- 한 줄 함수 및 서브루틴에는 또는 문이 포함 되지 않습니다 `End Function` `End Sub` .

- 키워드를 사용 하 여 람다 식 매개 변수의 데이터 형식을 지정 `As` 하거나 매개 변수의 데이터 형식을 유추할 수 있습니다. 모든 매개 변수에는 지정 된 데이터 형식이 있어야 합니다. 그렇지 않으면 모두 유추 해야 합니다.

- `Optional`및 `Paramarray` 매개 변수는 허용 되지 않습니다.

- 제네릭 매개 변수는 허용 되지 않습니다.

## <a name="async-lambdas"></a>비동기 람다

[Async](../../../language-reference/modifiers/async.md) 및 [wait 연산자](../../../language-reference/operators/await-operator.md) 키워드를 사용 하 여 비동기 처리를 통합 하는 람다 식과 문을 쉽게 만들 수 있습니다. 예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.

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

[AddHandler 문에](../../../language-reference/statements/addhandler-statement.md)비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수 있습니다. 이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.

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

비동기 메서드를 만들고 사용 하는 방법에 대 한 자세한 내용은 [async 및 wait를 사용한 비동기 프로그래밍](../../concepts/async/index.md)을 참조 하세요.

## <a name="context"></a>Context

람다 식은 컨텍스트를 정의 된 범위와 공유 합니다. 포함 하는 범위에 작성 된 코드와 동일한 액세스 권한을 가집니다. 여기에는 포함 하는 범위의 멤버 변수, 함수 및 sub, `Me` 및 매개 변수와 지역 변수에 대 한 액세스 권한이 포함 됩니다.

포함 범위의 지역 변수 및 매개 변수에 대 한 액세스는 해당 범위의 수명 이상으로 확장 될 수 있습니다. 람다 식을 참조 하는 대리자를 가비지 수집에 사용할 수 없는 경우 원래 환경의 변수에 대 한 액세스가 유지 됩니다. 다음 예제에서 변수 `target` 는 `makeTheGame` 람다 식이 정의 된 메서드인에서 로컬입니다 `playTheGame` . 에서에 할당 된 반환 된 람다 식은 `takeAGuess` `Main` 여전히 지역 변수에 액세스할 수 있습니다 `target` .

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

다음 예제에서는 중첩 된 람다 식의 광범위 한 액세스 권한을 보여 줍니다. 반환 된 람다 식이로에서 실행 될 `Main` 때 `aDel` 다음 요소에 액세스 합니다.

- 클래스가 정의 된 클래스의 필드입니다.`aField`

- 정의 된 클래스의 속성:`aProp`

- 메서드가 정의 된 메서드의 매개 변수는 `functionWithNestedLambda` 다음과 같습니다.`level1`

- 의 지역 변수입니다 `functionWithNestedLambda` .`localVar`

- 중첩 된 람다 식의 매개 변수는 다음과 같습니다.`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>대리자 형식으로 변환

람다 식을 호환 되는 대리자 형식으로 암시적으로 변환할 수 있습니다. 호환성에 대 한 일반 요구 사항에 대 한 자세한 내용은 [완화 된 대리자 변환](../delegates/relaxed-delegate-conversion.md)을 참조 하세요. 예를 들어 다음 코드 예제에서는를 또는 일치 하는 대리자 시그니처로 암시적으로 변환 하는 람다 식을 보여 줍니다 `Func(Of Integer, Boolean)` .

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

다음 코드 예제에서는를 또는 일치 하는 대리자 시그니처로 암시적으로 변환 하는 람다 식을 보여 줍니다 `Sub(Of Double, String, Double)` .

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

람다 식을 대리자에 할당 하거나이를 프로시저에 인수로 전달 하는 경우 매개 변수 이름을 지정할 수 있지만 해당 데이터 형식을 생략 하 여 대리자에서 형식을 가져올 수 있습니다.

## <a name="examples"></a>예제

- 다음 예제에서는 `True` nullable 값 형식 인수에 할당 된 값이 있는 경우를 반환 하 고, `False` 해당 값이 이면를 반환 하는 람다 식을 정의 합니다 `Nothing` .

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- 다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 람다 식을 정의 합니다.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [Visual Basic의 LINQ 소개](../linq/introduction-to-linq.md)
- [대리자](../delegates/index.md)
- [Function 문](../../../language-reference/statements/function-statement.md)
- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [Nullable 값 형식](../data-types/nullable-value-types.md)
- [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [방법: 람다 식 만들기](./how-to-create-a-lambda-expression.md)
- [완화된 대리자 변환](../delegates/relaxed-delegate-conversion.md)
