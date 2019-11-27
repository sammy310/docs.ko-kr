---
title: Continue 문
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 20140cafb68c7e5518bf3d5fa80e56ca1c1de2c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354118"
---
# <a name="continue-statement-visual-basic"></a>Continue 문(Visual Basic)
루프의 다음 반복으로 즉시 제어를 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>주의  
 `Do`, `For`또는 `While` 루프 내에서 해당 루프의 다음 반복으로 전송할 수 있습니다. 컨트롤은 루프 조건 테스트에 즉시 전달 됩니다 .이 테스트는 `For` 또는 `While` 문으로 전송 하거나 `Until` 또는 `While` 절이 포함 된 `Do` 또는 `Loop` 문으로 전송 하는 것과 같습니다.  
  
 전송을 허용 하는 루프의 모든 위치에서 `Continue`를 사용할 수 있습니다. 제어를 전송할 수 있도록 허용 하는 규칙은 [GoTo 문과](../../../visual-basic/language-reference/statements/goto-statement.md)동일 합니다.  
  
 예를 들어 루프가 `Try` 블록, `Catch` 블록 또는 `Finally` 블록 내에 완전히 포함 되는 경우 `Continue`를 사용 하 여 루프 밖으로 전송할 수 있습니다. 반면에 `Try`...`End Try` 구조체가 루프 내에 포함 된 경우에는 `Continue`를 사용 하 여 제어를 `Finally` 블록 외부로 전송할 수 없으며이를 사용 하 여 `Try` `Catch` 구조에서 완전히 전송 하는 경우에만 `Try`또는`End Try` 블록 밖으로 전송할 수 있습니다.  
  
 다른 `Do` 루프 내에 `Do` 루프와 같은 형식의 중첩 루프가 있는 경우 `Continue Do` 문은 해당 루프를 포함 하는 가장 안쪽의 `Do` 루프의 다음 반복으로 건너뜁니다. `Continue`를 사용 하 여 같은 형식의 포함 루프의 다음 반복으로 건너뛸 수는 없습니다.  
  
 `For` 루프 내에 `Do` 루프와 같이 다양 한 형식의 루프를 중첩 하는 경우 `Continue Do` 또는 `Continue For`를 사용 하 여 두 루프의 다음 반복으로 건너뛸 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Continue While` 문을 사용 하 여 제수가 0 인 경우 배열의 다음 열로 건너뜁니다. `Continue While` `For` 루프 내에 있습니다. `For` 루프를 포함 하는 가장 안쪽의 `While` 루프의 다음 반복 인 `While col < lastcol` 문으로 전송 합니다.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>참고 항목

- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
