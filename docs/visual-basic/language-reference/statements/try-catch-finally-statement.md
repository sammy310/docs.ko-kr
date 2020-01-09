---
title: Try ... Catch ... Finally 문
description: Visual Basic Try/Catch/Finally 문을 사용 하 여 예외 처리를 사용 하는 방법을 알아봅니다.
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.openlocfilehash: bb6f17f7ce88caea0b9d30ec880194f2bb71c6a6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705771"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally 문(Visual Basic)

코드를 계속 실행 하면서 지정 된 코드 블록에서 발생할 수 있는 일부 또는 모든 오류를 처리 하는 방법을 제공 합니다.

## <a name="syntax"></a>구문

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a>구성 요소

|용어|정의|
|---|---|
|`tryStatements`|옵션. 오류가 발생할 수 있는 문입니다. 복합 문일 수 있습니다.|
|`Catch`|옵션. 여러 `Catch` 블록을 사용할 수 있습니다. `Try` 블록을 처리할 때 예외가 발생 하는 경우 각 `Catch` 문이 예외 `exception`를 처리 하는지 여부를 확인 하기 위해 텍스트 순서 대로 검사 되며 throw 된 예외를 나타냅니다.|
|`exception`|옵션. 임의의 변수 이름입니다. `exception`의 초기 값은 throw된 오류 값입니다. `Catch`와 함께 사용 되어 catch 된 오류를 지정 합니다. 생략 하는 경우 `Catch` 문은 예외를 catch 합니다.|
|`type`|옵션. 클래스 필터의 유형을 지정 합니다. `exception` 값이 `type` 또는 파생 형식으로 지정 된 형식인 경우 식별자는 예외 개체에 바인딩됩니다.|
|`When`|옵션. `When` 절을 사용 하는 `Catch` 문은 `expression`이 `True`로 계산 되는 경우에만 예외를 catch 합니다. `When` 절은 예외 형식을 확인 한 후에만 적용 되 고 `expression`는 예외를 나타내는 식별자를 참조할 수 있습니다.|
|`expression`|옵션. `Boolean`로 암시적으로 변환할 수 있어야 합니다. 제네릭 필터를 설명 하는 식입니다. 일반적으로 오류 번호로 필터링 하는 데 사용 됩니다. 오류가 발생 하는 상황을 지정 하기 위해 `When` 키워드와 함께 사용 됩니다.|
|`catchStatements`|옵션. 관련 된 `Try` 블록에서 발생 하는 오류를 처리 하는 문입니다. 복합 문일 수 있습니다.|
|`Exit Try`|옵션. `Try...Catch...Finally` 구조체에서 분리 되는 키워드입니다. `End Try` 문 바로 다음에 오는 코드를 사용 하 여 실행을 다시 시작 합니다. `Finally` 문은 계속 실행 됩니다. `Finally` 블록에서는 허용 되지 않습니다.|
|`Finally`|옵션. `Finally` 블록은 실행이 `Try...Catch` 문의 일부를 떠날 때 항상 실행 됩니다.|
|`finallyStatements`|옵션. 다른 모든 오류 처리가 발생 한 후 실행 되는 문입니다.|
|`End Try`|`Try...Catch...Finally` 구조체를 종료 합니다.|

## <a name="remarks"></a>주의

특정 코드 섹션 중 특정 예외가 발생할 것으로 생각 되는 경우 코드를 `Try` 블록에 배치 하 고 `Catch` 블록을 사용 하 여 컨트롤을 유지 하 고 예외가 발생 하면 예외를 처리 합니다.

`Try…Catch` 문은 `Try` 블록 뒤에 여러 가지 예외에 대 한 처리기를 지정 하는 하나 이상의 `Catch` 절로 구성 됩니다. `Try` 블록에서 예외가 throw 되 면 Visual Basic는 예외를 처리 하는 `Catch` 문을 찾습니다. 일치 하는 `Catch` 문이 없는 경우 Visual Basic는 현재 메서드를 호출한 메서드를 검사 하 여 호출 스택을 확인 합니다. `Catch` 블록을 찾을 수 없는 경우 Visual Basic는 처리 되지 않은 예외 메시지를 사용자에 게 표시 하 고 프로그램의 실행을 중지 합니다.

`Try…Catch` 문에서 둘 이상의 `Catch` 문을 사용할 수 있습니다. 이 작업을 수행 하는 경우 `Catch` 절의 순서는 순서 대로 검사 되기 때문에 중요 합니다. 더 구체적인 예외를 덜 구체적인 예외보다 먼저 catch합니다.

