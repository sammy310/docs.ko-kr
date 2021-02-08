---
description: 다음에 대해 자세히 알아보기 ... 다음 문 (Visual Basic)
title: For Each...Next 문
ms.date: 07/20/2015
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
ms.openlocfilehash: ff7afb5e3b505ebe2326343063a7884dc4f567b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769106"
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next 문(Visual Basic)

컬렉션의 각 요소에 대해 문 그룹을 반복 합니다.

## <a name="syntax"></a>Syntax

```vb
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>부분

|용어|정의|
|---|---|
|`element`|`For Each`문에 필요 합니다. `Next`문에서 선택적입니다. 변수 컬렉션의 요소를 반복 하는 데 사용 됩니다.|
|`datatype`|[`Option Infer`](option-infer-statement.md)가 on (기본값) 이거나 `element` 이미 선언 된 경우 선택 사항입니다. `Option Infer` 가 off이 고 `element` 아직 선언 되지 않은 경우에는 필수입니다. `element`의 데이터 형식입니다.|
|`group`|필수 사항입니다. 컬렉션 형식 또는 개체인 형식의 변수입니다. 가 반복 될 컬렉션을 참조 `statements` 합니다.|
|`statements`|선택 사항입니다. `For Each` `Next` 에서 각 항목에 대해 실행 되는 하나 이상의 문입니다 `group` .|
|`Continue For`|선택 사항입니다. 루프의 시작 부분으로 제어를 전달 `For Each` 합니다.|
|`Exit For`|선택 사항입니다. 루프 외부로 제어를 전달 `For Each` 합니다.|
|`Next`|필수 사항입니다. 루프의 정의를 종료 `For Each` 합니다.|

## <a name="simple-example"></a>간단한 예

`For Each` `Next` 컬렉션 또는 배열의 각 요소에 대해 문 집합을 반복 하려면 ... 루프를 사용 합니다.

> [!TIP]
> ... [ 다음 문은](for-next-statement.md) 루프의 각 반복을 컨트롤 변수와 연결 하 고 해당 변수의 초기 및 최종 값을 결정할 수 있는 경우에 효과적입니다. 그러나 컬렉션을 처리할 때 초기 및 최종 값의 개념은 의미가 없으며 컬렉션에 포함 된 요소의 수를 반드시 알아야 하는 것은 아닙니다. 이러한 종류의 경우 `For Each` ... 루프를 선택 하는 `Next` 것이 더 좋습니다.

다음 예제 `For Each` 에서 ...`Next` 문은 목록 컬렉션의 모든 요소를 반복 합니다.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

더 많은 예제는 [컬렉션](../../../standard/collections/index.md) 및 [배열](../../programming-guide/language-features/arrays/index.md)을 참조 하세요.

## <a name="nested-loops"></a>Nested Loops

`For Each`루프 하나를 다른 루프에 배치 하 여 루프를 중첩할 수 있습니다.

다음 예제 `For Each` 에서는 중첩 된 ...`Next` 구조물.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

루프를 중첩할 때 각 루프에는 고유한 변수가 있어야 합니다 `element` .

서로 다른 종류의 제어 구조를 중첩할 수도 있습니다. 자세한 내용은 [중첩 컨트롤 구조](../../programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.

## <a name="exit-for-and-continue-for"></a>종료 및 계속

문에 [대 한 exit](exit-statement.md) 로 인해 실행이 종료 `For` 됩니다.`Next` 루프를 실행 하 고 문 뒤의 문으로 제어를 전달 `Next` 합니다.

`Continue For`문은 루프의 다음 반복으로 제어를 즉시 전송 합니다. 자세한 내용은 [Continue 문](continue-statement.md)을 참조 하세요.

다음 예제에서는 및 문을 사용 하는 방법을 보여 줍니다 `Continue For` `Exit For` .

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

루프에 원하는 수의 문을 넣을 수 있습니다 `Exit For` `For Each` . 중첩 된 루프 내에서 사용 되는 경우 `For Each` `Exit For` 실행이 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.

`Exit For` 는 경우에 따라 일부 조건을 평가한 후에 `If` `Then` 사용 됩니다. 예를 들어 ... ...`Else` 구조체나. 다음 조건에 대해를 사용 하는 것이 좋습니다 `Exit For` .

- 계속 반복은 불필요 하거나 불가능 합니다. 이 오류는 잘못 된 값 이나 종료 요청으로 인해 발생할 수 있습니다.

- 예외가 `Try` catch `Catch` ... ...`Finally`. `Exit For` 블록의 끝에를 사용할 수 있습니다 `Finally` .

- 무한 하거나 무한 한 횟수를 실행 하는 루프 인 무한 루프가 있습니다. 이러한 조건을 감지한 경우를 사용 하 여 루프를 `Exit For` 이스케이프할 수 있습니다. 자세한 내용은 다음 [을 참조 하세요. Loop 문](do-loop-statement.md).

## <a name="iterators"></a>반복기

*반복기* 를 사용 하 여 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기는 함수 또는 접근자 일 수 있습니다 `Get` . 문을 사용 하 여 `Yield` 컬렉션의 각 요소를 한 번에 하나씩 반환 합니다.

문을 사용 하 여 반복기를 호출 `For Each...Next` 합니다. 각각의 `For Each` 루프의 반복이 반복기를 호출합니다. `Yield`반복기에서 문에 도달 하면 `Yield` 문의 식이 반환 되 고 코드에서 현재 위치는 유지 됩니다. 다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.

다음 예제에서는 반복기 함수를 사용 합니다. 반복기 함수에 `Yield` 는 [에 대 한 다음의 문이 있습니다. Next](for-next-statement.md) 루프. `ListEvenNumbers`메서드에서 문 본문을 반복할 때마다 `For Each` 다음 문으로 진행 하는 반복기 함수에 대 한 호출이 생성 `Yield` 됩니다.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md), [Yield 문](yield-statement.md)및 [반복기](../modifiers/iterator.md)를 참조 하세요.

## <a name="technical-implementation"></a>기술 구현

`For Each`...`Next` 문이 실행 되 고, Visual Basic는 루프가 시작 되기 전에 컬렉션을 한 번만 계산 합니다. 문 블록이 `element` 또는을 변경 하 `group` 는 경우 이러한 변경 내용은 루프 반복에 영향을 주지 않습니다.

컬렉션의 모든 요소를에 연속적으로 할당 하면 `element` `For Each` 루프가 중지 되 고 문 다음에 오는 문으로 제어가 전달 `Next` 됩니다.

[유추 옵션](option-infer-statement.md) (기본 설정)이 설정 된 경우 Visual Basic 컴파일러는의 데이터 형식을 유추할 수 있습니다 `element` . 해제 되어 있고 `element` 루프 외부에서 선언 되지 않은 경우에는 문에서 선언 해야 합니다 `For Each` . 데이터 형식을 명시적으로 선언 하려면 `element` 절을 사용 `As` 합니다. 요소의 데이터 형식이 ... 구문 외부에서 정의 되지 않은 경우 `For Each` `Next` 해당 범위는 루프의 본문입니다. `element`루프의 외부 및 내부에서 모두 선언할 수 없습니다.

문에서 선택적으로 지정할 수 있습니다 `element` `Next` . 이렇게 하면 특히 루프가 중첩 된 경우 프로그램의 가독성을 향상 시킬 수 있습니다 `For Each` . 해당 문에 표시 되는 변수와 동일한 변수를 지정 해야 합니다 `For Each` .

루프 내에서 값을 변경 하지 않는 것이 좋습니다 `element` . 이렇게 하면 코드를 읽고 디버그 하기가 더 어려워질 수 있습니다. 의 값을 변경 해도 `group` 컬렉션 또는 해당 요소에는 영향을 주지 않습니다 .이는 루프를 처음 입력할 때 결정 되었습니다.

루프를 중첩 하는 경우 `Next` 외부 중첩 수준의 문이 내부 수준의 보다 먼저 발견 되 면 `Next` 컴파일러는 오류를 표시 합니다. 그러나 컴파일러는 모든 문에서를 지정 하는 경우에만 이러한 중복 오류를 감지할 수 있습니다 `element` `Next` .

코드가 특정 순서로 컬렉션을 순회 하는 것에 의존 하는 경우 `For Each` `Next` 컬렉션에서 노출 하는 열거자 개체의 특성을 몰라도 ... 루프를 선택 하지 않는 것이 좋습니다. 순회 순서는 Visual Basic에 의해 결정 되지 않지만 <xref:System.Collections.IEnumerator.MoveNext%2A> 열거자 개체의 메서드에 의해 결정 됩니다. 따라서 컬렉션에서 반환 되는 첫 번째 요소 `element` 또는 지정 된 요소 뒤에 반환 되는 다음의 요소를 예측할 수 없습니다. ... 또는 ...와 같은 다른 루프 구조를 사용 하 여 보다 안정적인 결과를 달성할 수 있습니다. `For` `Next` `Do` `Loop`

런타임은의 요소를로 변환할 수 있어야 합니다 `group` `element` . [ `Option Strict` ] 문은 확대 변환과 축소 변환이 모두 허용 되는지 ( `Option Strict` 즉, off, 기본값) 또는 확대 변환만 허용 되는지 (on)를 제어 합니다 `Option Strict` . 자세한 내용은 [축소 변환](#narrowing-conversions)을 참조 하세요.

의 데이터 형식은 `group` 열거 가능한 컬렉션 또는 배열을 참조 하는 참조 형식 이어야 합니다. 가장 일반적으로는 네임 스페이스의 `group` <xref:System.Collections.IEnumerable> 인터페이스 또는 네임 스페이스의 인터페이스를 구현 하는 개체를 참조 `System.Collections` <xref:System.Collections.Generic.IEnumerable%601> `System.Collections.Generic` 합니다. `System.Collections.IEnumerable`<xref:System.Collections.IEnumerable.GetEnumerator%2A>컬렉션에 대 한 열거자 개체를 반환 하는 메서드를 정의 합니다. 열거자 개체는 `System.Collections.IEnumerator` 네임 스페이스의 인터페이스를 구현 `System.Collections` 하 고 <xref:System.Collections.IEnumerator.Current%2A> 속성과 <xref:System.Collections.IEnumerator.Reset%2A> 및 메서드를 노출 합니다 <xref:System.Collections.IEnumerator.MoveNext%2A> . Visual Basic는이를 사용 하 여 컬렉션을 트래버스 합니다.

### <a name="narrowing-conversions"></a>축소 변환

`Option Strict`가로 설정 된 경우 `On` 축소 변환은 일반적으로 컴파일러 오류를 발생 시킵니다. `For Each`그러나 문에서의 요소를로 변환 하 `group` `element` 는 것은 런타임에 계산 되어 수행 되며 축소 변환으로 인 한 컴파일러 오류가 표시 되지 않습니다.

다음 예제에서 `m` 에 대 한 초기 값으로의 할당은 `n` 가 설정 되어 있을 때 컴파일되지 않습니다 `Option Strict` .를로 변환 하는 것은 `Long` `Integer` 축소 변환입니다. `For Each`그러나에 대 한 할당에 `number` 에서와 동일한 변환이 필요 하지만, 문에서 컴파일러 오류가 보고 되지 않습니다 `Long` `Integer` . 많은 `For Each` 수를 포함 하는 문에서 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> 를 많은 수에 적용 하면 런타임 오류가 발생 합니다.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>IEnumerator 호출

... 루프의 실행 `For Each` 이 시작 되 면가 `Next` `group` 유효한 컬렉션 개체를 참조 하는지 확인 Visual Basic. 그렇지 않으면 예외를 throw 합니다. 그렇지 않으면 <xref:System.Collections.IEnumerator.MoveNext%2A> <xref:System.Collections.IEnumerator.Current%2A> 열거자 개체의 메서드 및 속성을 호출 하 여 첫 번째 요소를 반환 합니다. 가 `MoveNext` 다음 요소가 없다는 것을 나타냅니다. 즉, 컬렉션이 비어 있으면 `For Each` 루프가 중단 되 고 문 뒤의 문으로 제어가 전달 됩니다 `Next` . 그렇지 않으면 Visual Basic를 `element` 첫 번째 요소로 설정 하 고 문 블록을 실행 합니다.

문이 Visual Basic 때마다 `Next` `For Each` 문으로 돌아갑니다. `MoveNext` `Current` 그런 다음 및를 호출 하 여 다음 요소를 반환 하 고, 결과에 따라 블록을 실행 하거나 루프를 중지 합니다. 이 프로세스는 `MoveNext` 다음 요소가 없다는 것을 표시 하거나 문이 발견 될 때까지 계속 됩니다 `Exit For` .

**컬렉션을 수정 합니다.** 일반적으로 반환 되는 열거자 개체는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 요소를 추가, 삭제, 바꾸기 또는 다시 정렬 하 여 컬렉션을 변경할 수 없습니다. ... 루프를 시작한 후 컬렉션을 변경 하면 `For Each` `Next` 열거자 개체가 무효화 되 고, 다음 요소에 액세스 하려고 하면 <xref:System.InvalidOperationException> 예외가 발생 합니다.

그러나 이러한 수정 내용은 Visual Basic에 의해 결정 되는 것이 아니라 인터페이스의 구현에 의해 결정 <xref:System.Collections.IEnumerable> 됩니다. `IEnumerable`반복 중에 수정할 수 있는 방법으로를 구현할 수 있습니다. 이러한 동적 수정 작업을 수행 하는 경우 `IEnumerable` 사용 하는 컬렉션에 대 한 구현의 특징을 이해 해야 합니다.

**컬렉션 요소 수정** 열거자 개체의 <xref:System.Collections.IEnumerator.Current%2A> 속성은 [ReadOnly](../modifiers/readonly.md)이며 각 컬렉션 요소의 로컬 복사본을 반환합니다. 즉, ... 루프에서 요소 자체를 수정할 수 없습니다. `For Each` `Next` 수정한 내용은의 로컬 복사본에만 적용 되 `Current` 고 기본 컬렉션에는 다시 반영 되지 않습니다. 그러나 요소가 참조 형식이 면 요소가 가리키는 인스턴스의 멤버를 수정할 수 있습니다. 다음 예제에서는 `BackColor` 각 요소의 멤버를 수정 합니다 `thisControl` . 그러나 자체를 수정할 수는 없습니다 `thisControl` .

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

이전 예제에서는 `BackColor` 자체를 수정할 수는 없지만 각 요소의 멤버를 수정할 수 있습니다 `thisControl` `thisControl` .

**배열 트래버스.** 클래스는 <xref:System.Array> 인터페이스를 구현 하므로 <xref:System.Collections.IEnumerable> 모든 배열은 메서드를 노출 <xref:System.Array.GetEnumerator%2A> 합니다. 즉, ... 루프를 사용 하 여 배열을 반복할 수 있습니다. `For Each` `Next` 그러나 배열 요소만 읽을 수 있습니다. 변경할 수 없습니다.

## <a name="example"></a>예제

다음 예제에서는 C:\의 모든 폴더를 나열 합니다. 클래스를 사용 하는 디렉터리 <xref:System.IO.DirectoryInfo> 입니다.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>예제

다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다. 예제에서는에 저장 된 클래스의 인스턴스를 정렬 합니다 `Car` <xref:System.Collections.Generic.List%601> . `Car` 클래스는 <xref:System.IComparable%601.CompareTo%2A> 메서드가 구현되어야 하는 <xref:System.IComparable%601> 인터페이스를 구현합니다.

메서드를 호출할 때마다 <xref:System.IComparable%601.CompareTo%2A> 정렬에 사용 되는 단일 비교가 수행 됩니다. `CompareTo` 메서드의 사용자 작성 코드는 다른 개체와 현재 개체의 각 비교에 대한 값을 반환합니다. 현재 개체가 다른 개체보다 작으면 반환되는 값이 0보다 작고, 현재 개체가 다른 개체보다 크면 0보다 크고, 같으면 0입니다. 이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.

`ListCars` 메서드에서 `cars.Sort()` 문은 목록을 정렬합니다. <xref:System.Collections.Generic.List%601>의 <xref:System.Collections.Generic.List%601.Sort%2A> 메서드를 호출하면 `List`의 `Car` 개체에 대해 `CompareTo` 메서드가 자동으로 호출됩니다.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>참고 항목

- [컬렉션](../../../standard/collections/index.md)
- [For...Next 문](for-next-statement.md)
- [루프 구조체](../../programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 문](while-end-while-statement.md)
- [Do...Loop 문](do-loop-statement.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [개체 이니셜라이저: 명명된 형식 및 무명 형식](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [컬렉션 이니셜라이저](../../programming-guide/language-features/collection-initializers/index.md)
- [배열](../../programming-guide/language-features/arrays/index.md)
