---
title: Sub 문
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404176"
---
# <a name="sub-statement-visual-basic"></a>Sub 문(Visual Basic)

프로시저를 정의 하는 이름, 매개 변수 및 코드를 선언 `Sub` 합니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>부분

- `attributelist`

  선택 사항입니다. [특성 목록](attribute-list.md)을 참조 하십시오.

- `Partial`

  선택 사항입니다. 부분 메서드 정의를 나타냅니다. [부분 메서드](../../programming-guide/language-features/procedures/partial-methods.md)를 참조 하세요.

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

- `name`

  필수 요소. 프로시저의 이름입니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요. 클래스에 대 한 생성자 프로시저를 만들려면 프로시저의 이름을 키워드로 설정 합니다 `Sub` `New` . 자세한 내용은 [개체 수명: 개체가 만들어지고 소멸 되는 방법](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)을 참조 하세요.

- `typeparamlist`

  선택 사항입니다. 제네릭 프로시저에 대 한 형식 매개 변수 목록입니다. [형식 목록](type-list.md)을 참조 하십시오.

- `parameterlist`

  선택 사항입니다. 이 프로시저의 매개 변수를 나타내는 지역 변수 이름 목록입니다. [매개 변수 목록](parameter-list.md)을 참조 하세요.

- `Implements`

  선택 사항입니다. 이 프로시저에서 하나 이상의 `Sub` 프로시저를 구현 하 고 각각이 프로시저의 포함 하는 클래스 또는 구조체에 의해 구현 된 인터페이스에 정의 됨을 나타냅니다. [Implements 문](implements-statement.md)을 참조 하세요.

- `implementslist`

  `Implements`가 제공된 경우 필수입니다. 구현할 `Sub` 프로시저 목록입니다.

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

- `End Sub`

  이 프로시저의 정의를 종료 합니다.

## <a name="remarks"></a>설명

모든 실행 코드는 프로시저 내에 있어야 합니다. `Sub`호출 코드에 값을 반환 하지 않으려는 경우 프로시저를 사용 합니다. `Function`값을 반환 하려는 경우 프로시저를 사용 합니다.

## <a name="defining-a-sub-procedure"></a>Sub 프로시저 정의

`Sub`모듈 수준 에서만 프로시저를 정의할 수 있습니다. 따라서 sub 프로시저의 선언 컨텍스트는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

`Sub`프로시저는 기본적으로 공용 액세스입니다. 액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.

프로시저에서 키워드를 사용 하는 경우 `Implements` 포함 하는 클래스 또는 구조체에는 `Implements` 또는 문 바로 다음에 오는 문이 있어야 합니다 `Class` `Structure` . `Implements`문에는에 지정 된 각 인터페이스가 포함 되어야 합니다 `implementslist` . 그러나 인터페이스에서 `Sub` (의)를 정의 하는 이름은 `definedname` 이 프로시저 (에서)의 이름과 일치할 필요가 없습니다 `name` .

## <a name="returning-from-a-sub-procedure"></a>Sub 프로시저에서 반환

프로시저에서 `Sub` 호출 코드로 반환 되 면 문을 호출한 문 뒤의 문을 사용 하 여 실행이 계속 됩니다.

다음 예에서는 프로시저에서 반환 하는 방법을 보여 줍니다 `Sub` .

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

`Exit Sub`및 `Return` 문은 프로시저에서 즉각적인 종료를 발생 시킵니다 `Sub` . 프로시저의 모든 위치에는 개수와 `Exit Sub` `Return` 문이 모두 표시 될 수 있으며 `Exit Sub` 문과 문을 혼합할 수 있습니다 `Return` .

## <a name="calling-a-sub-procedure"></a>Sub 프로시저 호출

`Sub`문에 프로시저 이름을 사용 하 여 프로시저를 호출한 다음 해당 이름을 괄호 안의 인수 목록에 따라 호출 합니다. 인수를 제공 하지 않는 경우에만 괄호를 생략할 수 있습니다. 그러나 항상 괄호를 포함 하는 경우 코드를 더 쉽게 읽을 수 있습니다.

`Sub`프로시저와 프로시저는 `Function` 매개 변수를 포함 하 고 일련의 문을 수행할 수 있습니다. 그러나 프로시저는 `Function` 값을 반환 하며 `Sub` 프로시저는 그렇지 않습니다. 따라서 식에는 프로시저를 사용할 수 없습니다 `Sub` .

