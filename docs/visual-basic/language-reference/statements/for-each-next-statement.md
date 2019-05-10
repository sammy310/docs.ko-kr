---
title: For Each...Next 문(Visual Basic)
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
ms.openlocfilehash: ecde6ca8d3a95e356c5b1389ba95c4ad72b68d45
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623900"
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next 문(Visual Basic)
컬렉션의 각 요소에 대 한 문 그룹을 반복합니다.  
  
## <a name="syntax"></a>구문  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|에 필요한는 `For Each` 문입니다. 선택 사항는 `Next` 문입니다. 변수입니다. 컬렉션의 요소를 반복 하는 데 사용 합니다.|  
|`datatype`|필요한 경우 `element` 이미 선언 되지 않습니다. 데이터 형식의 `element`합니다.|  
|`group`|필수 요소. 컬렉션 형식 또는 개체 형식으로 사용 되는 변수입니다. 컬렉션을 의미 합니다 `statements` 반복 됩니다.|  
|`statements`|선택 사항입니다. 간에 하나 이상의 문으로 `For Each` 하 고 `Next` 각 항목에 대해 실행 되는 `group`합니다.|  
|`Continue For`|선택 사항입니다. 컨트롤의 시작 부분으로 전송 된 `For Each` 루프입니다.|  
|`Exit For`|선택 사항입니다. 밖으로 제어를 전송 합니다 `For Each` 루프입니다.|  
|`Next`|필수 요소. 정의 종료 합니다 `For Each` 루프입니다.|  
  
## <a name="simple-example"></a>간단한 예  
 사용 된 `For Each`... `Next` 컬렉션 또는 배열의 각 요소에 대 한 문 집합을 반복 하려는 경우 루프입니다.  
  
