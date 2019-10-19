---
title: GoTo 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581811"
---
# <a name="goto-statement"></a>GoTo 문
프로시저에서 지정 된 줄로 무조건 분기 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>파트  
 `line`  
 필수 요소. 모든 줄 레이블입니다.  
  
## <a name="remarks"></a>주의  
 @No__t_0 문은 표시 되는 프로시저의 줄로만 분기할 수 있습니다. 줄에는 `GoTo` 참조할 수 있는 줄 레이블이 있어야 합니다. 자세한 내용은 [방법: 레이블 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)을 참조 하세요.  
  
> [!NOTE]
> `GoTo` 문을 사용 하면 코드를 읽고 유지 관리 하기 어려울 수 있습니다. 가능 하면 컨트롤 구조를 대신 사용 합니다. 자세한 내용은 [제어 흐름](../../../visual-basic/programming-guide/language-features/control-flow/index.md)을 참조 하세요.  
  
 @No__t_0 문을 사용 하 여 `For` 외부에서 분기할 수 없습니다. `Next`, `For Each` ... `Next`, `SyncLock` ... `End SyncLock`, `Try` ... `Catch` ... `Finally`, 0 ... 1 또는 2 ... 내의 레이블에 3 생성  
  
## <a name="branching-and-try-constructions"></a>분기 및 시도 생성  
 @No__t_0 내에서 ... `Catch` ... `Finally` 생성에서는 `GoTo` 문으로 분기 하는 데 다음 규칙이 적용 됩니다.  
  
|블록 또는 지역|외부에서 분기|내부에서 외부 분기|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` 블록|동일한 <sup>생성의</sup> `Catch` 블록 에서만|전체 생성 외부에만|  
|`Catch` 블록|허용 되지 않음|전체 <sup>생성 외부 또는 동일한 생성의</sup> `Try` 블록에만 해당|  
|`Finally` 블록|허용 되지 않음|허용 되지 않음|  
  
 <sup>1</sup> `Try` 한 경우 `Catch` ... `Finally` 생성은 `Catch` 다른 `Try` 블록에 포함 되지 않고 자체 중첩 수준에서 `Try` 블록으로 분기할 수 있습니다. 중첩 된 `Try` ... `Catch` ... `Finally` 생성은 중첩 된 생성의 `Try` 또는 `Catch` 블록에 완전히 포함 되어야 합니다.  
  
 다음 그림에서는 서로 중첩 된 하나의 `Try` 생성을 보여 줍니다. 두 생성의 블록 사이에 있는 다양 한 분기가 유효 하거나 유효 하지 않은 것으로 표시 됩니다.  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>예제  
 다음 예에서는 `GoTo` 문을 사용 하 여 프로시저의 줄 레이블로 분기 합니다.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>참조

- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [With...End With 문](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
