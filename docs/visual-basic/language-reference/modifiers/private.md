---
description: '자세히 알아보기: 개인 (Visual Basic)'
title: 비공개
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 20dcd943856e20ccb1b7cb5c0603fa5f313d2421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700951"
---
# <a name="private-visual-basic"></a>Private(Visual Basic)

하나 이상의 선언 된 프로그래밍 요소를 포함 된 형식 내에서 포함 하 여 해당 선언 컨텍스트 내 에서만 액세스할 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  

 프로그래밍 요소가 독점적인 기능을 나타내거나 기밀 데이터를 포함 하는 경우 일반적으로 해당 요소에 대 한 액세스를 최대한 엄격 하 게 제한 하려고 합니다. 모듈, 클래스 또는 구조체를 정의 하는 구조체를 사용 하 여 액세스할 수 있도록 허용 하 여 최대 제한을 달성할 수 있습니다. 이러한 방식으로 요소에 대 한 액세스를 제한 하려면로 선언할 수 있습니다 `Private` .  

> [!NOTE]
> [Private Protected](private-protected.md) 액세스 한정자를 사용 하 여 해당 클래스 내에서, 그리고 포함 하는 어셈블리에 있는 파생 클래스에서 멤버에 액세스할 수 있게 할 수도 있습니다.

## <a name="rules"></a>규칙  

- **선언 컨텍스트.** `Private`는 모듈 수준에서만 사용할 수 있습니다. 즉, 요소에 대 한 선언 컨텍스트는 `Private` 모듈, 클래스 또는 구조체 여야 하며 소스 파일, 네임 스페이스, 인터페이스 또는 프로시저일 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
- **액세스 수준입니다.** 선언 컨텍스트 내의 모든 코드는 해당 요소에 액세스할 수 있습니다 `Private` . 여기에는 중첩 된 클래스 또는 열거형의 할당 식과 같은 포함 된 형식 내의 코드가 포함 됩니다. 선언 컨텍스트 외부에 있는 코드는 해당 요소에 액세스할 수 없습니다 `Private` .  
  
- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드를 *액세스 한정자* 라고 합니다. 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
 `Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../statements/class-statement.md)  
  
 [Const 문](../statements/const-statement.md)  
  
 [Declare 문](../statements/declare-statement.md)  
  
 [Delegate 문](../statements/delegate-statement.md)  
  
 [Dim 문](../statements/dim-statement.md)  
  
 [Enum 문](../statements/enum-statement.md)  
  
 [Event 문](../statements/event-statement.md)  
  
 [Function 문](../statements/function-statement.md)  
  
 [Interface 문](../statements/interface-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure 문](../statements/structure-statement.md)  
  
 [Sub 문](../statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [공용](public.md)
- [보호됨](protected.md)
- [Friend](friend.md)
- [비공개 보호](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../programming-guide/language-features/procedures/index.md)
- [구조체](../../programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)