> [!TIP]
>  [에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 제어 변수를 사용 하 여 루프의 각 반복을 연결 하 고 해당 변수의 초기 및 최종 값을 확인 수 때 잘 작동 합니다. 그러나 컬렉션을 처리 하는 경우 초기 및 최종 값 개념이 의미 하지 않으며 컬렉션의 요소 수를 알 필요가 없습니다. 이 유형의 경우에는 `For Each`... `Next` 루프는 종종 것이 좋습니다.  
  
 다음 예제에서는 `For Each`...`Next` 문 목록 컬렉션의 모든 요소를 반복합니다.  
  
 [!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]  
  
 더 많은 예제를 참조 하세요 [컬렉션](../../../standard/collections/index.md) 하 고 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="nested-loops"></a>중첩 된 루프  
 중첩할 수 있습니다 `For Each` 루프 내에서 다른 한 루프를 배치 하 여 합니다.  
  
 다음 예제에서는 중첩 된 `For Each`...`Next` 구조입니다.  
  
 [!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]  
  
 각 루프는 고유 해야 루프를 중첩할 때 `element` 변수입니다.  
  
 또한 다른 종류의 서로 다른 제어 구조를 중첩할 수 있습니다. 자세한 내용은 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-for-and-continue-for"></a>에 대 한 종료 하 고 계속  
 합니다 [에 Exit](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 사용 하면 실행을 종료 하는 `For`...`Next` 루프 및 전송 컨트롤 뒤에 오는 문에 `Next` 문입니다.  
  
 `Continue For` 문은 제어 즉시 루프의 다음 반복으로 합니다. 자세한 내용은 [Continue 문은](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `Continue For` 고 `Exit For` 문.  
  
 [!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]  
  
 개수에 관계 없이 입력할 수 있습니다 `Exit For` 문에서 `For Each` 루프입니다. 사용 하는 경우 내에 중첩 `For Each` 루프 `Exit For` 실행이 다음 더 높은 수준의 중첩 가장 안쪽의 루프 및 전송 컨트롤을 종료 합니다.  
  
 `Exit For` 특정 조건에 대 한 평가 후에 대개 예는 `If`... `Then`... `Else` 구조입니다. 사용 하려는 `Exit For` 다음 조건에 대 한 합니다.  
  
- 계속 반복은 불필요 하거나 불가능 합니다. 잘못 된 값 이나 종료 요청 원인일 수 있습니다.  
  
- 예외가 포착 되는 `Try`... `Catch`... `Finally`. 사용할 수 있습니다 `Exit For` 끝에 `Finally` 블록입니다.  
  
- 여기도 무한히 여러 번 실행할 수는 루프가 무한 루프를 합니다. 이러한 상태를 발견 하는 경우 사용할 수 있습니다 `Exit For` 루프를 이스케이프 합니다. 자세한 내용은 참조 하세요. [수행 하는 중... 문이 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.  
  
## <a name="iterators"></a>반복기  
 사용 하는 *반복기* 컬렉션에 대해 사용자 지정 반복을 수행 하 합니다. 반복기는 함수 일 수 있습니다 또는 `Get` 접근자입니다. 사용 된 `Yield` 문을 한 번에 하나씩 컬렉션의 각 요소를 반환 합니다.  
  
 사용 하 여 반복기를 호출 하는 `For Each...Next` 문입니다. 각각의 `For Each` 루프의 반복이 반복기를 호출합니다. 경우는 `Yield` 반복기 식에서에서 문에 도달 하면는 `Yield` 문을 반환 되 고 코드에서 현재 위치는 유지 됩니다. 다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 다음 예제에서는 반복기 함수를 사용 합니다. 반복기 함수에는 `Yield` 문 내에 있는 [에 대 한 중... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다. 에 `ListEvenNumbers` 메서드, 각 반복의 합니다 `For Each` 문 본문에서 다음 단계로 진행 하는 반복기 함수에 대 한 호출이 생성 `Yield` 문.  
  
 [!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]  
  
 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 [Yield 문을](../../../visual-basic/language-reference/statements/yield-statement.md), 및 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 경우는 `For Each`...`Next` 한 번만 루프가 시작 되기 전에 컬렉션을 평가 하는 Visual Basic 문을 실행 합니다. 문 블록이 변경 되 면 `element` 또는 `group`, 이러한 변경 내용을 반복 루프의 영향을 주지 않습니다.  
  
 때 컬렉션의 모든 요소가 연속적에 할당 된 `element`는 `For Each` 루프가 종료 되 고 다음 문으로 전달 제어를 `Next` 문입니다.  
  
 하는 경우 `element` 선언 해야이 루프 외부 선언 되지 않은에 `For Each` 문. 형식을 선언할 수 있습니다 `element` 를 사용 하 여 명시적으로 `As` 문 또는 있습니다 형식을 할당 하는 형식 유추에 사용할 수 있습니다. 두 경우 모두 범위의 `element` 루프의 본문입니다. 그러나 선언할 수 없습니다 `element` 외부와 루프입니다.  
  
 선택적으로 지정할 수 있습니다 `element` 에 `Next` 문입니다. 중첩 된 경우에 특히 프로그램의 가독성을 향상 시킵니다이 `For Each` 루프입니다. 해당 표시 되는 것과 동일한 변수를 지정 해야 합니다 `For Each` 문입니다.  
  
 값을 변경 하지 않도록 하려는 `element` 루프 내에서. 이렇게 어려울 수 있습니다 더 읽고 코드를 디버그 합니다. 값을 변경 `group` 컬렉션 또는 루프를 처음 입력 하면 결정 된 해당 요소에 영향을 주지 않습니다.  
  
 경우 루프를 중첩 하는 경우는 `Next` 바깥쪽 중첩 수준을 문이 하기 전에 `Next` 컴파일러는 내부 수준에서 오류를 알립니다. 그러나 컴파일러 감지할 수 있습니다이 오류를 지정 하는 경우에 겹치는 `element` 에서 모든 `Next` 문입니다.  
  
 코드를 특정 순서로 컬렉션을 순회에 종속 된 경우는 `For Each`... `Next` 루프에 적합 하지 않을, 열거자 개체의 특징을 알 수 없는 컬렉션을 노출 합니다. 트래버스 순서에서 하지만 Visual Basic에서 결정 되지 않습니다는 <xref:System.Collections.IEnumerator.MoveNext%2A> 열거자 개체의 메서드. 반환할 첫 번째 컬렉션의 요소를 예측할 수 없습니다 따라서 `element`, 다음에 지정 된 요소 반환 되는 또는 합니다. 와 같은 다른 루프 구조를 사용 하 여 더 안정적인 결과 얻을 수 있습니다 `For`... `Next` 또는 `Do`... `Loop`.  
  
 데이터 형식이 `element` 요소의 데이터 형식이 되도록 해야 `group` 변환할 수 있습니다.  
  
 데이터 형식은 `group` 컬렉션 또는 열거할 수 있는 배열을 참조 하는 참조 형식 이어야 합니다. 즉 가장 일반적으로 `group` 구현 하는 개체를 참조 하는 <xref:System.Collections.IEnumerable> 의 인터페이스는 `System.Collections` 네임 스페이스 또는 <xref:System.Collections.Generic.IEnumerable%601> 의 인터페이스는 `System.Collections.Generic` 네임 스페이스입니다. `System.Collections.IEnumerable` 정의 된 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 컬렉션에 대 한 열거자 개체를 반환 하는 메서드. 열거자 개체를 구현 하는 `System.Collections.IEnumerator` 의 인터페이스를 `System.Collections` 네임 스페이스 노출 합니다 <xref:System.Collections.IEnumerator.Current%2A> 속성 및 <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드. Visual Basic을 사용 하 여 컬렉션을 순회를 이러한.  
  
### <a name="narrowing-conversions"></a>축소 변환  
 때 `Option Strict` 로 설정 된 `On`, 축소 변환에는 일반적으로 컴파일러 오류가 발생 합니다. 그러나에 `For Each` 문을 요소에서 변환 `group` 에 `element` 계산 되 고 런타임에 수행 축소 변환으로 인해 발생 하는 컴파일러 오류가 표시 되지 않습니다.  
  
 다음 예에서 할당 `m` 에 대 한 초기 값으로 `n` 때 컴파일되지 않습니다 `Option Strict` 있기 때문에 변환을 `Long` 에 `Integer` 축소 변환입니다. 에 `For Each` 문, 컴파일러 오류가 없는 것 인데, 할당 하는 경우에 보고 `number` 에서 동일한 변환을 수행 해야 `Long` 에 `Integer`입니다. 에 `For Each` 를 많은 수를 포함 하는 문에서 런타임 오류가 발생 하는 경우 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> 많은 경우에 적용 됩니다.  
  
 [!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]  
  
### <a name="ienumerator-calls"></a>IEnumerator 호출  
 경우 실행을 `For Each`... `Next` 루프가 시작, Visual Basic 확인 `group` 유효한 컬렉션 개체를 참조 합니다. 그렇지 않은 경우 예외가 throw 됩니다. 를 호출 합니다 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드 및 <xref:System.Collections.IEnumerator.Current%2A> 첫 번째 요소를 반환 하는 열거자 개체의 속성입니다. 경우 `MoveNext` 있음을 다음 요소가 없는 즉, 컬렉션이 비어 합니다 `For Each` 루프가 종료 되 고 다음 문으로 전달 제어를 `Next` 문입니다. 그렇지 않은 경우 Visual Basic 설정 `element` 첫 번째 요소 및 문 블록을 실행 합니다.  
  
 Visual Basic 발생할 때마다 합니다 `Next` 문을 반환 합니다 `For Each` 문. 다시 호출한 `MoveNext` 고 `Current` 및 반환 하 고 다음 요소인 다시 해당 블록을 실행 또는 결과 따라 루프를 중지 합니다. 될 때까지이 프로세스가 계속 됩니다 `MoveNext` 다음 요소가 있는지를 나타내는 또는 `Exit For` 문이 있습니다.  
  
 **컬렉션을 수정 합니다.** 반환 하는 열거자 개체 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 일반적으로 선택할 수는 없습니다 추가, 삭제, 바꾸기 또는 모든 요소를 다시 정렬 하 여 컬렉션을 변경 합니다. 초기화 한 후에 컬렉션을 변경한 경우를 `For Each`... `Next` 루프 열거자 개체를 무효화 하 고 다음 요소에 액세스 하려고 하면는 <xref:System.InvalidOperationException> 예외입니다.  
  
 그러나 수정이 차단은 Visual Basic에서 아니라 구현 대신에 의해 결정 되지 않습니다는는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 구현 하는 것이 불가능 `IEnumerable` 방식으로 반복 하는 동안 수정할 수 있도록 합니다. 이러한 동적 수정을 수행를 고려 하는 경우의 특징을 이해 하는 있는지 확인 합니다 `IEnumerable` 구현을 사용 하는 컬렉션에 있습니다.  
  
 **컬렉션 요소를 수정 합니다.** 합니다 <xref:System.Collections.IEnumerator.Current%2A> 열거자 개체의 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), 각 컬렉션 요소의 로컬 복사본을 반환 합니다. 즉, 요소 자체를 수정할 수 없음을에 `For Each`... `Next` 루프입니다. 수정 내용을에서 로컬 복사본에만 영향을 줍니다 `Current` 다시 기본 컬렉션에 반영 되지 않습니다. 그러나 요소가 참조 형식이 면 가리키는 인스턴스 멤버를 수정할 수 있습니다. 다음 예제를 수정 합니다 `BackColor` 의 각 멤버 `thisControl` 요소입니다. 그러나 수정할 수 없는 `thisControl` 자체입니다.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 앞의 예제를 수정할 수는 `BackColor` 각 멤버 `thisControl` 요소를 수정할 수 없습니다 있지만 `thisControl` 자체입니다.  
  
 **통과 하는 배열입니다.** 때문에 <xref:System.Array> 클래스가 구현 하는 <xref:System.Collections.IEnumerable> 인터페이스를 모든 배열 노출는 <xref:System.Array.GetEnumerator%2A> 메서드. 즉, 배열을 반복할 수 있는지를 `For Each`... `Next` 루프입니다. 그러나 배열 요소를 읽을 수 있습니다. 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 C:\ 디렉터리에 있는 모든 폴더를 사용 하 여 나열 된 <xref:System.IO.DirectoryInfo> 클래스입니다.  
  
 [!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다. 예제 인스턴스를 정렬 한 `Car` 에 저장 되는 클래스를 <xref:System.Collections.Generic.List%601>. `Car` 클래스는 <xref:System.IComparable%601.CompareTo%2A> 메서드가 구현되어야 하는 <xref:System.IComparable%601> 인터페이스를 구현합니다.  
  
 각 호출에는 <xref:System.IComparable%601.CompareTo%2A> 메서드 정렬에 사용 되는 단일 비교가 수행 됩니다. `CompareTo` 메서드의 사용자 작성 코드는 다른 개체와 현재 개체의 각 비교에 대한 값을 반환합니다. 현재 개체가 다른 개체보다 작으면 반환되는 값이 0보다 작고, 현재 개체가 다른 개체보다 크면 0보다 크고, 같으면 0입니다. 이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.  
  
 `ListCars` 메서드에서 `cars.Sort()` 문은 목록을 정렬합니다. <xref:System.Collections.Generic.List%601>의 <xref:System.Collections.Generic.List%601.Sort%2A> 메서드를 호출하면 `List`의 `Car` 개체에 대해 `CompareTo` 메서드가 자동으로 호출됩니다.  
  
 [!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]  
  
## <a name="see-also"></a>참고자료

- [컬렉션](../../../standard/collections/index.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)
