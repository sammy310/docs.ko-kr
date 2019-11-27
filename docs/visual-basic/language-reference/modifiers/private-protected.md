---
title: 비공개 보호
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351338"
---
# <a name="private-protected-visual-basic"></a>개인 보호 (Visual Basic)

`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다. `Private Protected` 멤버는 포함 하는 클래스의 모든 멤버 뿐 아니라 포함 하는 클래스에서 파생 된 형식 뿐만 아니라 포함 하는 어셈블리에 있는 경우에만 액세스할 수 있습니다.

`Private Protected`는 클래스의 멤버에만 지정할 수 있습니다. 구조체는 상속 될 수 없으므로 구조체의 멤버에 `Private Protected`을 적용할 수 없습니다.

`Private Protected` 액세스 한정자는 Visual Basic 15.5 이상에서 지원 됩니다. 이를 사용 하려면 Visual Basic 프로젝트 (\*.vbproj) 파일에 다음 요소를 추가 하면 됩니다. Visual Basic 15.5 이상이 시스템에 설치 되어 있으면 최신 버전의 Visual Basic 컴파일러에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

자세한 내용은 [Visual Basic 언어 버전 설정](../../language-reference/configure-language-version.md)을 참조 하세요.

> [!NOTE]
> Visual Studio에서는 `private protected`에 대 한 F1 도움말을 선택 하 여 [개인](private.md) 또는 [보호 된](protected.md)에 대 한 도움말을 제공 합니다. IDE는 복합 단어가 아니라 커서에서 단일 토큰을 선택 합니다.

## <a name="rules"></a>규칙

- **선언 컨텍스트입니다.** 클래스 수준 에서만 `Private Protected`를 사용할 수 있습니다. 즉, `Protected` 요소에 대 한 선언 컨텍스트는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.

## <a name="behavior"></a>동작

- **액세스 수준입니다.** 클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다. 기본 클래스에서 파생 되 고 동일한 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스의 모든 `Private Protected` 요소에 액세스할 수 있습니다. 그러나 기본 클래스에서 파생 되 고 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스 `Private Protected` 요소에 액세스할 수 없습니다.

- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다. 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.

`Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

- 중첩 된 클래스의 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)

- 클래스에 중첩 된 대리자의 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)

- 클래스에 중첩 된 열거형의 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)

- 클래스에 중첩 된 인터페이스의 [인터페이스 문](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)

- 클래스에 중첩 된 구조체의 [구조체 문](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>참고자료

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Protected Friend](./protected-friend.md)
- [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
