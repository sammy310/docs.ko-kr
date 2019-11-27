---
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
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333010"
---
# <a name="return-statement-visual-basic"></a>Return 문(Visual Basic)
`Function`, `Sub`, `Get`, `Set`또는 `Operator` 프로시저를 호출한 코드에 대 한 제어를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>파트  
 `expression`  
 `Function`, `Get`또는 `Operator` 프로시저에 필요 합니다. 호출 코드에 반환 될 값을 나타내는 식입니다.  
  
## <a name="remarks"></a>주의  
 `Sub` 또는 `Set` 프로시저에서 `Return` 문은 `Exit Sub` 또는 `Exit Property` 문과 같으며 `expression`를 제공 하지 않아야 합니다.  
  
 `Function`, `Get`또는 `Operator` 프로시저에서 `Return` 문은 `expression`을 포함 해야 하며 `expression`는 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다. `Function` 또는 `Get` 프로시저에서는 프로시저 이름에 식을 할당 하 여 반환 값으로 사용 하 고 `Exit Function` 또는 `Exit Property` 문을 실행 하는 방법도 사용할 수 있습니다. `Operator` 프로시저에서는 `Return expression`를 사용 해야 합니다.  
  
 동일한 프로시저에 필요한 만큼 `Return` 문을 포함할 수 있습니다.  
  
> [!NOTE]
> `Finally` 블록의 코드는 `Try` 또는 `Catch` 블록에서 `Return` 문이 발생 한 후에 실행 되지만 해당 `Return` 문이 실행 되기 전에 실행 됩니다. `Finally` 블록에는 `Return` 문을 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 프로시저에서 다른 작업을 수행할 필요가 없을 때 `Return` 문을 여러 번 사용 하 여 호출 코드로 돌아갑니다.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>참고 항목

- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
