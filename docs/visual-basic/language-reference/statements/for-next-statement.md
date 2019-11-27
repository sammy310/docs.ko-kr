---
title: For...Next 문
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 3cae44abb8e790542f11e6c5a5f1e317675ff988
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351191"
---
# <a name="fornext-statement-visual-basic"></a>For...Next 문(Visual Basic)

지정 된 횟수 만큼 문 그룹을 반복 합니다.

## <a name="syntax"></a>구문

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>요소

|파트|설명|
|----------|-----------------|
|`counter`|`For` 문에 필요 합니다. 숫자 변수입니다. 루프의 제어 변수입니다. 자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.|
|`datatype`|(선택 사항) `counter`데이터 형식입니다. 자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.|
|`start`|필수입니다. 숫자 식입니다. `counter`의 초기 값입니다.|
|`end`|필수입니다. 숫자 식입니다. `counter`최종 값입니다.|
|`step`|(선택 사항) 숫자 식입니다. 루프를 통해 매번 `counter` 증가 하는 양입니다.|
|`statements`|(선택 사항) `For`와 `Next` 사이에 있는 하나 이상의 문 (지정 된 횟수 만큼 실행)|
|`Continue For`|(선택 사항) 제어를 다음 루프 반복으로 전송 합니다.|
|`Exit For`|(선택 사항) `For` 루프에서 제어를 전달 합니다.|
|`Next`|필수입니다. `For` 루프의 정의를 종료 합니다.|

> [!NOTE]
> 이 문에서는 `To` 키워드를 사용 하 여 카운터 범위를 지정 합니다. Select ...에서이 키워드를 사용할 수도 있습니다. [ Case 문과](../../../visual-basic/language-reference/statements/select-case-statement.md) 배열 선언에 있습니다. 배열 선언에 대 한 자세한 내용은 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)을 참조 하십시오.

## <a name="simple-examples"></a>간단한 예

문 집합을 설정 된 횟수 만큼 반복 하려면 `For`...`Next` 구조를 사용 합니다.

다음 예제에서 `index` 변수는 1 값으로 시작 하 고 루프가 반복 될 때마다 증가 하 고 `index` 값이 5에 도달 하면 끝납니다.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

