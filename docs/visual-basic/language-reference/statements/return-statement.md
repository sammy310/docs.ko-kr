---
description: '자세한 정보: Return 문 (Visual Basic)'
title: Return 문
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 62086090ede7e634b09d3edc3dc42feb28d15793
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741200"
---
# <a name="return-statement-visual-basic"></a>Return 문(Visual Basic)

`Function`,, `Sub` `Get` , `Set` 또는 `Operator` 프로시저를 호출한 코드로 제어를 반환 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>파트  

 `expression`  
 `Function`, `Get` 또는 프로시저에 필요 `Operator` 합니다. 호출 코드에 반환 될 값을 나타내는 식입니다.  
  
## <a name="remarks"></a>설명  

 `Sub`또는 프로시저에서 `Set` `Return` 문은 `Exit Sub` 또는 `Exit Property` 문과 같으며 `expression` 제공 되지 않아야 합니다.  
  
 `Function`, `Get` 또는 `Operator` 프로시저에서 `Return` 문은를 포함 해야 `expression` 하며, `expression` 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다. `Function`또는 프로시저에서 `Get` 프로시저 이름에 식을 할당 하 여 반환 값으로 사용 하 고 또는 문을 실행 하는 방법도 있습니다 `Exit Function` `Exit Property` . 프로시저에서 `Operator` 를 사용 해야 `Return expression` 합니다.  
  
 `Return`동일한 프로시저에 적절 한 수의 문을 포함할 수 있습니다.  
  
> [!NOTE]
> 블록의 코드는 `Finally` `Return` 또는 블록의 문이 발견 된 후에 실행 되며 `Try` `Catch` 해당 문이 실행 되기 전에 실행 됩니다 `Return` . `Return`문은 블록에 포함 될 수 없습니다 `Finally` .  
  
## <a name="example"></a>예제  

 다음 예제에서는 `Return` 문을 여러 번 사용 하 여 프로시저에서 다른 작업을 수행할 필요가 없을 때 호출 코드로 돌아갑니다.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>참고 항목

- [Function 문](function-statement.md)
- [Sub 문](sub-statement.md)
- [Get 문](get-statement.md)
- [Set 문](set-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Exit 문](exit-statement.md)
- [Try...Catch...Finally 문](try-catch-finally-statement.md)
