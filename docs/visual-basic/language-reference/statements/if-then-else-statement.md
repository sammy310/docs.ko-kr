---
description: 다음에 대해 자세히 알아보세요. 그런 다음 ... Else 문 (Visual Basic)
title: If...Then...Else 문
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 83850771354b95f0e2d9c1bf1360a61d5264fe2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769015"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 문(Visual Basic)

식의 값에 따라 문 그룹을 조건부로 실행합니다.

## <a name="syntax"></a>Syntax

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>예제 코드에 대 한 빠른 링크

이 문서 `If` 에는 `Then` 다음을 사용 하는 방법을 보여 주는 몇 가지 예가 포함 되어 있습니다. ...`Else` 선언문

- [여러 줄 구문 예제](#multi-line)
- [중첩 구문 예제](#nested)
- [한 줄 구문 예제](#single-line)

## <a name="parts"></a>부분

`condition` \
필수 사항입니다. 식 는 또는로 `True` 계산 `False` 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다 `Boolean` .

식이 Nothing으로 계산 되는 [null을 허용](../../programming-guide/language-features/data-types/nullable-value-types.md) 하는 변수인 경우 `Boolean` 조건은 식이 인 것 처럼 처리 되 고 블록이 있는 경우에는 블록을 [](../nothing.md)평가 하 고 블록이 있으면 `False` `ElseIf` `Else` 실행 합니다.

`Then` \
한 줄 구문에 필요 합니다. 여러 줄 구문에서 선택 사항입니다.

`statements` \
선택 사항입니다. 가 `If` `Then` 로 평가 되는 경우 실행 되는 하나 이상의 `condition` 문 ... `True`

`elseifcondition` \
`ElseIf`가 있는 경우 필수입니다. 식 는 또는로 `True` 계산 `False` 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다 `Boolean` .

`elseifstatements` \
선택 사항입니다. 가 `ElseIf` `Then` 로 평가 되는 경우 실행 되는 하나 이상의 `elseifcondition` 문 ... `True`

`elsestatements` \
선택 사항입니다. 이전 `condition` 또는 식이로 계산 되지 않는 경우 실행 되는 하나 이상의 문 `elseifcondition` `True` 입니다.

`End If` \
여러 줄 `If` 버전의 `Then` 를 종료 합니다. ...`Else` 거부.

## <a name="remarks"></a>설명

### <a name="multiline-syntax"></a>여러 줄 구문

`If`... `Then` ...`Else` 문이 발견 되 면 `condition` 가 테스트 됩니다. `condition`가 이면 `True` 다음 문이 `Then` 실행 됩니다. `condition`가 이면 `False` 각 `ElseIf` 문 (있는 경우)이 순서 대로 평가 됩니다. `True` `elseifcondition` 가 발견 되 면 연결 된 바로 다음에 오는 문이 `ElseIf` 실행 됩니다. 가 `elseifcondition` 로 계산 되지 `True` 않거나 `ElseIf` 문이 없으면 다음 문이 `Else` 실행 됩니다. , 또는 다음에 오는 문을 실행 한 후에 `Then` `ElseIf` `Else` 는 다음 문을 사용 하 여 실행이 계속 `End If` 됩니다.

`ElseIf`And `Else` 절은 모두 선택 사항입니다. `ElseIf`원하는 수의 `If` `Then` 절을 원하는 개수 만큼 포함할 수 있습니다. ...`Else` 문 이지만 절 뒤에는 `ElseIf` 절이 나타나지 않습니다 `Else` . `If`...`Then` ...`Else` 문은 서로 중첩 될 수 있습니다.

여러 줄 구문에서 `If` 문은 첫째 줄에서 유일한 문 이어야 합니다. `ElseIf`, `Else` 및 `End If` 문은 줄 레이블 앞에만 올 수 있습니다. ... `If` `Then` ...`Else` 블록은 문으로 끝나야 합니다 `End If` .

> [!TIP]
> [Select ... Case 문은](select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 평가할 때 더 유용할 수 있습니다.

### <a name="single-line-syntax"></a>Single-Line 구문

True 인 경우 코드를 실행 하는 단일 조건에 대해 한 줄 구문을 사용할 수 있습니다. 그러나 여러 줄로 구성 된 구문은 더 많은 구조와 유연성을 제공 하며 읽기, 유지 관리 및 디버깅 하기가 더 쉽습니다.

키워드 다음에 나오는 항목을 `Then` 검사 하 여 문이 한 줄 인지 여부를 확인 `If` 합니다. 주석이 아닌 다른 항목이 `Then` 같은 줄에 표시 되는 경우이 문은 한 줄로 된 문으로 처리 됩니다 `If` . `Then`가 없으면 여러 줄 `If` `Then` 의 시작 이어야 합니다. ...`Else`.

한 줄 구문에서 ... 결정의 결과로 여러 문을 실행할 수 있습니다. `If` `Then` 모든 문은 같은 줄에 있고 콜론으로 구분 해야 합니다.

## <a name="multiline-syntax-example"></a>여러 줄 구문 예제

<a name="multi-line"></a>

다음 예제에서는 ...의 여러 줄 `If` 로 된 `Then` 구문을 사용 하는 방법을 보여 줍니다. ...`Else` 선언문.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>중첩 구문 예제

<a name="nested"></a>

다음 예제에 `If` 는 중첩 `Then` 된 ... ...`Else` 할당문.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Single-Line 구문 예제

<a name="single-line"></a> 다음 예제에서는 한 줄의 구문을 사용 하는 방법을 보여 줍니다.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else 지시문](../directives/if-then-else-directives.md)
- [Select...Case 문](select-case-statement.md)
- [중첩 제어 구조체](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [판단 구조체](../../programming-guide/language-features/control-flow/decision-structures.md)
- [Visual Basic의 논리 및 비트 연산자](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If 연산자](../operators/if-operator.md)
