---
title: If...Then...Else 문(Visual Basic)
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
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637757"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 문(Visual Basic)
식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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

이 문서에서는의 용도 보여 주는 몇 가지 예는 `If`... `Then`... `Else` 문:

* [여러 줄로 된 구문 예제](#multi-line)
* [중첩 된 구문 예제](#nested)
* [한 줄 구문 예제](#single-line)

## <a name="parts"></a>요소  
 `condition`  
 필수 요소. 식입니다. 여야 `True` 또는 `False`, 또는 암시적으로 변환할 수 있는 데이터 형식으로 `Boolean`입니다.  
  
 식이 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 계산 되는 변수 [Nothing](../../../visual-basic/language-reference/nothing.md), 조건 식이 처럼 처리 됩니다 `False` 및 `Else` 블록이 실행 됩니다.  
  
 `Then`  
 한 줄 구문; 필요 여러 줄 구문에서 선택 사항입니다.  
  
 `statements`  
 선택 사항입니다. 하나 이상의 문 다음 `If`... `Then` 하는 경우 실행 되는 `condition` 로 `True`합니다.  
  
 `elseifcondition`  
 필요한 경우 `ElseIf` 표시 됩니다. 식입니다. 여야 `True` 또는 `False`, 또는 암시적으로 변환할 수 있는 데이터 형식으로 `Boolean`입니다.  
  
 `elseifstatements`  
 선택 사항입니다. 하나 이상의 문 다음 `ElseIf`... `Then` 하는 경우 실행 되는 `elseifcondition` 로 `True`합니다.  
  
 `elsestatements`  
 선택 사항입니다. 이전 하는 경우 실행 되는 하나 이상의 문을 `condition` 나 `elseifcondition` 식이 `True`합니다.  
  
 `End If`  
 여러 줄로 된 버전의 종료 `If`... `Then`... `Else` 블록입니다.  
  
## <a name="remarks"></a>설명  
  
### <a name="multiline-syntax"></a>여러 줄 구문  
 경우는 `If`... `Then`... `Else` 문이 있으면 `condition` 테스트 됩니다. 하는 경우 `condition` 됩니다 `True`, 다음 문을 `Then` 실행 됩니다. 하는 경우 `condition` 됩니다 `False`각각 `ElseIf` 문 (있는 경우) 순서 대로 평가 됩니다. 경우는 `True` `elseifcondition` 발견 되 면 바로 다음에 관련 된 문을 `ElseIf` 실행 됩니다. 없으면 `elseifcondition` 로 평가 `True`, 있는 경우 또는 없습니다 `ElseIf` 다음 문은 `Else` 실행 됩니다. 다음을 실행 한 후 `Then`, `ElseIf`, 또는 `Else`, 다음 문으로 실행이 계속 `End If`합니다.  
  
 합니다 `ElseIf` 고 `Else` 절이 둘 다 선택 사항입니다. 만큼 할 수 있습니다 `ElseIf` 때 절에서 원하는 `If`... `Then`... `Else` 문과 비슷하지만 no `ElseIf` 절 뒤에 나타날 수는 `Else` 절. `If`... `Then`... `Else` 문을 서로 중첩 될 수 있습니다.  
  
 여러 줄 구문에서은 `If` 문은 첫 번째 줄에서 유일한 문 이어야 합니다. 합니다 `ElseIf`, `Else`, 및 `End If` 문의 줄 레이블을 의해서만 올 수 있습니다. `If`... `Then`... `Else` 블록은 끝나야는 `End If` 문입니다.  
  
> [!TIP]
>  [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 평가할 때 더 유용할 수 있습니다.  
  
### <a name="single-line-syntax"></a>한 줄 구문  
 True 일 경우 실행할 코드를 사용 하 여 단일 조건에 대 한 한 줄 구문을 사용할 수 있습니다. 그러나 여러 줄 구문 더 많은 구조와 유연성을 제공 및 읽기, 유지 관리 및 디버그 하기가 쉽습니다.  
  
 다음은 `Then` 키워드를 검사 하는 문을 한 줄 인지 여부를 확인 `If`합니다. 뒤에 나오면 주석 이외의 `Then` 같은 줄에서 문을 한 줄으로 처리 됩니다 `If` 문입니다. 하는 경우 `Then` 가 없는 여러 줄의 시작 해야 `If`... `Then`... `Else`.  
  
 한 줄 구문의 결과로 실행 되는 여러 개의 문을 포함할 수 있습니다는 `If`... `Then` 의사 결정 합니다. 모든 문이 동일한 줄에 있어야 합니다 및 콜론으로 구분 되어야 합니다.  

## <a name="multiline-syntax-example"></a>여러 줄로 된 구문 예제

<a name="multi-line"></a>
 
 다음 예제를 여러 줄 구문의 사용을 `If`... `Then`... `Else` 문입니다.  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>중첩 된 구문 예제

<a name="nested"></a>

 다음 예제에는 중첩 된 `If`... `Then`... `Else` 문입니다.  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>한 줄 구문 예제
  
<a name="single-line"></a> 다음 예제에서는 줄 구문을 사용을 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [판단 구조](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If 연산자](../../../visual-basic/language-reference/operators/if-operator.md)
