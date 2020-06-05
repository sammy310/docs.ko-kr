---
title: Function 문
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404630"
---
# <a name="function-statement-visual-basic"></a>Function 문(Visual Basic)

프로시저를 정의 하는 이름, 매개 변수 및 코드를 선언 `Function` 합니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>부분

- `attributelist`

  선택 사항입니다. [특성 목록](attribute-list.md)을 참조 하십시오.

- `accessmodifier`

  선택 사항입니다. 다음 중 하나일 수 있습니다.

  - [공용](../modifiers/public.md)

  - [보호](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [프라이빗](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [개인 보호](../modifiers/private-protected.md)

  [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.

- `proceduremodifiers`

  선택 사항입니다. 다음 중 하나일 수 있습니다.

  - [오버로드](../modifiers/overloads.md)

  - [재정의](../modifiers/overrides.md)

  - [Overrides](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [New](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  선택 사항입니다. [공유](../modifiers/shared.md)를 참조 하세요.

- `Shadows`

  선택 사항입니다. [그림자](../modifiers/shadows.md)를 참조 하세요.

- `Async`

  선택 사항입니다. [Async](../modifiers/async.md)를 참조 하세요.

- `Iterator`

  선택 사항입니다. [반복기](../modifiers/iterator.md)를 참조 하세요.

- `name`

  필수 요소. 프로시저의 이름입니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.

- `typeparamlist`

  선택 사항입니다. 제네릭 프로시저에 대 한 형식 매개 변수 목록입니다. [형식 목록](type-list.md)을 참조 하십시오.

- `parameterlist`

  선택 사항입니다. 이 프로시저의 매개 변수를 나타내는 지역 변수 이름 목록입니다. [매개 변수 목록](parameter-list.md)을 참조 하세요.

- `returntype`

  필요한 경우 `Option Strict` 는 `On`합니다. 이 프로시저에서 반환 하는 값의 데이터 형식입니다.

- `Implements`

  선택 사항입니다. 이 프로시저에서 하나 이상의 `Function` 프로시저를 구현 하 고 각각이 프로시저의 포함 하는 클래스 또는 구조체에 의해 구현 된 인터페이스에 정의 됨을 나타냅니다. [Implements 문](implements-statement.md)을 참조 하세요.

- `implementslist`

  `Implements`가 제공된 경우 필수입니다. 구현할 `Function` 프로시저 목록입니다.

  `implementedprocedure [ , implementedprocedure ... ]`

  각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.

  `interface.definedname`

  |부분|Description|
  |---|---|
  |`interface`|필수 요소. 이 프로시저에 포함 된 클래스 또는 구조체에 의해 구현 된 인터페이스의 이름입니다.|
  |`definedname`|필수 요소. 프로시저가 `interface`에 정의되는 이름입니다.|

- `Handles`

  선택 사항입니다. 이 프로시저가 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다. [핸들](handles-clause.md)을 참조 하세요.

- `eventlist`

  `Handles`가 제공된 경우 필수입니다. 이 프로시저가 처리 하는 이벤트 목록입니다.

  `eventspecifier [ , eventspecifier ... ]`

  각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.

  `eventvariable.event`

  |부분|Description|
  |---|---|
  |`eventvariable`|필수 요소. 이벤트를 발생 시키는 클래스 또는 구조체의 데이터 형식으로 선언 된 개체 변수입니다.|
  |`event`|필수 요소. 이 프로시저가 처리 하는 이벤트의 이름입니다.|

- `statements`

  선택 사항입니다. 이 프로시저 내에서 실행할 문 블록입니다.

- `End Function`

  이 프로시저의 정의를 종료 합니다.

## <a name="remarks"></a>설명

모든 실행 코드는 프로시저 내에 있어야 합니다. 각 프로시저는 클래스, 구조체 또는 포함 하는 클래스, 구조체 또는 모듈 이라고 하는 모듈 내에서 선언 됩니다.

호출 코드에 값을 반환 하려면 프로시저를 사용 하 `Function` 고, 그렇지 않은 경우 프로시저를 사용 `Sub` 합니다.

## <a name="defining-a-function"></a>함수 정의

`Function`모듈 수준 에서만 프로시저를 정의할 수 있습니다. 따라서 함수의 선언 컨텍스트는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

`Function`프로시저는 기본적으로 공용 액세스입니다. 액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.

프로시저는 `Function` 프로시저에서 반환 하는 값의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다. 매개 변수를 지정 하지 않으면 `returntype` 프로시저가 반환 `Object` 됩니다.

이 프로시저에서 키워드를 사용 하는 경우 `Implements` 포함 하는 클래스 또는 구조체에도 `Implements` 해당 또는 문 바로 다음에 오는 문이 있어야 합니다 `Class` `Structure` . `Implements`문에는에 지정 된 각 인터페이스가 포함 되어야 합니다 `implementslist` . 그러나 인터페이스에서 (의)를 정의 하는 이름은 `Function` `definedname` 이 프로시저의 이름과 일치할 필요가 없습니다 (에서 `name` ).

> [!NOTE]
> 람다 식을 사용 하 여 함수 식을 인라인으로 정의할 수 있습니다. 자세한 내용은 [함수 식](../operators/function-expression.md) 및 [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)을 참조 하세요.

## <a name="returning-from-a-function"></a>함수에서 반환

`Function`프로시저가 호출 코드에 반환 되 면 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다.

함수에서 값을 반환 하려면 함수 이름에 값을 할당 하거나 문에 포함할 수 있습니다 `Return` .

`Return`문은 다음 예제와 같이 반환 값을 동시에 할당 하 고 함수를 종료 합니다.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

다음 예에서는 함수 이름에 반환 값을 할당 한 `myFunction` 다음 문을 사용 하 여를 `Exit Function` 반환 합니다.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

`Exit Function`및 `Return` 문은 프로시저에서 즉각적인 종료를 발생 시킵니다 `Function` . 프로시저의 모든 위치에는 개수와 `Exit Function` `Return` 문이 모두 표시 될 수 있으며 `Exit Function` 문과 문을 혼합할 수 있습니다 `Return` .

`Exit Function`에 값을 할당 하지 않고를 사용 하는 경우 `name` 프로시저는에 지정 된 데이터 형식에 대 한 기본값을 반환 합니다 `returntype` . 을 `returntype` 지정 하지 않으면이 프로시저는 `Nothing` 에 대 한 기본값인을 반환 합니다 `Object` .

## <a name="calling-a-function"></a>함수 호출

프로시저 `Function` 이름을 사용 하 여 프로시저를 호출한 다음 식에서 괄호 안의 인수 목록을 사용 합니다. 인수를 제공 하지 않는 경우에만 괄호를 생략할 수 있습니다. 그러나 항상 괄호를 포함 하는 경우 코드를 더 쉽게 읽을 수 있습니다.

`Function`, 또는와 같은 라이브러리 함수를 호출 하는 것과 동일한 방식으로 프로시저를 호출 합니다 `Sqrt` `Cos` `ChrW` .

키워드를 사용 하 여 함수를 호출할 수도 있습니다 `Call` . 이 경우 반환 값은 무시 됩니다. `Call`대부분의 경우 키워드를 사용 하지 않는 것이 좋습니다. 자세한 내용은 [Call 문](call-statement.md)을 참조 하세요.

때로는 산술 식을 다시 정렬 하 여 내부 효율성을 높이는 Visual Basic. `Function`이러한 이유로 함수에서 동일한 식의 변수 값을 변경 하는 경우에는 산술 식에 프로시저를 사용 하지 않아야 합니다.

## <a name="async-functions"></a>비동기 함수

비동기 *기능을* 사용 하면 명시적 콜백을 사용 하거나 여러 함수 또는 람다 식에서 수동으로 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.

[비동기](../modifiers/async.md) 한정자를 사용 하 여 함수를 표시 하는 경우 함수에서 [wait](../operators/await-operator.md) 연산자를 사용할 수 있습니다. 제어가 `Await` 함수에서 식에 도달 하면 `Async` 제어가 호출자에 게 반환 되 고 대기 작업이 완료 될 때까지 함수의 진행률이 일시 중단 됩니다. 작업이 완료 되 면 함수에서 실행을 다시 시작할 수 있습니다.

> [!NOTE]
> `Async`프로시저는 아직 완료 되지 않은 첫 번째 대기 개체를 발견 하거나 프로시저 끝에 도달할 때마다 호출자에 게 반환 `Async` 됩니다.

`Async`함수는 또는의 반환 형식을 사용할 수 <xref:System.Threading.Tasks.Task%601> 있습니다 <xref:System.Threading.Tasks.Task> . `Async`반환 형식이 인 함수의 예는 <xref:System.Threading.Tasks.Task%601> 다음과 같습니다.

`Async`함수는 [ByRef](../modifiers/byref.md) 매개 변수를 선언할 수 없습니다.

[하위 문은](sub-statement.md) 한정자로 표시 될 수도 있습니다 `Async` . 이는 주로 값을 반환할 수 없는 이벤트 처리기에 사용 됩니다. 프로시저는 `Async` `Sub` 대기 수 없으며 프로시저 호출자는 `Async` `Sub` 프로시저에서 throw 된 예외를 catch 할 수 없습니다 `Sub` .

함수에 대 한 자세한 내용은 `Async` [Async 및 wait를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../programming-guide/concepts/async/control-flow-in-async-programs.md)및 [비동기 반환 형식](../../programming-guide/concepts/async/async-return-types.md)을 참조 하세요.

## <a name="iterator-functions"></a>반복기 함수

*반복기* 함수는 목록 또는 배열과 같은 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기 함수는 [Yield](yield-statement.md) 문을 사용 하 여 각 요소를 한 번에 하나씩 반환 합니다. [Yield](yield-statement.md) 문에 도달 하면 코드의 현재 위치가 기억 됩니다. 다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.

For Each ...를 사용 하 여 클라이언트 코드에서 반복기를 호출 합니다. [ 다음](for-each-next-statement.md) 문.

반복기 함수의 반환 형식은,, 또는 일 수 <xref:System.Collections.IEnumerable> 있습니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.IEnumerator> <xref:System.Collections.Generic.IEnumerator%601> .

자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 문을 사용 하 여 `Function` 프로시저 본문을 구성 하는 이름, 매개 변수 및 코드를 선언 합니다 `Function` . `ParamArray`한정자를 사용 하면 함수에서 다양 한 수의 인수를 사용할 수 있습니다.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>예제

다음 예제에서는 앞의 예제에서 선언한 함수를 호출 합니다.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>예제

다음 예제에서 `DelayAsync` 는 `Async` `Function` 반환 형식이 인입니다 <xref:System.Threading.Tasks.Task%601> . `DelayAsync` 에는 정수를 반환하는 `Return` 문이 포함됩니다. 따라서의 함수 선언에는 `DelayAsync` 의 반환 형식이 있어야 `Task(Of Integer)` 합니다. 반환 형식이 이므로 `Task(Of Integer)` `Await` 의 식 계산에서 정수를 생성 합니다 `DoSomethingAsync` . 이에 대 한 설명은 다음과 같습니다 `Dim result As Integer = Await delayTask` .

프로시저는 `startButton_Click` 프로시저의 예입니다 `Async Sub` . 는 함수 이기 때문에 `DoSomethingAsync` `Async` 에 대 한 호출에 대 한 작업은 `DoSomethingAsync` 다음 문과 같이 대기 되어야 합니다 `Await DoSomethingAsync()` .. `startButton_Click` `Sub` 프로시저에 `Async` 식이 있으므로 한정자를 사용 하 여 프로시저를 정의 해야 합니다 `Await` .

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>참고 항목

- [Sub 문](sub-statement.md)
- [함수 프로시저](../../programming-guide/language-features/procedures/function-procedures.md)
- [매개 변수 목록](parameter-list.md)
- [Dim 문](dim-statement.md)
- [Call 문](call-statement.md)
- [으로](of-clause.md)
- [매개 변수 배열](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [방법: 제네릭 클래스 사용](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [프로시저 문제 해결](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [함수 식](../operators/function-expression.md)
