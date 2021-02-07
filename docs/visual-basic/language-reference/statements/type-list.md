---
description: '자세한 정보: 형식 목록 (Visual Basic)'
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: d4c8bcab4a39af0ac0747d6be0d04408edd98a55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740901"
---
# <a name="type-list-visual-basic"></a>형식 목록(Visual Basic)

*제네릭* 프로그래밍 요소에 대 한 *형식 매개 변수* 를 지정 합니다. 여러 매개 변수는 쉼표로 구분 됩니다. 다음은 하나의 형식 매개 변수에 대 한 구문입니다.

## <a name="syntax"></a>Syntax

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>부분

|용어|정의|
|---|---|
|`genericmodifier`|선택 사항입니다. 제네릭 인터페이스 및 대리자 에서만 사용할 수 있습니다. In 키워드를 사용 하 여 [Out](../modifiers/out-generic-modifier.md) 키워드나 반공 변을 사용 하 여 형식을 공변 [(](../modifiers/in-generic-modifier.md) covariant)으로 선언할 수 있습니다. [공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.|
|`typename`|필수 사항입니다. 형식 매개 변수의 이름입니다. 해당 형식 인수가 제공 하는 정의 된 형식으로 대체 될 자리 표시자입니다.|
|`constraintlist`|선택 사항입니다. 에 대해 제공할 수 있는 데이터 형식을 제한 하는 요구 사항 목록입니다 `typename` . 제약 조건이 여러 개인 경우 중괄호 ()로 묶고 쉼표를 `{ }` 사용 하 여 구분 합니다. 제약 조건 목록에 [As](as-clause.md) 키워드를 사용 해야 합니다. `As`목록의 시작 부분에는 한 번만 사용 합니다.|

## <a name="remarks"></a>설명

모든 제네릭 프로그래밍 요소는 하나 이상의 형식 매개 변수를 사용 해야 합니다. 형식 매개 변수는 클라이언트 코드에서 제네릭 형식의 인스턴스를 만들 때 지정 하는 특정 형식 ( *생성 된 요소*)에 대 한 자리 표시자입니다. 제네릭 클래스, 구조체, 인터페이스, 프로시저 또는 대리자를 정의할 수 있습니다.

제네릭 형식을 정의 하는 경우에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)을 참조 하세요. 형식 매개 변수 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.

## <a name="rules"></a>규칙

- **괄호.** 형식 매개 변수 목록을 제공 하는 경우 괄호로 묶어야 합니다 .이 목록에는 [Of](of-clause.md) 키워드를 사용 해야 합니다. `Of`목록의 시작 부분에는 한 번만 사용 합니다.

- **적용.** 형식 매개 변수에 대 한 *제약 조건* 목록에는 다음과 같은 항목이 조합 되어 포함 될 수 있습니다.

  - 인터페이스 수 제한 없음 제공 된 형식은이 목록의 모든 인터페이스를 구현 해야 합니다.

  - 최대 하나의 클래스입니다. 제공 된 형식은 해당 클래스에서 상속 해야 합니다.

  - `New` 키워드. 제공 된 형식은 제네릭 형식에서 액세스할 수 있는 매개 변수가 없는 생성자를 노출 해야 합니다. 이는 하나 이상의 인터페이스로 형식 매개 변수를 제한 하는 경우에 유용 합니다. 인터페이스를 구현 하는 형식이 반드시 생성자를 노출 하는 것은 아니며, 생성자의 액세스 수준에 따라 제네릭 형식 내의 코드에서 액세스 하지 못할 수도 있습니다.

  - `Class`키워드나 키워드 중 하나 `Structure` 입니다. `Class`키워드는 제네릭 형식 매개 변수에 전달 된 형식 인수가 문자열, 배열 또는 대리자와 같은 참조 형식 이거나 클래스에서 만든 개체를 참조 형식으로 요구 하도록 제한 합니다. `Structure`키워드는 제네릭 형식 매개 변수에 전달 된 형식 인수가 값 형식 (예: 구조체, 열거형 또는 기본 데이터 형식)이 되도록 제약을 받도록 제한 합니다. `Class`와 `Structure` 는 모두 동일한에 포함할 수 없습니다 `constraintlist` .

  제공 된 형식은에 포함 하는 모든 요구 사항을 충족 해야 합니다 `constraintlist` .

  각 형식 매개 변수에 대 한 제약 조건은 다른 형식 매개 변수에 대 한 제약 조건과는 독립적입니다.

## <a name="behavior"></a>동작

- **컴파일 시간 대체입니다.** 제네릭 프로그래밍 요소에서 생성 된 형식을 만들 때 각 형식 매개 변수에 대해 정의 된 형식을 제공 합니다. Visual Basic 컴파일러는 제네릭 요소 내의 모든 항목에 대해 제공 된 형식을 대체 합니다 `typename` .

- **제약 조건이 없습니다.** 형식 매개 변수에 대 한 제약 조건을 지정 하지 않으면 해당 형식 매개 변수에 대 한 [개체 데이터 형식](../data-types/object-data-type.md) 에서 지 원하는 작업 및 멤버로 코드가 제한 됩니다.

## <a name="example"></a>예제

다음 예제에서는 사전에 새 항목을 추가 하는 기본 함수를 포함 하 여 제네릭 사전 클래스의 기본 정의를 보여 줍니다.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>예제

는 일반적 이므로이를 `dictionary` 사용 하는 코드는 동일한 기능을 갖지만 다른 데이터 형식에서 작동 하는 다양 한 개체를 만들 수 있습니다. 다음 예제에서는 `dictionary` 항목 및 키를 사용 하 여 개체를 만드는 코드 줄을 보여 줍니다 `String` `Integer` .

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>예제

다음 예제에서는 앞의 예제에서 생성 된 해당 하는 기본 정의를 보여 줍니다.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>참고 항목

- [으로](of-clause.md)
- [New 연산자](../operators/new-operator.md)
- [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Object Data Type](../data-types/object-data-type.md)
- [Function 문](function-statement.md)
- [Structure 문](structure-statement.md)
- [Sub 문](sub-statement.md)
- [방법: 제네릭 클래스 사용](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [공 분산 및 반공 분산](../../programming-guide/concepts/covariance-contravariance/index.md)
- [위치](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
