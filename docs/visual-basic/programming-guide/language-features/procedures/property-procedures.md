---
description: '자세한 정보: 속성 프로시저 (Visual Basic)'
title: 속성 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: 55588278cdb8423a4f13a4e7ecc02f7ea692a618
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466590"
---
# <a name="property-procedures-visual-basic"></a>Property 프로시저(Visual Basic)

속성 프로시저는 모듈, 클래스 또는 구조체의 사용자 지정 속성을 조작 하는 일련의 Visual Basic 문입니다. 속성 프로시저를 *속성 접근자* 라고도 합니다.

Visual Basic는 다음 속성 프로시저를 제공 합니다.

- `Get`프로시저는 속성의 값을 반환 합니다. 식의 속성에 액세스할 때 호출 됩니다.
- `Set`프로시저는 개체 참조를 포함 하 여 속성을 값으로 설정 합니다. 속성에 값을 할당할 때 호출 됩니다.

일반적으로 및 문을 사용 하 여 속성 프로시저를 쌍으로 정의 `Get` `Set` 하지만 속성이 읽기 전용 ([Get 문](../../../language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([Set 문](../../../language-reference/statements/set-statement.md)) 인 경우에만 프로시저를 정의할 수 있습니다.

`Get` `Set` 자동 구현 속성을 사용 하는 경우 및 프로시저를 생략할 수 있습니다. 자세한 내용은 [자동으로 구현된 속성](./auto-implemented-properties.md)을 참조하세요.

클래스, 구조체 및 모듈에서 속성을 정의할 수 있습니다. 속성은 `Public` 기본적으로 이므로 속성의 컨테이너에 액세스할 수 있는 응용 프로그램의 어디에서 나 호출할 수 있습니다.

속성과 변수를 비교 하는 방법에 대 한 자세한 내용은 [Visual Basic의 속성과 변수 간의 차이점](differences-between-properties-and-variables.md)을 참조 하세요.

## <a name="declaration-syntax"></a>선언 구문

속성 자체는 [속성 문과](../../../language-reference/statements/property-statement.md) 문 내에 포함 된 코드 블록에 의해 정의 됩니다 `End Property` . 이 블록 내에서 각 속성 프로시저는 선언 문 ( `Get` 또는 `Set` ) 및 일치 하는 선언 내에 포함 된 내부 블록으로 나타납니다 `End` .

속성 및 해당 프로시저를 선언 하는 구문은 다음과 같습니다.

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

는 `Modifiers` 오버 로드, 재정의, 공유 및 숨김과 관련 된 액세스 수준 및 정보와 속성이 읽기 전용 이거나 쓰기 전용인 지 여부에 대 한 정보를 지정할 수 있습니다. `AccessLevel` `Get` 또는 프로시저의는 `Set` 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적인 수준이 될 수 있습니다. 자세한 내용은 [Property 문](../../../language-reference/statements/property-statement.md)을 참조 하세요.

### <a name="data-type"></a>데이터 형식

속성의 데이터 형식 및 보안 주체 액세스 수준은 `Property` 속성 프로시저가 아닌 문에 정의 됩니다. 속성에는 데이터 형식이 하나만 있을 수 있습니다. 예를 들어 값을 저장 하 고 값을 검색 하는 속성을 정의할 수 없습니다 `Decimal` `Double` .

### <a name="access-level"></a>액세스 수준

그러나 속성의 보안 주체 액세스 수준을 정의 하 고 속성 프로시저 중 하나에서 액세스 수준을 추가로 제한할 수 있습니다. 예를 들어 속성을 정의한 `Public` 다음 프로시저를 정의할 수 있습니다 `Private Set` . `Get`프로시저는 그대로 유지 `Public` 됩니다. 속성의 프로시저 중 하나 에서만 액세스 수준을 변경할 수 있으며, 보안 주체 액세스 수준 보다 제한적 으로만 설정할 수 있습니다. 자세한 내용은 [방법: 액세스 수준이 혼합 된 속성 선언](how-to-declare-a-property-with-mixed-access-levels.md)을 참조 하세요.

## <a name="parameter-declaration"></a>매개 변수 선언

전달 메커니즘이 여야 한다는 점을 제외 하 고 [하위 프로시저](sub-procedures.md)와 동일한 방식으로 각 매개 변수를 선언 합니다 `ByVal` .

매개 변수 목록의 각 매개 변수에 대 한 구문은 다음과 같습니다.

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

매개 변수가 선택 사항인 경우에는 해당 선언의 일부로도 기본값을 제공 해야 합니다. 기본값을 지정 하는 구문은 다음과 같습니다.

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a>속성 값

프로시저에서 `Get` 반환 값은 속성 값으로 호출 식에 제공 됩니다.

프로시저에서 `Set` 새 속성 값은 문의 매개 변수로 전달 됩니다 `Set` . 매개 변수를 명시적으로 선언 하는 경우에는 속성과 동일한 데이터 형식을 사용 하 여 선언 해야 합니다. 매개 변수를 선언 하지 않으면 컴파일러는 암시적 매개 변수를 사용 하 여 `Value` 속성에 할당 되는 새 값을 나타냅니다.

## <a name="calling-syntax"></a>호출 구문

속성을 참조 하 여 암시적으로 속성 프로시저를 호출 합니다. 변수 이름을 사용 하는 것과 동일한 방식으로 속성의 이름을 사용 합니다. 단, 선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다. 인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.

프로시저에 대 한 암시적 호출 구문은 `Set` 다음과 같습니다.

```vb
propertyname[(argumentlist)] = expression
```

프로시저에 대 한 암시적 호출 구문은 `Get` 다음과 같습니다.

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>선언 및 호출에 대 한 그림

다음 속성은 이름, 이름 및 성 이라는 두 가지 구성 이름으로 전체 이름을 저장 합니다. 호출 코드가 읽는 경우 `fullName` `Get` 프로시저는 두 가지 구성 이름을 결합 하 고 전체 이름을 반환 합니다. 호출 코드에서 새 전체 이름을 할당 하면 `Set` 프로시저는 두 개의 구성 된 이름으로 코드를 분리 하려고 시도 합니다. 공백을 찾지 못하면 모두 이름으로 저장 합니다.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

다음 예에서는의 속성 프로시저에 대 한 일반적인 호출을 보여 줍니다 `fullName` .

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>추가 정보

- [절차](index.md)
- [함수 프로시저](function-procedures.md)
- [연산자 프로시저](operator-procedures.md)
- [프로시저 매개 변수 및 인수](procedure-parameters-and-arguments.md)
- [Visual Basic에서 속성과 변수의 차이점](differences-between-properties-and-variables.md)
- [방법: 속성 만들기](how-to-create-a-property.md)
- [방법: 속성 프로시저 호출](how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](how-to-get-a-value-from-a-property.md)
