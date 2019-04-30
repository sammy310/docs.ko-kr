---
title: Class 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 68401571645d77a41b827c13b3cfc3674076e218
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945043"
---
# <a name="class-statement-visual-basic"></a>Class 문(Visual Basic)
클래스의 이름을 선언 하 고 변수, 속성, 이벤트 및 클래스를 구성 하는 프로시저의 정의 소개 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attributelist`|선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.|  
|`accessmodifier`|선택 사항입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private Protected](../../language-reference/modifiers/private-protected.md)<br/><br/> [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|  
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|  
|`MustInherit`|선택 사항입니다. 참조 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.|  
|`NotInheritable`|선택 사항입니다. 참조 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)합니다.|  
|`Partial`|선택 사항입니다. 클래스의 부분 정의 나타냅니다. 참조 [부분](../../../visual-basic/language-reference/modifiers/partial.md)합니다.|  
|`name`|필수 요소. 이 클래스의 이름입니다. [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|  
|`Of`|선택 사항입니다. 제네릭 클래스 임을 지정 합니다.|  
|`typelist`|사용 하는 경우 필요 합니다 [의](../../../visual-basic/language-reference/statements/of-clause.md) 키워드입니다. 이 클래스에 대 한 형식 매개 변수의 목록입니다. 참조 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.|  
|`Inherits`|선택 사항입니다. 이 클래스의 다른 클래스 멤버를 상속 함을 나타냅니다. 참조 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)합니다.|  
|`classname`|사용 하는 경우 필요 합니다 `Inherits` 문입니다. 이 클래스가 파생 되는 클래스의 이름입니다.|  
|`Implements`|선택 사항입니다. 이 클래스의 하나 이상의 인터페이스 멤버를 구현 함을 나타냅니다. 참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.|  
|`interfacenames`|사용 하는 경우 필요 합니다 `Implements` 문입니다. 이 클래스를 구현 하는 인터페이스의 이름입니다.|  
|`statements`|선택 사항입니다. 이 클래스의 멤버를 정의 하는 문입니다.|  
|`End Class`|필수 요소. 종료는 `Class` 정의 합니다.|  
  
## <a name="remarks"></a>설명  
 `Class` 문은 새 데이터 형식을 정의 합니다. A *클래스* 은 개체 지향 프로그래밍 (OOP)의 기본 빌딩 블록입니다. 자세한 내용은 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
 사용할 수 있습니다 `Class` 네임 스페이스 또는 모듈 수준 에서만. 즉, 합니다 *선언 컨텍스트* 클래스 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스 여야 하 고 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 클래스의 각 인스턴스 수명이 다른 모든 인스턴스도 무관 합니다. 이 수명에서 만들어질 때 시작 되는 [New 연산자](../../../visual-basic/language-reference/operators/new-operator.md) 절 또는와 같은 함수에 의해 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. 인스턴스를 가리키는 모든 변수를 설정한 될 때 끝납니다 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 다른 클래스의 인스턴스.  
  
 클래스는 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다. 액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다. 자세한 내용은 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="rules"></a>규칙  
  
- **중첩 합니다.** 다른 내에서 하나의 클래스를 정의할 수 있습니다. 외부 클래스 라고 합니다 *클래스를 포함 하*, 내부 클래스 라고는 *중첩 된 클래스*합니다.  
  
- **상속.** 클래스를 사용 하는 경우는 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), 하나의 기본 클래스 또는 인터페이스를 지정할 수 있습니다. 클래스는 둘 이상의 요소에서 상속할 수 없습니다.  
  
     클래스는 더 제한적인 액세스 수준 가진 다른 클래스에서 상속할 수 없습니다. 예를 들어, 한 `Public` 클래스에서 상속할 수 없습니다는 `Friend` 클래스입니다.  
  
     클래스는 그 안에 중첩 된 클래스에서 상속할 수 없습니다.  
  
- **구현입니다.** 클래스를 사용 하는 경우는 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)에서 지정 하는 모든 인터페이스에 의해 정의 된 모든 멤버를 구현 해야 `interfacenames`합니다. 이 예외는 기본 클래스 멤버의 구현을 다시 수행 합니다. 자세한 내용은 "다시 구현"를 참조 하세요 [구현](../../../visual-basic/language-reference/statements/implements-clause.md)합니다.  
  
- **기본 속성입니다.** 클래스에서는 하나 이상의 속성으로 지정할 수는 *속성의 기본값을*입니다. 자세한 내용은 [기본](../../../visual-basic/language-reference/modifiers/default.md)입니다.  
  
## <a name="behavior"></a>동작  
  
- **액세스 수준입니다.** 클래스 내의 자체 액세스 수준이 있는 각 멤버를 선언할 수 있습니다. 클래스 멤버는 기본적으로 [공개](../../../visual-basic/language-reference/modifiers/public.md) 변수와 상수를 제외 하 고는 기본적으로 액세스 [개인](../../../visual-basic/language-reference/modifiers/private.md) 액세스 합니다. 클래스에 보다 제한적인 해당 멤버 중 하나를 클래스 액세스 수준은 우선적으로 적용 합니다.  
  
- **범위입니다.** 클래스는 해당 포함 된 네임 스페이스, 클래스, 구조체 또는 모듈 전체 범위입니다.  
  
     모든 클래스 멤버의 범위는 전체 클래스입니다.  
  
     **수명입니다.** Visual Basic에서 정적 클래스를 지원 하지 않습니다. 정적 클래스의 상응 모듈에 의해 제공 됩니다. 자세한 내용은 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)합니다.  
  
     클래스 멤버에는 선언 방법 및 위치에 따라 유효 기간이 있습니다. 자세한 내용은 [Visual Basic의 수명](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)합니다.  
  
- **정규화 합니다.** 클래스 외부 코드 멤버의 이름을 해당 클래스의 이름으로 한 정해야 합니다.  
  
     중첩 된 클래스 내의 코드는 프로그래밍 요소를 비 정규화 된 참조를 만드는 경우 Visual Basic 요소에 대해 먼저 검색을 포함 하는 클래스에 다음 중첩된 클래스에서 등 포함 하는 가장 바깥쪽 요소를 합니다.  
  
## <a name="classes-and-modules"></a>클래스와 모듈  
 이러한 요소는 비슷한 점이 많이 몇 가지 중요 한 차이점도 있습니다.  
  
- **용어입니다.** 이전 버전의 Visual Basic 등 두 유형의 모듈로 인식: *클래스 모듈* (.cls 파일) 및 *표준 모듈* (.bas 파일). 현재 버전에서는 이러한 *클래스* 하 고 *모듈*, 각각.  
  
- **공유 멤버입니다.** 공유 클래스의 멤버 인지 또는 인스턴스 멤버를 제어할 수 있습니다.  
  
- **개체 방향입니다.** 클래스는 개체 지향 되지만 모듈이 없습니다. 클래스의 인스턴스가 하나 이상 만들 수 있습니다. 자세한 내용은 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Class` 을 클래스와 몇 가지 멤버를 정의 합니다.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>참고자료

- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [구조체와 클래스](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)
- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
- [개체 수명: 개체가 만들어지고 제거 하는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
