---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402709"
---
# <a name="shadows-visual-basic"></a>Shadows(Visual Basic)

선언 된 프로그래밍 요소가 기본 클래스에서 동일 하 게 명명 된 요소 또는 오버 로드 된 요소 집합을 요소가 하 고 숨기도록 지정 합니다.

## <a name="remarks"></a>설명

숨김 ( *이름으로 숨기기*라고도 함)의 주요 용도는 클래스 멤버의 정의를 유지 하는 것입니다. 기본 클래스는 이미 정의한 것과 동일한 이름으로 요소를 만드는 변경 될 수 있습니다. 이 경우 `Shadows` 한정자는 클래스를 통해 참조가 새 기본 클래스 요소가 아닌 사용자가 정의한 멤버로 확인 되도록 합니다.

숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.

## <a name="rules"></a>규칙

- **선언 컨텍스트.** 는 `Shadows` 클래스 수준 에서만 사용할 수 있습니다. 즉, 요소에 대 한 선언 컨텍스트는 `Shadows` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.

  단일 선언문에서 하나의 섀도잉 요소만 선언할 수 있습니다.

- **결합된 한정자.** `Shadows` `Overloads` `Overrides` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Static` .

- **요소 형식.** 모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다. 다른 속성이 나 프로시저를 사용 하 여 속성 또는 프로시저를 숨기는 경우 매개 변수와 반환 형식이 기본 클래스 속성 또는 프로시저의 매개 변수와 일치 하지 않아도 됩니다.

- **하.** 기본 클래스의 숨겨진 요소는 일반적으로 해당 요소를 숨기는 파생 클래스 내에서 사용할 수 없습니다. 그러나 다음 고려 사항이 적용 됩니다.

  - 해당 요소를 참조 하는 코드에서 숨기는 요소에 액세스할 수 없는 경우 참조는 숨겨진 요소로 확인 됩니다. 예를 들어 `Private` 요소가 기본 클래스 요소를 숨기는 경우 요소에 액세스할 수 있는 권한이 없는 코드는 `Private` 대신 기본 클래스 요소에 액세스 합니다.

  - 요소를 숨기는 경우에도 기본 클래스의 형식으로 선언 된 개체를 통해 숨겨진 요소에 액세스할 수 있습니다. 를 통해 액세스할 수도 있습니다 `MyBase` .

`Shadows` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

- [Class 문](../statements/class-statement.md)

- [Const 문](../statements/const-statement.md)

- [Declare 문](../statements/declare-statement.md)

- [Delegate 문](../statements/delegate-statement.md)

- [Dim 문](../statements/dim-statement.md)

- [Enum 문](../statements/enum-statement.md)

- [Event 문](../statements/event-statement.md)

- [Function 문](../statements/function-statement.md)

- [Interface 문](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Structure 문](../statements/structure-statement.md)

- [Sub 문](../statements/sub-statement.md)

## <a name="see-also"></a>참고 항목

- [공유](shared.md)
- [정적](static.md)
- [프라이빗](private.md)
- [Me, My, MyBase 및 MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [상속 기본 사항](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [New](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [오버로드](overloads.md)
- [Overrides](overridable.md)
- [재정의](overrides.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
