---
description: '자세히 알아보기: Property 문'
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 95f2ac1f993fc8698d2033dfe50d925cd55a7dc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741395"
---
# <a name="property-statement"></a>Property Statement

속성의 이름과 속성 값을 저장 하 고 검색 하는 데 사용 되는 속성 프로시저를 선언 합니다.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a>부분

- `attributelist`

  선택 사항입니다. 이 속성 또는 프로시저에 적용 되는 특성의 목록입니다 `Get` `Set` . [특성 목록](attribute-list.md)을 참조 하십시오.

- `Default`

  선택 사항입니다. 이 속성이 정의 된 클래스 또는 구조체에 대 한 기본 속성 임을 지정 합니다. 기본 속성은 매개 변수를 허용 해야 하며 속성 이름을 지정 하지 않고 설정 하 고 검색할 수 있습니다. 속성을로 선언 하는 경우 속성 `Default` 또는 속성 프로시저 중 하나에서을 사용할 수 없습니다 `Private` .

- `accessmodifier`

  `Property`문과 및 문 중 하나 이상에 대 한 선택 사항 `Get` 입니다 `Set` . 다음 중 하나일 수 있습니다.

  - [공용](../modifiers/public.md)

  - [보호됨](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [개인](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [비공개 보호](../modifiers/private-protected.md)

  [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.

- `propertymodifiers`

  선택 사항입니다. 다음 중 하나일 수 있습니다.

  - [오버로드](../modifiers/overloads.md)

  - [재정의](../modifiers/overrides.md)

  - [Overrides](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [New](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  선택 사항입니다. [공유](../modifiers/shared.md)를 참조 하세요.

- `Shadows`

  선택 사항입니다. [그림자](../modifiers/shadows.md)를 참조 하세요.

- `ReadOnly`

  선택 사항입니다. [ReadOnly](../modifiers/readonly.md)를 참조 하세요.

- `WriteOnly`

  선택 사항입니다. [WriteOnly](../modifiers/writeonly.md)를 참조 하세요.

- `Iterator`

  선택 사항입니다. [반복기](../modifiers/iterator.md)를 참조 하세요.

- `name`

  필수 사항입니다. 속성의 이름입니다. [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.

- `parameterlist`

  선택 사항입니다. 이 속성의 매개 변수를 나타내는 지역 변수 이름과 프로시저의 가능한 추가 매개 변수를 나타내는 목록입니다 `Set` . [매개 변수 목록](parameter-list.md)을 참조 하세요.

- `returntype`

  필요한 경우 `Option Strict` 는 `On`합니다. 이 속성에서 반환 하는 값의 데이터 형식입니다.

- `Implements`

  선택 사항입니다. 이 속성이이 속성의 포함 클래스 또는 구조체에서 구현 하는 인터페이스에 각각 정의 된 하나 이상의 속성을 구현 함을 나타냅니다. [Implements 문](implements-statement.md)을 참조 하세요.

- `implementslist`

  `Implements`가 제공된 경우 필수입니다. 구현 중인 속성의 목록입니다.

  `implementedproperty [ , implementedproperty ... ]`

  각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.

  `interface.definedname`

  |파트|설명|
  |---|---|
  |`interface`|필수 사항입니다. 이 속성에 포함 된 클래스 또는 구조체에 의해 구현 된 인터페이스의 이름입니다.|
  |`definedname`|필수 사항입니다. 속성이에서 정의 되는 이름 `interface` 입니다.|

- `Get`

  선택 사항입니다. 속성이로 표시 된 경우 필수 `ReadOnly` 입니다. `Get`속성의 값을 반환 하는 데 사용 되는 속성 프로시저를 시작 합니다.  `Get`문은 [자동으로 구현 된 속성과](../../programming-guide/language-features/procedures/auto-implemented-properties.md)함께 사용 되지 않습니다.

- `statements`

  선택 사항입니다. 또는 프로시저 내에서 실행할 문 블록 `Get` 입니다 `Set` .

- `End Get`

  `Get`속성 프로시저를 종료 합니다.

- `Set`

  선택 사항입니다. 속성이로 표시 된 경우 필수 `WriteOnly` 입니다. `Set`속성의 값을 저장 하는 데 사용 되는 속성 프로시저를 시작 합니다.  `Set`문은 [자동으로 구현 된 속성과](../../programming-guide/language-features/procedures/auto-implemented-properties.md)함께 사용 되지 않습니다.

- `End Set`

  `Set`속성 프로시저를 종료 합니다.

- `End Property`

  이 속성의 정의를 종료 합니다.

## <a name="remarks"></a>설명

`Property`문은 속성의 선언을 소개 합니다. 속성에는 `Get` 프로시저 (읽기 전용), `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기/쓰기)를 사용할 수 있습니다. `Get` `Set` 자동 구현 속성을 사용 하는 경우 및 프로시저를 생략할 수 있습니다. 자세한 내용은 [자동으로 구현된 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.

는 `Property` 클래스 수준 에서만 사용할 수 있습니다. 즉, 속성에 대 한 *선언 컨텍스트* 는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.

기본적으로 속성은 공용 액세스를 사용 합니다. 문의 액세스 한정자를 사용 하 여 속성의 액세스 수준을 조정 하 `Property` 고 필요에 따라 속성 프로시저 중 하나를 더 제한적인 액세스 수준으로 조정할 수 있습니다.

Visual Basic는 속성을 할당 하는 동안 매개 변수를 프로시저에 전달 `Set` 합니다. 에 대 한 매개 변수를 제공 하지 않으면 `Set` IDE (통합 개발 환경)에서 라는 암시적 매개 변수를 사용 합니다 `value` . 이 매개 변수는 속성에 할당 되는 값을 포함 합니다. 일반적으로이 값을 private 지역 변수에 저장 하 고 프로시저가 호출 될 때마다 반환 `Get` 합니다.

## <a name="rules"></a>규칙

- **혼합 액세스 수준.** 읽기/쓰기 속성을 정의 하는 경우 필요에 따라 또는 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있습니다 `Get` `Set` . 이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다. 예를 들어 속성이 선언 된 경우 `Friend` 프로시저를 선언할 수 있지만는 선언할 수 `Set` `Private` 없습니다 `Public` .

  또는 속성을 정의 하는 경우 `ReadOnly` `WriteOnly` 단일 속성 프로시저 ( `Get` 또는 `Set` 각각)는 속성을 모두 나타냅니다. 속성에 대해 두 개의 액세스 수준을 설정 하므로 프로시저에 대해 다른 액세스 수준을 선언할 수 없습니다.

- **반환 형식입니다.** `Property`문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.

  을 지정 하지 않으면 `returntype` 속성은을 반환 합니다 `Object` .

- **구현이.** 이 속성이 키워드를 사용 하는 경우 `Implements` 포함 하는 클래스 또는 구조체에는 `Implements` 또는 문 바로 다음에 문이 있어야 합니다 `Class` `Structure` . `Implements`문에는에 지정 된 각 인터페이스가 포함 되어야 합니다 `implementslist` . 그러나 인터페이스에서 (의)를 정의 하는 이름은 `Property` `definedname` 이 속성의 이름과 같을 필요가 없습니다 `name` .

## <a name="behavior"></a>동작

- **속성 프로시저에서 반환** `Get`또는 `Set` 프로시저가 호출 코드에 반환 되 면 실행 되는 문 다음에 오는 문을 실행 합니다.

  `Exit Property`및 `Return` 문을 실행 하면 속성 프로시저에서 즉시 종료 됩니다. 프로시저의 모든 위치에는 개수와 `Exit Property` `Return` 문이 모두 표시 될 수 있으며 `Exit Property` 문과 문을 혼합할 수 있습니다 `Return` .

- **반환 값입니다.** 프로시저에서 값을 반환 하려면 `Get` 속성 이름에 값을 할당 하거나 문에 해당 값을 포함 하면 됩니다 `Return` . 다음 예에서는 반환 값을 속성 이름에 할당 한 `quoteForTheDay` 다음 문을 사용 하 여를 `Exit Property` 반환 합니다.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  `Exit Property`에 값을 할당 하지 않고를 사용 하는 경우이 `name` `Get` 프로시저는 속성의 데이터 형식에 대 한 기본값을 반환 합니다.

  `Return`명령문은 `Get` 프로시저 반환 값을 할당 하 고 프로시저를 종료 합니다. 다음 예에서는 이러한 방법을 보여 줍니다.

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a>예제

다음 예제에서는 클래스의 속성을 선언 합니다.

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a>참고 항목

- [자동으로 구현된 속성](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)
- [Get 문](get-statement.md)
- [Set 문](set-statement.md)
- [매개 변수 목록](parameter-list.md)
- [기본값](../modifiers/default.md)
