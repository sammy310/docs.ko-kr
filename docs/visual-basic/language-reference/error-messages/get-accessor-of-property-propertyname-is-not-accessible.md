---
title: "'<propertyname>' 속성의 'Get' 접근자에 액세스할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 08986cde7151cac5e70083705f38a83837bedb93
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874045"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a>'\<propertyname>' 속성의 'Get' 접근자에 액세스할 수 없습니다.

문이 속성의 프로시저에 대 한 액세스 권한이 없는 경우 속성의 값을 검색 하려고 시도 합니다 `Get` .  
  
 [Get 문이](../statements/get-statement.md) [property 문](../statements/property-statement.md)보다 더 제한적인 액세스 수준으로 표시 되 면 다음과 같은 경우에 속성 값을 읽으려고 할 수 있습니다.  
  
- `Get`문이 [Private](../modifiers/private.md) 으로 표시 되 고 호출 코드가 속성이 정의 된 클래스 또는 구조체 외부에 있습니다.  
  
- `Get`문이 [Protected](../modifiers/protected.md) 로 표시 되어 있고 호출 코드가 속성이 정의 된 클래스 또는 구조체에 없거나 파생 클래스에 없는 경우  
  
- `Get`문이 [Friend](../modifiers/friend.md) 로 표시 되어 있고 호출 코드가 속성이 정의 된 어셈블리와 동일 하지 않습니다.  
  
 **오류 ID:** BC31103  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 속성을 정의 하는 소스 코드를 제어할 수 있는 경우 `Get` 속성 자체와 동일한 액세스 수준을 사용 하 여 프로시저를 선언 하는 것이 좋습니다.  
  
- 속성을 정의 하는 소스 코드를 제어할 수 없거나 `Get` 프로시저 액세스 수준을 속성 자체 보다 더 제한 해야 하는 경우 속성 값을 읽는 문을 속성에 대 한 액세스를 향상 하는 코드 영역으로 이동 합니다.  
  
## <a name="see-also"></a>참조

- [속성 프로시저](../../programming-guide/language-features/procedures/property-procedures.md)
- [방법: 액세스 수준이 혼합된 속성 선언](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
