---
title: Continue 문
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: cf73ea1b3d402609c9966980dcab9ddd9bc096c2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874973"
---
# <a name="continue-statement-visual-basic"></a>Continue 문(Visual Basic)

루프의 다음 반복으로 즉시 제어를 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>설명  

 `Do`, `For` 또는 루프 내에서 `While` 해당 루프의 다음 반복으로 전송할 수 있습니다. 제어는 `For` 또는 문으로 전송 하거나 `While` `Do` `Loop` 또는 절이 포함 된 또는 문으로 루프 `Until` 조건 테스트에 즉시 전달 됩니다 `While` .  
  
 `Continue`전송을 허용 하는 루프의 모든 위치에서을 사용할 수 있습니다. 제어를 전송할 수 있도록 허용 하는 규칙은 [GoTo 문과](goto-statement.md)동일 합니다.  
  
 예를 들어 루프가 블록, 블록 또는 블록 내에 완전히 포함 된 경우를 `Try` `Catch` `Finally` 사용 `Continue` 하 여 루프 밖으로 전송할 수 있습니다. 반면, `Try` ... 구조체가 루프 내에 포함 된 경우를 `End Try` 사용 하 여 제어를 블록 밖으로 전송 하 고,이를 사용 하 여 또는 블록 밖으로 전송 하는 경우에 `Continue` `Finally` `Try` `Catch` 만 또는 블록 `Try` `End Try` 외부로 전송할 수 있습니다.  
  
 다른 루프 내의 루프와 같이 동일한 형식의 루프를 중첩 하는 경우 `Do` `Do` 문은 해당 루프를 `Continue Do` `Do` 포함 하는 가장 안쪽 루프의 다음 반복으로 건너뜁니다. 를 사용 하 여 `Continue` 같은 형식의 포함 하는 루프의 다음 반복으로 건너뛸 수는 없습니다.  
  
 루프 내에서 루프와 같이 다양 한 형식의 루프를 중첩 한 경우 `Do` `For` 또는를 사용 하 여 두 루프의 다음 반복으로 건너뛸 수 있습니다 `Continue Do` `Continue For` .  
  
## <a name="example"></a>예제  

 다음 코드 예제에서는 문을 사용 하 여 `Continue While` 제수가 0 인 경우 배열의 다음 열로 건너뜁니다. `Continue While`가 루프 내에 `For` 있습니다. `While col < lastcol`루프를 포함 하는 가장 안쪽 루프의 다음 반복 인 문으로 전송 합니다 `While` `For` .  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>참조

- [Do...Loop 문](do-loop-statement.md)
- [For...Next 문](for-next-statement.md)
- [While...End While 문](while-end-while-statement.md)
- [Try ... Catch ... Finally 문](try-catch-finally-statement.md)
