---
title: 공용
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: f2b6a126435b111ef56ee2a9870ea6fbddf87901
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867689"
---
# <a name="public-visual-basic"></a>Public(Visual Basic)

하나 이상의 선언 된 프로그래밍 요소에 액세스 제한이 없도록 지정 합니다.  
  
## <a name="remarks"></a>설명  

 클래스 라이브러리와 같은 구성 요소 또는 구성 요소 집합을 게시 하는 경우 일반적으로 어셈블리와 상호 작용 하는 코드에서 프로그래밍 요소에 액세스할 수 있도록 합니다. 요소에 대 한 무제한 액세스를 설정 하려면를 사용 하 여 선언 하면 `Public` 됩니다.  
  
 공용 액세스는 프로그래밍 요소에 대 한 액세스를 제한 하지 않아도 되는 일반적인 수준입니다. 선언 하지 않으면 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언 된 요소의 액세스 수준이 기본적으로로 설정 `Public` 됩니다.  
  
## <a name="rules"></a>규칙  
  
- **선언 컨텍스트.** 는 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다. 즉, 요소에 대 한 선언 컨텍스트는 `Public` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 하며 프로시저 일 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
- **액세스 수준입니다.** 모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 요소에 액세스할 수 있습니다 `Public` .  
  
- **기본 액세스.** 프로시저 내의 지역 변수는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.  
  
- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다. 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
 `Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../statements/class-statement.md)  
  
 [Const 문](../statements/const-statement.md)  
  
 [Declare 문](../statements/declare-statement.md)  
  
 [Delegate 문](../statements/delegate-statement.md)  
  
 [Dim 문](../statements/dim-statement.md)  
  
 [Enum 문](../statements/enum-statement.md)  
  
 [Event 문](../statements/event-statement.md)  
  
 [Function 문](../statements/function-statement.md)  
  
 [Interface 문](../statements/interface-statement.md)  
  
 [Module 문](../statements/module-statement.md)  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure 문](../statements/structure-statement.md)  
  
 [Sub 문](../statements/sub-statement.md)  
  
## <a name="see-also"></a>참조

- [보호](protected.md)
- [Friend](friend.md)
- [개인](private.md)
- [개인 보호](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../programming-guide/language-features/procedures/index.md)
- [구조체](../../programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)