다음 `Catch` 문 조건은 가장 덜 구체적 이며 <xref:System.Exception> 클래스에서 파생 되는 모든 예외를 catch 합니다. 일반적으로 원하는 특정 예외를 모두 catch 한 후에는 일반적으로 이러한 변형 중 하나를 `Try...Catch...Finally` 구조체의 마지막 `Catch` 블록으로 사용 해야 합니다. 제어 흐름은 이러한 변형 중 하나를 따르는 `Catch` 블록에 도달할 수 없습니다.

- `type` `Exception`입니다. 예를 들면 `Catch ex As Exception`

- 문에 `exception` 변수가 없습니다 (예: `Catch`

`Try…Catch…Finally` 문이 다른 `Try` 블록에 중첩 된 경우 Visual Basic 먼저 가장 안쪽의 `Try` 블록에서 각 `Catch` 문을 검사 합니다. 일치 하는 `Catch` 문이 없는 경우 검색은 외부 `Try…Catch…Finally` 블록의 `Catch` 문으로 진행 됩니다.

`Try` 블록의 지역 변수는 별도의 블록 이므로 `Catch` 블록에서 사용할 수 없습니다. 둘 이상의 블록에서 변수를 사용 하려면 `Try...Catch...Finally` 구조체 외부에서 변수를 선언 합니다.

> [!TIP]
> `Try…Catch…Finally` 문은 IntelliSense 코드 조각으로 사용할 수 있습니다. 코드 조각 관리자에서 코드 패턴을 확장 합니다. **For Each, Try Catch, Property 등**, **오류 처리 (예외)** 를 차례로 클릭 합니다. 자세한 내용은 [Code Snippets](/visualstudio/ide/code-snippets)을 참조하세요.

## <a name="finally-block"></a>Finally 블록

`Try` 구조를 끝내기 전에 실행 해야 하는 문이 하나 이상 있는 경우 `Finally` 블록을 사용 합니다. 컨트롤은 `Try…Catch` 구조 외부로 전달 되기 직전에 `Finally` 블록으로 전달 됩니다. 이는 `Try` 구조 내에서 예외가 발생 하는 경우에도 마찬가지입니다.

`Finally` 블록은 예외가 있는 경우에도 실행 해야 하는 모든 코드를 실행 하는 데 유용 합니다. `Try...Catch` 블록이 종료 되는 방법에 관계 없이 컨트롤이 `Finally` 블록으로 전달 됩니다.

`Finally` 블록의 코드는 코드가 `Try` 또는 `Catch` 블록에서 `Return` 문을 발견 하는 경우에도 실행 됩니다. 제어는 다음과 같은 경우에 `Try` 또는 `Catch` 블록에서 해당 `Finally` 블록으로 전달 되지 않습니다.

- [End 문이](end-statement.md) `Try` 또는 `Catch` 블록에서 발견 되었습니다.

- <xref:System.StackOverflowException> `Try` 또는 `Catch` 블록에서 throw 됩니다.

`Finally` 블록으로 실행을 명시적으로 전송 하는 것은 유효 하지 않습니다. 예외를 제외 하 고는 `Finally` 블록 외부로의 실행 전송이 잘못 되었습니다.

`Try` 문에 `Catch` 블록이 하나 이상 포함 되어 있지 않으면 `Finally` 블록을 포함 해야 합니다.

> [!TIP]
> 특정 예외를 catch 하지 않아도 되는 경우 `Using` 문은 블록을 종료 하는 방법에 관계 없이 `Try…Finally` 블록 처럼 동작 하 고 리소스 삭제를 보장 합니다. 처리 되지 않은 예외가 있는 경우에도 마찬가지입니다. 자세한 내용은 [using 문](using-statement.md)을 참조하세요.

## <a name="exception-argument"></a>예외 인수

`Catch` 블록 `exception` 인수는 <xref:System.Exception> 클래스의 인스턴스이거나 `Exception` 클래스에서 파생 되는 클래스입니다. `Exception` 클래스 인스턴스는 `Try` 블록에서 발생 한 오류에 해당 합니다.

`Exception` 개체의 속성은 예외의 원인과 위치를 식별 하는 데 도움이 됩니다. 예를 들어 <xref:System.Exception.StackTrace%2A> 속성은 예외를 발생 시킨 호출 된 메서드를 나열 하 여 코드에서 오류가 발생 한 위치를 찾을 수 있도록 합니다. <xref:System.Exception.Message%2A>는 예외를 설명 하는 메시지를 반환 합니다. <xref:System.Exception.HelpLink%2A>는 연결 된 도움말 파일에 대 한 링크를 반환 합니다. <xref:System.Exception.InnerException%2A>는 현재 예외를 발생 시킨 `Exception` 개체를 반환 하거나, 원래 `Exception`없는 경우 `Nothing`을 반환 합니다.

## <a name="considerations-when-using-a-trycatch-statement"></a>Try 사용 시 고려 사항 ... Catch 문

`Try…Catch` 문을 사용 하 여 비정상적인 또는 예기치 않은 프로그램 이벤트의 발생을 신호로 알립니다. 이러한 이유는 다음과 같습니다.

- 런타임에 예외를 catch 하면 추가 오버 헤드가 발생 하며 예외를 방지 하기 위해 사전 검사 보다 속도가 느려질 수 있습니다.

- `Catch` 블록이 올바르게 처리 되지 않은 경우 예외가 사용자에 게 올바르게 보고 되지 않을 수 있습니다.

- 예외 처리는 프로그램을 더 복잡 하 게 만듭니다.

발생할 가능성이 있는 조건을 확인 하는 데 항상 `Try…Catch` 문이 필요 하지는 않습니다. 다음 예에서는 파일을 열기 전에 파일이 있는지 여부를 확인 합니다. 이렇게 하면 <xref:System.IO.File.OpenText%2A> 메서드에서 throw 된 예외를 catch 하는 필요성이 줄어듭니다.

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

`Catch` 블록의 코드에서 스레드로부터 안전한 로깅 또는 적절 한 메시지를 통해 사용자에 게 예외를 올바르게 보고할 수 있는지 확인 합니다. 그렇지 않으면 예외를 알 수 없는 상태로 유지할 수 있습니다.

## <a name="async-methods"></a>비동기 메서드

[비동기](../modifiers/async.md) 한정자를 사용 하 여 메서드를 표시 하는 경우 메서드에서 [wait](../operators/await-operator.md) 연산자를 사용할 수 있습니다. `Await` 연산자를 사용 하는 문은 대기 작업이 완료 될 때까지 메서드 실행을 일시 중단 합니다. 작업은 진행 중인 작업을 나타냅니다. `Await` 연산자와 연결 된 작업이 완료 되 면 동일한 메서드에서 실행이 다시 시작 됩니다. 자세한 내용은 [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)을 참조 하세요.

비동기 메서드에서 반환 되는 작업은 처리 되지 않은 예외로 인해 완료 되었음을 나타내는 오류가 발생 한 상태로 종료 될 수 있습니다. 작업은 취소 됨 상태로 종료 될 수도 있습니다 .이로 인해 wait 식에서 `OperationCanceledException` 발생 합니다. 두 가지 유형의 예외를 catch 하려면 작업과 연결 된 `Await` 식을 `Try` 블록에 놓고 `Catch` 블록에서 예외를 catch 합니다. 예제는이 항목의 뒷부분에 나와 있습니다.

여러 예외로 인해 오류가 발생 했기 때문에 작업이 오류 상태에 있을 수 있습니다. 예를 들어 작업은 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 호출의 결과일 수 있습니다. 이러한 작업을 기다릴 때 catch 된 예외는 예외 중 하나일 뿐 이며 catch 할 예외를 예측할 수 없습니다. 예제는이 항목의 뒷부분에 나와 있습니다.

`Await` 식은 `Catch` 블록 또는 `Finally` 블록 안에 있을 수 없습니다.

## <a name="iterators"></a>Iterators

반복기 함수 또는 `Get` 접근자는 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기는 [Yield](yield-statement.md) 문을 사용 하 여 컬렉션의 각 요소를 한 번에 하나씩 반환 합니다. For Each ...를 사용 하 여 반복기 함수를 호출 합니다. [ 다음 문](for-each-next-statement.md).

`Yield` 문은 `Try` 블록 안에 있을 수 있습니다. `Yield` 문을 포함 하는 `Try` 블록은 `Catch` 블록을 포함할 수 있으며 `Finally` 블록을 포함할 수 있습니다. 예제는 [반복기](../../programming-guide/concepts/iterators.md) 의 "Try 블록 Visual Basic" 섹션을 참조 하세요.

`Yield` 문은 `Catch` 블록 또는 `Finally` 블록 안에 있을 수 없습니다.

`For Each` 본문 (반복기 함수 외부)에서 예외를 throw 하는 경우 반복기 함수의 `Catch` 블록이 실행 되지 않지만 반복기 함수의 `Finally` 블록이 실행 됩니다. 반복기 함수 내의 `Catch` 블록은 반복기 함수 내에서 발생 하는 예외만 catch 합니다.

## <a name="partial-trust-situations"></a>부분 신뢰 상황

네트워크 공유에서 호스트 되는 응용 프로그램과 같은 부분 신뢰 상황에서 호출을 포함 하는 메서드를 호출 하기 전에 발생 하는 보안 예외는 `Try...Catch...Finally`에서 catch 하지 않습니다. 다음 예제를 서버 공유에 배치 하 고 여기에서 실행 하면 "System.web Exception: Request Failed" 오류가 발생 합니다. 보안 예외에 대 한 자세한 내용은 <xref:System.Security.SecurityException> 클래스를 참조 하세요.

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

이러한 부분 신뢰 상황에서는 `Process.Start` 문을 별도의 `Sub`에 배치 해야 합니다. `Sub`에 대 한 초기 호출이 실패 합니다. 이렇게 하면 `Process.Start`를 포함 하는 `Sub`이 시작 되 고 보안 예외가 생성 되기 전에 `Try...Catch`에서이를 catch 할 수 있습니다.

## <a name="examples"></a>예

### <a name="the-structure-of-trycatchfinally"></a>Try ... Catch ... 마지막으로

다음 예에서는 `Try...Catch...Finally` 문의 구조를 보여 줍니다.

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>Try 블록에서 호출 된 메서드에서 예외가 발생 했습니다.

다음 예제에서 `CreateException` 메서드는 `NullReferenceException`를 throw 합니다. 예외를 생성 하는 코드는 `Try` 블록에 없습니다. 따라서 `CreateException` 메서드는 예외를 처리 하지 않습니다. `CreateException` 메서드에 대 한 호출이 `Try` 블록에 있기 때문에 `RunSample` 메서드는 예외를 처리 합니다.

이 예제에는 몇 가지 유형의 예외에 대 한 `Catch` 문이 포함 되어 있으며 가장 일반적인 순서로 정렬 되어 있습니다.

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Catch When 문

다음 예에서는 `Catch When` 문을 사용 하 여 조건 식을 필터링 하는 방법을 보여 줍니다. 조건식이 `True`로 평가 되는 경우 `Catch` 블록의 코드가 실행 됩니다.

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>중첩 된 Try 문

다음 예제에는 `Try` 블록에 포함 된 `Try…Catch` 문이 있습니다. 내부 `Catch` 블록은 `InnerException` 속성이 원래 예외로 설정 된 예외를 throw 합니다. 외부 `Catch` 블록은 자체 예외 및 내부 예외를 보고 합니다.

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>비동기 메서드에 대 한 예외 처리

다음 예제에서는 비동기 메서드에 대한 예외 처리를 보여 줍니다. 비동기 작업에 적용 되는 예외를 catch 하기 위해 `Await` 식은 호출자의 `Try` 블록에 있으며 예외는 `Catch` 블록에서 catch 됩니다.

예제에서 `Throw New Exception` 줄의 주석 처리를 제거하여 예외 처리를 보여 줍니다. 예외는 `Catch` 블록에서 catch 되 고, 작업의 `IsFaulted` 속성은 `True`로 설정 되 고, 작업의 `Exception.InnerException` 속성은 예외로 설정 됩니다.

`Throw New OperationCancelledException` 줄의 주석 처리를 제거하여 비동기 프로세스를 취소할 수 있을 때 발생하는 동작을 보여 줍니다. 예외는 `Catch` 블록에서 catch 되 고 작업의 `IsCanceled` 속성은 `True`로 설정 됩니다. 그러나이 예제에 적용 되지 않는 일부 조건에서는 `IsFaulted`이 `True`으로 설정 되 고 `IsCanceled`이 `False`로 설정 됩니다.

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>비동기 메서드에서 여러 예외 처리

다음 예제에서는 여러 작업에서 여러 예외가 발생할 수 있는 경우 예외 처리를 보여 줍니다. `Try` 블록에는 반환 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 태스크에 대 한 `Await` 식이 있습니다. <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 적용 되는 세 가지 작업이 완료 되 면 작업이 완료 됩니다.

세 작업에서 각각 예외가 발생합니다. `Catch` 블록은 반환 `Task.WhenAll`는 작업의 `Exception.InnerExceptions` 속성에 있는 예외를 반복 합니다.

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>참조

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Exit 문](exit-statement.md)
- [On Error 문](on-error-statement.md)
- [코드 조각 사용에 대한 모범 사례](/visualstudio/ide/best-practices-for-using-code-snippets)
- [예외 처리](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw 문](throw-statement.md)
