---
title: 중첩 제어 구조체
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266926"
---
# <a name="nested-control-structures-visual-basic"></a>중첩 제어 구조(Visual Basic)
다른 컨트롤 문(예: 루프 내의 `If...Then...Else` 블록) `For...Next` 내에 제어 문을 배치할 수 있습니다. 다른 제어 문 안에 배치된 제어 문이 *중첩되었다고*합니다.  
  
## <a name="nesting-levels"></a>중첩 수준  
 Visual Basic의 컨트롤 구조는 원하는 수의 레벨에 중첩될 수 있습니다. 각 구조의 본문을 들여쓰기하여 중첩 된 구조를 더 읽기 쉽게 만드는 것이 일반적입니다. 통합 개발 환경(IDE) 편집기는 자동으로 이 작업을 수행합니다.  
  
 다음 예제에서 프로시저는 `sumRows` 행렬의 각 행의 양수 요소를 함께 추가합니다.  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 앞의 예제에서 첫 `Next` 번째 문은 내부 `For` 루프를 `Next` 닫고 마지막 `For` 문은 외부 루프를 닫습니다.  
  
 마찬가지로 중첩 된 `If` 문에서 `End If` 문은 가장 가까운 이전 `If` 문에 자동으로 적용됩니다. 중첩 `Do` 루프는 가장 안쪽 문과 일치하는 `Loop` `Do` 가장 안쪽 문과 비슷한 방식으로 작동합니다.  
  
> [!NOTE]
> 많은 컨트롤 구조의 경우 키워드를 클릭하면 구조의 모든 키워드가 강조 표시됩니다. 예를 들어 구성을 `If` `If...Then...Else` 클릭하면 `If`구성의 모든 `Then` `ElseIf` `Else` `End If` 인스턴스가 강조 표시됩니다. 강조 표시된 다음 또는 이전 키워드로 이동하려면 CTRL+SHIFT+DOWN 화살표 또는 CTRL+SHIFT+UP 화살표를 누릅니다.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>다양한 종류의 제어 구조 중첩  
 한 종류의 제어 구조를 다른 종류 내에 중첩할 수 있습니다. 다음 예제에서는 `With` `For Each` 루프 내부의 블록과 `If` `With` 블록 내부에 중첩된 블록을 사용합니다.  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>겹치는 제어 구조  
 컨트롤 구조를 겹칠 수 없습니다. 즉, 중첩된 구조는 가장 안쪽 의 구조 내에 완전히 포함되어야 합니다. 예를 들어 내부 `For` `With` 블록이 종료되기 전에 루프가 종료되므로 다음 배열이 잘못되었습니다.  
  
 ![잘못된 중첩의 예를 보여 주는 다이어그램입니다.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Visual Basic 컴파일러는 이러한 겹치는 제어 구조를 감지하고 컴파일 타임 오류를 신호합니다.  
  
## <a name="see-also"></a>참고 항목

- [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [루프 구조체](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
