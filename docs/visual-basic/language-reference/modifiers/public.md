---
title: Public
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351289"
---
# <a name="public-visual-basic"></a>Public(Visual Basic)
하나 이상의 선언 된 프로그래밍 요소에 액세스 제한이 없도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 클래스 라이브러리와 같은 구성 요소 또는 구성 요소 집합을 게시 하는 경우 일반적으로 어셈블리와 상호 작용 하는 코드에서 프로그래밍 요소에 액세스할 수 있도록 합니다. 요소에 대 한 무제한 액세스를 설정 하기 위해 `Public`를 사용 하 여 선언할 수 있습니다.  
  
 공용 액세스는 프로그래밍 요소에 대 한 액세스를 제한 하지 않아도 되는 일반적인 수준입니다. 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언 된 요소에 대 한 액세스 수준은 기본적으로 `Public` (그렇지 않은 경우)로 선언 됩니다.  
  
## <a name="rules"></a>규칙  
  
- **선언 컨텍스트입니다.** `Public`는 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다. 즉, `Public` 요소에 대 한 선언 컨텍스트는 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 하 고 프로시저일 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
- **액세스 수준입니다.** 모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 `Public` 요소에 액세스할 수 있습니다.  
  
- **기본 액세스.** 프로시저 내의 지역 변수는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.  
  
- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다. 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
 `Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고자료

- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
