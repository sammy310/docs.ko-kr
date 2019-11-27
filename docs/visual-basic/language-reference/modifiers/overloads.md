---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 44823b409cfa81dc889aabacf101fac90bf851e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351405"
---
# <a name="overloads-visual-basic"></a>Overloads(Visual Basic)

속성 또는 프로시저에서 하나 이상의 기존 속성 또는 프로시저를 같은 이름으로 다시 선언할 수 있도록 지정합니다.

## <a name="remarks"></a>주의

*오버 로드* 는 동일한 범위에서 지정 된 속성 또는 프로시저 이름에 대 한 정의를 두 개 이상 제공 하는 방법입니다. 서명이 다른 속성 또는 프로시저를 *서명으로*다시 선언할 하는 경우도 있습니다.

## <a name="rules"></a>규칙

- **선언 컨텍스트입니다.** `Overloads`는 속성 또는 프로시저 선언문 에서만 사용할 수 있습니다.

- **결합 된 한정자입니다.** 동일한 프로시저 선언에서 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md) 와 함께 `Overloads`를 지정할 수 없습니다.

- **필요한 차이점.** 이 선언의 *시그니처* 는 오버 로드 되는 모든 속성 또는 프로시저의 서명과 달라 야 합니다. 서명은 다음 항목과 함께 속성 또는 프로시저 이름으로 구성됩니다.

  - 매개 변수 수

  - 매개 변수의 순서

  - 매개 변수의 데이터 형식

  - 형식 매개 변수의 수(제네릭 프로시저의 경우)

  - 반환 형식(변환 연산자 프로시저의 경우만)

  모든 오버로드는 이름이 같아야 하지만 앞에서 설명한 하나 이상의 측면과 관련하여 각각은 다른 모든 오버로드와 달라야 합니다. 그러면 컴파일러가 코드에서 속성 또는 프로시저를 호출할 때 사용할 버전을 구분할 수 있습니다.

- **허용 되지 않는 차이점입니다.** 다음 중 하나 이상은 서명의 일부가 아니므로 속성 또는 프로시저를 오버로드하기 위해 변경할 수 없습니다.

  - 값을 반환하는지 여부(프로시저의 경우)

  - 반환 값의 데이터 형식(변환 연산자 제외)

  - 매개 변수 또는 형식 매개 변수의 이름

  - 형식 매개 변수에 대한 제약 조건(제네릭 프로시저의 경우)

  - 매개 변수 한정자 키워드(예: `ByRef` 또는 `Optional`)

  - 속성 또는 프로시저 한정자 키워드(예: `Public` 또는 `Shared`)

- **선택적 한정자입니다.** 동일한 클래스에서 여러 오버 로드 된 속성 또는 프로시저를 정의 하는 경우에는 `Overloads` 한정자를 사용할 필요가 없습니다. 그러나 선언 중 하나에서 `Overloads`를 사용하는 경우에는 모든 선언에서 사용해야 합니다.

- **숨김 및 오버 로드.** `Overloads`를 사용 하 여 기본 클래스에서 기존 멤버 또는 오버 로드 된 멤버 집합을 숨길 수도 있습니다. 이런 방식으로 `Overloads`를 사용하는 경우 기본 클래스 멤버와 동일한 이름 및 동일한 매개 변수 목록을 사용하여 속성 또는 메서드를 선언하고 `Shadows` 키워드는 제공하지 않습니다.

`Overrides`를 사용하는 경우 라이브러리 API가 보다 쉽게 C#으로 작업할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.

`Overloads` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)

- [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)

- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>참고 항목

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [프로시저 오버로딩](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
