---
description: '다음에 대 한 자세한 정보: GoTo 문'
title: GoTo 문
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
ms.openlocfilehash: 804baec130111562225b09cbdc7b5fb2d73adba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769054"
---
# <a name="goto-statement"></a>GoTo 문

프로시저에서 지정 된 줄로 무조건 분기 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>파트  

 `line`  
 필수 사항입니다. 모든 줄 레이블입니다.  
  
## <a name="remarks"></a>설명  

 `GoTo`문은 표시 되는 프로시저의 줄로만 분기할 수 있습니다. 줄에는를 참조할 수 있는 줄 레이블이 있어야 합니다 `GoTo` . 자세한 내용은 [방법: 레이블 문](../../programming-guide/program-structure/how-to-label-statements.md)을 참조 하세요.  
  
> [!NOTE]
> `GoTo` 문을 사용 하면 코드를 읽고 유지 관리 하기 어려울 수 있습니다. 가능 하면 컨트롤 구조를 대신 사용 합니다. 자세한 내용은 [Control Flow](../../programming-guide/language-features/control-flow/index.md)을 참조하세요.  
  
 문을 사용 하 여 (..., ..., ..., ... `GoTo` `For` `Next` `For Each` `Next` `SyncLock` `End SyncLock` , `Try` `Catch` ...) 외부에서 분기할 수 없습니다. ... `Finally` , `With` ... `End With` 또는 `Using` ... `End Using` 생성이 내부 레이블에 있습니다.  
  
## <a name="branching-and-try-constructions"></a>분기 및 시도 생성  

 내 ... `Try` `Catch` ...`Finally` 다음 규칙은 문을 사용 하 여 분기에 적용 `GoTo` 됩니다.  
  
|블록 또는 지역|외부에서 분기|내부에서 외부 분기|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` 거부|`Catch`같은 생성의 블록 에서만 <sup>1</sup>|전체 생성 외부에만|  
|`Catch` 거부|허용 되지 않음|전체 생성 외부 또는 `Try` 동일한 생성의 블록 <sup></sup> 에만 해당|  
|`Finally` 거부|허용 되지 않음|허용 되지 않음|  
  
 <sup>1</sup> 일 경우 `Try` `Catch` ...`Finally` 생성은 다른 중첩 수준에서 중첩 되 고 `Catch` `Try` 다른 블록에는 포함 되지 않을 수 있습니다 `Try` . 중첩 된 ... `Try` `Catch` ...`Finally` 생성 `Try` 은 중첩 된 생성의 또는 블록에 완전히 포함 되어야 합니다 `Catch` .  
  
 다음 그림에서는 `Try` 다른 중첩 내에 중첩 된 하나의 생성을 보여 줍니다. 두 생성의 블록 사이에 있는 다양 한 분기가 유효 하거나 유효 하지 않은 것으로 표시 됩니다.  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>예제  

 다음 예에서는 문을 사용 하 여 `GoTo` 프로시저의 줄 레이블로 분기 합니다.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>참고 항목

- [Do...Loop 문](do-loop-statement.md)
- [For...Next 문](for-next-statement.md)
- [For Each...Next 문](for-each-next-statement.md)
- [If...Then...Else 문](if-then-else-statement.md)
- [Select...Case 문](select-case-statement.md)
- [Try...Catch...Finally 문](try-catch-finally-statement.md)
- [While...End While 문](while-end-while-statement.md)
- [With...End With 문](with-end-with-statement.md)
