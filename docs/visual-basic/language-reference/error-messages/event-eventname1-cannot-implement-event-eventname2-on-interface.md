---
title: 대리자 형식 '<eventname1>'과(와) '<eventname2>'이(가) 일치하지 않으므로 '<interface>' 이벤트에서 '<delegate1>' 인터페이스에 대해 '<delegate2>' 이벤트를 구현할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 3ec3e7bb2f28bf8c4dd38bc71e11193456860021
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379759"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>이벤트 '\<행사 이름 1 >' 이벤트를 구현할 수 없습니다. '\<eventname2 >' 인터페이스의 '\<인터페이스 >' 때문에 해당 대리자 형식\<delegate1 >' 및 '\<delegate2 >' 일치 하지 않습니다
이벤트의 대리자 형식과 인터페이스에서 이벤트의 대리자 형식과 일치 하지 않으므로 Visual Basic에서 이벤트를 구현할 수 없습니다. 이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다. 구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.  
  
 **오류 ID:** BC31423  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이벤트를 개별적으로 구현합니다.  
  
     또는  
  
-   사용 하는 인터페이스의 이벤트를 정의 합니다 `As` 구문 동일한 대리자 형식을 지정 합니다.  
  
## <a name="see-also"></a>참고자료
- [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)
- [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
