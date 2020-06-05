---
title: 재정의
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392030"
---
# <a name="overrides-visual-basic"></a>Overrides(Visual Basic)

속성 또는 프로시저가 기본 클래스에서 상속된 이름이 같은 속성 또는 프로시저를 재정의하도록 지정합니다.

## <a name="rules"></a>규칙

- **선언 컨텍스트.** `Overrides`속성 또는 프로시저 선언 문에서만를 사용할 수 있습니다.

- **결합된 한정자.** `Overrides` `Shadows` 동일한 선언에서 또는를 함께 지정할 수 없습니다 `Shared` . 재정의 요소는 암시적으로 재정의할 수 있으므로 `Overridable`과 `Overrides`를 결합할 수 없습니다.

- **일치하는 서명.** 이 선언의 서명은 재정의 하는 속성 또는 프로시저의 *시그니처와* 정확히 일치 해야 합니다. 즉, 매개 변수 목록에 동일한 데이터 형식의 매개 변수가 동일한 개수 및 순서로 포함되어야 합니다.

  서명 외에도 재정의 선언이 다음과 정확히 일치해야 합니다.

  - 액세스 수준

  - 반환 형식(있는 경우)

- **제네릭 서명.** 제네릭 프로시저의 경우 서명에 형식 매개 변수 개수가 포함됩니다. 따라서 해당 측면에서도 재정의 선언이 기본 클래스 버전과 일치해야 합니다.

- **추가 일치.** 기본 클래스 버전과의 서명 일치 외에도 이 선언은 다음 측면에서 기본 클래스 버전과 일치해야 합니다.

  - 액세스 수준 한정자 (예: [Public](public.md))

  - 각 매개 변수의 전달 메커니즘 ([ByVal](byval.md) 또는 [ByRef](byref.md))

  - 제네릭 프로시저의 각 형식 매개 변수에 대한 제약 조건 목록

- **숨김 및 재정의.** 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.

`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.

`Overrides` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

- [Function 문](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Sub 문](../statements/sub-statement.md)

## <a name="see-also"></a>참고 항목

- [New](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overrides](overridable.md)
- [C++ 키워드](../keywords/index.md)
- [Visual Basic에서 숨김](../../programming-guide/language-features/declared-elements/shadowing.md)
- [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
