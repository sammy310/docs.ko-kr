---
title: With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873848"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>With' 문 내부에서만 '.' 또는 '!'로 시작할 수 있습니다.

블록 내에 없는 마침표 (.) 또는 느낌표 (!)는 `With` 왼쪽에 식 없이 발생 합니다. 멤버 액세스 ( `.` ) 및 사전 멤버 액세스 ( `!` )에는 멤버가 포함 된 요소를 지정 하는 식이 필요 합니다. 이는 접근자의 왼쪽에 바로 나타나거나 `With` 멤버 액세스를 포함 하는 블록의 대상으로 나타나야 합니다.  
  
 **오류 ID:** BC30157  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. `With`블록의 형식이 올바르게 지정 되었는지 확인 합니다.  
  
2. 블록이 없으면 멤버를 `With` 포함 하는 정의 된 요소로 계산 되는 식을 접근자의 왼쪽에 추가 합니다.  
  
## <a name="see-also"></a>참조

- [코드의 특수 문자](../../programming-guide/program-structure/special-characters-in-code.md)
- [With...End With 문](../statements/with-end-with-statement.md)
