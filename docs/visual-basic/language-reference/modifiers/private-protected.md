---
title: 비공개 보호
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303467"
---
# <a name="private-protected-visual-basic"></a>개인 보호 (Visual Basic)

`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다. 멤버는 포함 하는 `Private Protected` 클래스의 모든 멤버 뿐 아니라 포함 하는 클래스에서 파생 된 형식 뿐만 아니라 포함 하는 어셈블리에 있는 경우에만 액세스할 수 있습니다.

클래스의 멤버만 지정할 수 있습니다. 구조체 `Private Protected` `Private Protected` 는 상속 될 수 없으므로 구조체의 멤버에는 적용할 수 없습니다.

`Private Protected`액세스 한정자는 Visual Basic 15.5 이상에서 지원 됩니다. 이를 사용 하려면 Visual Basic 프로젝트 (.vbproj) 파일에 다음 요소를 추가 하면 \* 됩니다. Visual Basic 15.5 이상이 시스템에 설치 되어 있으면 최신 버전의 Visual Basic 컴파일러에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

자세한 내용은 [Visual Basic 언어 버전 설정](../configure-language-version.md)을 참조 하세요.

> [!NOTE]
> Visual Studio에서 F1 도움말을 선택 하 여 `private protected` [개인](private.md) 또는 [보호 된](protected.md)에 대 한 도움말을 제공 합니다. IDE는 복합 단어가 아니라 커서에서 단일 토큰을 선택 합니다.

## <a name="rules"></a>규칙

- **선언 컨텍스트.** `Private Protected`는 클래스 수준 에서만 사용할 수 있습니다. 즉, 요소에 대 한 선언 컨텍스트는 `Protected` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.

## <a name="behavior"></a>동작

- **액세스 수준입니다.** 클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다. 기본 클래스에서 파생 되 고 동일한 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스의 모든 요소에 액세스할 수 있습니다 `Private Protected` . 그러나 기본 클래스에서 파생 되 고 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스 요소에 액세스할 수 없습니다 `Private Protected` .

- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다. 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.

`Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

- 중첩 된 클래스의 [Class 문](../statements/class-statement.md)

- [Const 문](../statements/const-statement.md)

- [Declare 문](../statements/declare-statement.md)

- 클래스에 중첩 된 대리자의 [Delegate 문](../statements/delegate-statement.md)

- [Dim 문](../statements/dim-statement.md)

- 클래스에 중첩 된 열거형의 [Enum 문](../statements/enum-statement.md)

- [Event 문](../statements/event-statement.md)

- [Function 문](../statements/function-statement.md)

- 클래스에 중첩 된 인터페이스의 [인터페이스 문](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- 클래스에 중첩 된 구조체의 [구조체 문](../statements/structure-statement.md)

- [Sub 문](../statements/sub-statement.md)

## <a name="see-also"></a>참고 항목

- [공용](public.md)
- [보호](protected.md)
- [Friend](friend.md)
- [프라이빗](private.md)
- [Protected Friend](./protected-friend.md)
- [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)
- [절차](../../programming-guide/language-features/procedures/index.md)
- [구조체](../../programming-guide/language-features/data-types/structures.md)
- [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)
