---
title: Continue 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835390"
---
# <a name="continue-statement-visual-basic"></a>Continue 문(Visual Basic)
루프의 다음 반복으로 즉시 제어를 전송 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>설명  
 전송할 수 있습니다 내부를 `Do`, `For`, 또는 `While` 루프의 다음 반복 루프입니다. 제어를 전송 하는 것과 같은 루프 조건 테스트를 즉시 전달 합니다 `For` 또는 `While` 문 또는 `Do` 또는 `Loop` 문을 포함 하는 `Until` 또는 `While` 절.  
  
 사용할 수 있습니다 `Continue` 전송 허용 되는 루프의 모든 위치에 있습니다. 컨트롤의 전송을 허용 규칙은 동일 하 게 합니다 [GoTo 문](../../../visual-basic/language-reference/statements/goto-statement.md)합니다.  
  
 예를 들어 루프 내에 완전히 포함 되어는 `Try` 블록을 `Catch` 블록 또는 `Finally` 블록을 사용할 수 있습니다 `Continue` 루프 밖으로 전송할 합니다. 반면, 경우에는 `Try`... `End Try` 루프 내에서 포함 된 구조를 사용할 수 없습니다 `Continue` 밖으로 제어를 전송 하는 `Finally` 블록 하는 데 사용할 수 / 전송를 `Try` 또는 `Catch` 개 완전히 전송 하는 경우에 차단 합니다 `Try`... `End Try` 구조입니다.  
  
 동일한 형식의 중첩 된 루프 예를 들어 있는지를 `Do` 루프 내에서 다른 `Do` 루프를 `Continue Do` 문은 가장 안쪽의 다음 반복으로 건너뜁니다 `Do` 포함 하는 루프입니다. 사용할 수 없습니다 `Continue` 동일한 형식의 포함 된 루프의 다음 반복으로 건너뛸 수 있습니다.  
  
 다양 한 유형의 중첩 된 루프 예를 들어 있는지를 `Do` 내에서 반복을 `For` 루프를 건너뛸 수 있습니다 하거나 루프의 다음 반복을 사용 하 여 `Continue Do` 또는 `Continue For`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Continue While` 제수가 0 인 경우 배열에 포함 된 다음 열을 건너뛰려면 문입니다. 합니다 `Continue While` 안에 `For` 루프입니다. 전송 된 `While col < lastcol` 가장 안쪽의 다음 반복 문을 `While` 포함 하는 루프를 `For` 루프입니다.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>참고자료

- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