다음 예제에서 `number` 변수는 2에서 시작 하 고 루프의 각 반복에서 0.25으로 감소 하 고 `number` 값이 0에 도달 하면 끝납니다. `-.25`의 `Step` 인수는 루프가 반복 될 때마다 0.25 값을 줄입니다.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> 잠시 [... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 또는 [Do ... Loop 문은](../../../visual-basic/language-reference/statements/do-loop-statement.md) 루프에서 문을 실행 하는 횟수를 미리 알 수 없는 경우에 잘 작동 합니다. 그러나 루프를 특정 횟수 만큼 실행 해야 하는 경우에는 `For`...`Next` 루프를 선택 하는 것이 더 좋습니다. 루프를 처음 시작할 때 반복 횟수를 결정 합니다.

## <a name="nesting-loops"></a>중첩 루프

루프 하나를 다른 루프에 배치 하 여 `For` 루프를 중첩할 수 있습니다. 다음 예제에서는 단계 값이 다른 중첩 된 `For`...`Next` 구조체를 보여 줍니다. 외부 루프는 루프의 모든 반복에 대 한 문자열을 만듭니다. 내부 루프는 루프의 모든 반복에 대해 루프 카운터 변수를 감소 시킵니다.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

루프를 중첩 하는 경우 각 루프에 고유한 `counter` 변수가 있어야 합니다.

서로 다른 종류의 제어 구조를 중첩할 수도 있습니다. 자세한 내용은 [중첩 컨트롤 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.

## <a name="exit-for-and-continue-for"></a>종료 및 계속

`Exit For` 문은 즉시 `For`를 끝냅니다`Next` 루프를 실행 하 고 제어를 `Next` 문 다음에 오는 문으로 전달 합니다.

`Continue For` 문은 루프의 다음 반복으로 제어를 즉시 전달 합니다. 자세한 내용은 [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)을 참조 하세요.

다음 예에서는 `Continue For` 및 `Exit For` 문을 사용 하는 방법을 보여 줍니다.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

`For`에 원하는 수의 `Exit For` 문을 넣을 수 있습니다.`Next` loop. 중첩 된 `For`내에서 사용 하는 경우`Next` 루프, `Exit For` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.

`Exit For`은 일부 조건을 평가한 후에 자주 사용 됩니다 (예: `If`...`Then`...`Else` 구조체). 다음 조건에 `Exit For`를 사용 하는 것이 좋습니다.

- 계속 반복은 불필요 하거나 불가능 합니다. 잘못 된 값 또는 종료 요청은이 조건을 만들 수 있습니다.

- `Try`...`Catch`...`Finally` 문에서 예외를 catch 합니다. `Finally` 블록의 끝에 `Exit For`를 사용할 수 있습니다.

- 무한 하거나 무한 한 횟수를 실행 하는 루프 인 무한 루프를 사용할 수 있습니다. 이러한 조건을 감지 하면 `Exit For`를 사용 하 여 루프를 이스케이프할 수 있습니다. 자세한 내용은 다음 [을 참조 하세요. Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>기술적 구현

`For`...`Next` 루프가 시작 될 때 Visual Basic `start`, `end`및 `step`평가 됩니다. Visual Basic는 현재이 값을 평가한 다음 `counter`에 `start`를 할당 합니다. 문 블록을 실행 하기 전에 Visual Basic `counter`를 `end`와 비교 합니다. `counter` 이미 `end` 값 보다 크거나 `step`가 음수인 경우 더 작은 경우 `For` 루프가 종료 되 고 `Next` 문 다음에 오는 문으로 제어가 전달 됩니다. 그렇지 않으면 문 블록이 실행 됩니다.

Visual Basic에서 `Next` 문을 발견할 때마다 `step`으로 `counter` 증가 하 고 `For` 문으로 돌아갑니다. 다시 `end``counter`를 비교한 다음 결과에 따라 블록을 실행 하거나 루프를 종료 합니다. 이 프로세스는 `counter` `end` 전달 되거나 `Exit For` 문이 발생할 때까지 계속 됩니다.

`counter`가 `end`를 전달할 때까지 루프가 중지 되지 않습니다. `counter` `end`와 같으면 루프가 계속 됩니다. 블록을 실행할지 여부를 결정 하는 비교는 `step`가 양수인 경우 `end`  <= `counter`하 고 `counter`가 음수인 경우  >= `end` `step` 합니다.

루프 내에서 `counter` 값을 변경 하는 경우 코드를 읽고 디버그 하기가 더 어려울 수 있습니다. `start`, `end`또는 `step` 값을 변경 해도 루프가 처음 입력 될 때 결정 된 반복 값에는 영향을 주지 않습니다.

루프를 중첩 하는 경우 컴파일러는 내부 수준의 `Next` 문 앞에 있는 외부 중첩 수준의 `Next` 문을 발견 하면 오류를 표시 합니다. 그러나 컴파일러는 모든 `Next` 문에서 `counter` 지정 하는 경우에만 이러한 중복 오류를 감지할 수 있습니다.

### <a name="step-argument"></a>Step 인수

`step`의 값은 양수 또는 음수일 수 있습니다. 이 매개 변수는 다음 표에 따라 루프 처리를 결정 합니다.

|**단계 값**|**루프 실행**|
|--------------------|--------------------------|
|양수 또는 0|`counter` <= `end`|
|부정|`counter` >= `end`|

`step` 기본값은 1입니다.

### <a name="BKMK_Counter"></a>Counter 인수

다음 표에서는 `counter` 전체 `For…Next` 루프로 범위가 지정 된 새 지역 변수를 정의할 지 여부를 나타냅니다. 이러한 결정은 `datatype` 있는지 여부와 `counter` 이미 정의 되어 있는지 여부에 따라 달라 집니다.

|`datatype` 제공 되나요?|`counter` 이미 정의 되어 있나요?|Result (`counter`에서 전체 `For...Next` 루프로 범위가 지정 된 새 지역 변수를 정의 하는지 여부)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|아니요|예|아니요. `counter` 이미 정의 되어 있기 때문입니다. `counter` 범위가 프로시저에 로컬인 경우 컴파일 타임 경고가 발생 합니다.|
|아니요|아니요|예. 데이터 형식은 `start`, `end`및 `step` 식에서 유추 됩니다. 형식 유추에 대 한 자세한 내용은 [Option 유추 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.|
|예|예|예, 하지만 기존 `counter` 변수가 프로시저 외부에서 정의 된 경우에만 가능 합니다. 해당 변수는 분리 된 상태로 유지 됩니다. 기존 `counter` 변수의 범위가 프로시저에 로컬인 경우 컴파일 타임 오류가 발생 합니다.|
|예|아니요|예.|

`counter` 데이터 형식은 다음 형식 중 하나 여야 하는 반복의 유형을 결정 합니다.

- `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`또는 `Double`입니다.

- [Enum 문을](../../../visual-basic/language-reference/statements/enum-statement.md)사용 하 여 선언 하는 열거형입니다.

- `Object`입니다.

- 다음 연산자를 포함 하는 `T` 형식입니다. 여기서 `B`는 `Boolean` 식에서 사용할 수 있는 형식입니다.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

`Next` 문에서 `counter` 변수를 선택적으로 지정할 수 있습니다. 이 구문은 특히 `For` 루프가 중첩 된 경우 프로그램의 가독성을 향상 시킵니다. 해당 `For` 문에 표시 되는 변수를 지정 해야 합니다.

`start`, `end`및 `step` 식은 `counter`형식으로 확대 되는 모든 데이터 형식으로 계산 될 수 있습니다. `counter`에 사용자 정의 형식을 사용 하는 경우 `CType` 변환 연산자를 정의 하 여 `start`, `end`또는 `step` 형식을 `counter`형식으로 변환 해야 할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 제네릭 목록에서 모든 요소를 제거 합니다. [For Each ... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)에서는 내림차순으로 반복 되는 `For`...`Next` 문을 보여 줍니다. 이 예제에서는 `removeAt` 메서드로 인해 제거 된 요소 뒤의 요소가 더 낮은 인덱스 값을 갖도록 하기 때문에이 기술을 사용 합니다.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>예제

다음 예제에서는 [Enum 문을](../../../visual-basic/language-reference/statements/enum-statement.md)사용 하 여 선언 된 열거형을 반복 합니다.

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>예제

다음 예제에서 문 매개 변수는 `+`, `-`, `>=`및 `<=` 연산자에 대 한 연산자 오버 로드가 있는 클래스를 사용 합니다.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>참고 항목

- <xref:System.Collections.Generic.List%601>
- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [컬렉션](../../programming-guide/concepts/collections.md)