프로시저를 호출할 때 키워드를 사용할 수 있지만 대부분의 경우에는 키워드를 사용 `Call` `Sub` 하지 않는 것이 좋습니다. 자세한 내용은 [Call 문](call-statement.md)을 참조 하세요.

때로는 산술 식을 다시 정렬 하 여 내부 효율성을 높이는 Visual Basic. 이러한 이유로 인수 목록에 다른 프로시저를 호출 하는 식이 포함 된 경우 해당 식이 특정 순서로 호출 된다고 가정 하면 안 됩니다.

## <a name="async-sub-procedures"></a>비동기 Sub 프로시저

비동기 기능을 사용 하면 명시적 콜백을 사용 하거나 여러 함수 또는 람다 식에서 수동으로 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.

[비동기](../modifiers/async.md) 한정자를 사용 하 여 프로시저를 표시 하는 경우 프로시저에서 [wait](../operators/await-operator.md) 연산자를 사용할 수 있습니다. 제어가 `Await` 프로시저에서 식에 도달 하면 `Async` 제어가 호출자에 게 반환 되 고 대기 작업이 완료 될 때까지 프로시저의 진행률이 일시 중단 됩니다. 작업이 완료 되 면 프로시저에서 실행을 다시 시작할 수 있습니다.

> [!NOTE]
> `Async`아직 완료 되지 않은 첫 번째 대기 개체가 발생 하거나 프로시저 끝에 `Async` 도달 하는 경우 (어느 쪽이 든 먼저 발생 하는 경우) 프로시저가 호출자에 게 반환 됩니다.

한정자를 사용 하 여 [함수 문을](function-statement.md) 표시할 수도 있습니다 `Async` . `Async`함수는 또는의 반환 형식을 사용할 수 <xref:System.Threading.Tasks.Task%601> 있습니다 <xref:System.Threading.Tasks.Task> . 이 항목의 뒷부분에 나오는 예제에서는 `Async` 반환 형식이 인 함수를 보여 줍니다 <xref:System.Threading.Tasks.Task%601> .

`Async``Sub`프로시저는 주로 값을 반환할 수 없는 이벤트 처리기에 사용 됩니다. 프로시저는 `Async` `Sub` 대기 수 없으며 프로시저 호출자는 `Async` `Sub` 프로시저에서 throw 되는 예외를 catch 할 수 없습니다 `Sub` .

`Async`프로시저에서 [ByRef](../modifiers/byref.md) 매개 변수를 선언할 수 없습니다.

프로시저에 대 한 자세한 내용은 `Async` [Async 및 wait를 사용한 비동기 프로그래밍](../../programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../programming-guide/concepts/async/control-flow-in-async-programs.md)및 [비동기 반환 형식](../../programming-guide/concepts/async/async-return-types.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는 문을 사용 하 여 `Sub` 프로시저의 본문을 형성 하는 이름, 매개 변수 및 코드를 정의 합니다 `Sub` .

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>예제

다음 예제에서 `DelayAsync` 는 `Async` `Function` 반환 형식이 인입니다 <xref:System.Threading.Tasks.Task%601> . `DelayAsync` 에는 정수를 반환하는 `Return` 문이 포함됩니다. 따라서의 함수 선언에는 `DelayAsync` 의 반환 형식이 있어야 합니다 `Task(Of Integer)` . 반환 형식이 이므로 `Task(Of Integer)` `Await` 의 식 계산에서 `DoSomethingAsync` 다음 문과 같이 정수가 생성 됩니다 `Dim result As Integer = Await delayTask` ..

프로시저는 `startButton_Click` 프로시저의 예입니다 `Async Sub` . 는 함수 이기 때문에 `DoSomethingAsync` `Async` 에 대 한 호출 작업은 `DoSomethingAsync` 다음 문과 같이 대기 되어야 합니다 `Await DoSomethingAsync()` .. `startButton_Click` `Sub` 프로시저에 `Async` 식이 있으므로 한정자를 사용 하 여 프로시저를 정의 해야 합니다 `Await` .

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>참고 항목

- [Implements 문](implements-statement.md)
- [Function 문](function-statement.md)
- [매개 변수 목록](parameter-list.md)
- [Dim 문](dim-statement.md)
- [Call 문](call-statement.md)
- [으로](of-clause.md)
- [매개 변수 배열](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [방법: 제네릭 클래스 사용](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [프로시저 문제 해결](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [부분 메서드](../../programming-guide/language-features/procedures/partial-methods.md)
