---
title: Protected(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 88e13fcd03c6a10cf1450cec90f9ca60aedc3eb1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819166"
---
# <a name="protected-visual-basic"></a>Protected(Visual Basic)
멤버 액세스 한정자는 하나 이상의 선언 된 프로그래밍 요소를 지정 하는 고유한 클래스 내부나 파생 클래스에서 에서만 액세스할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 중요 한 데이터 나 제한 된 코드를 클래스에 선언 된 프로그래밍 요소를 포함 하는 경우도 있습니다 및 요소에 대 한 액세스를 제한 하려면. 그러나 클래스를 상속할 수 없는 경우 파생된 클래스의 계층 구조를 원하는 코드나 데이터에 액세스 하기 위해 이러한 파생된 클래스에 대 한 할 수 있습니다. 이러한 경우 요소 기본 클래스 및 모든 파생된 클래스에서 모두 액세스할 수 있도록 해야 합니다. 이 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Protected`합니다.  

> [!NOTE]
> `Protected` 액세스 한정자는 다른 두 한정자와 결합할 수 있습니다.
> - 합니다 [Protected Friend](protected-friend.md) 한정자 클래스 멤버를 해당 클래스의 파생된 클래스에서 클래스가 정의 되어 있는 동일한 어셈블리 내에서 액세스할 수 있게 합니다. 
> - 합니다 [Private Protected](private-protected.md) 한정자 클래스 멤버에 액세스할 수 있도록 포함 된 어셈블리 내 에서만 파생된 형식에서입니다.
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 사용할 수 있습니다 `Protected` 클래스 수준에만 합니다. 즉, 선언 컨텍스트는 `Protected` 요소 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.  

## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 클래스의 모든 코드가 해당 요소에 액세스할 수 있습니다. 모든 기본 클래스에서 파생 되는 모든 클래스의 코드에 액세스할 수는 `Protected` 요소의 기본 클래스입니다. 모든 세대의 파생에 대 한 마찬가지입니다. 즉, 클래스에 액세스할 수 있도록 `Protected` 요소의 기본 클래스 등의 기본 클래스입니다.  
  
     보호 된 액세스는 상위 또는 하위 집합 friend 액세스 하지 않습니다.  
  
-   **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 액세스 한정자와 비교 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고자료

- [공용](../../../visual-basic/language-reference/modifiers/public.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [전용](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
