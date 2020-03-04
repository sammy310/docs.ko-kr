---
title: 구조체 형식 - C# 참조
ms.date: 02/24/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 6113912f176d2d7b68c77ff2e78a361b373ca31a
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634640"
---
# <a name="structure-types-c-reference"></a>구조체 형식(C# 참조)

‘구조체 형식’은 데이터와 관련 기능을 캡슐화할 수 있는 [값 형식](value-types.md)입니다.   구조체 형식은 `struct` 키워드를 사용하여 정의합니다.

[!code-csharp[struct example](~/samples/csharp/language-reference/builtin-types/StructType.cs#StructExample)]

구조체 형식은 ‘값 의미 체계’를 갖습니다.  즉, 구조체 형식의 변수는 해당 형식의 인스턴스를 포함합니다. 기본적으로 변수 값은 할당 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다. 구조체 형식 변수의 경우, 해당 형식의 인스턴스가 복사됩니다. 자세한 내용은 [값 형식](value-types.md)을 참조하세요.

구조체 형식은 일반적으로 동작을 거의 제공하지 않거나 전혀 제공하지 않는 작은 데이터 중심 형식을 설계하는 데 사용합니다. 예를 들어, .NET에서는 구조체 형식을 사용하여 숫자([정수](integral-numeric-types.md)와 [실수](floating-point-numeric-types.md)), [부울 값](bool.md), [유니코드 문자](char.md), [시간 인스턴스](xref:System.DateTime)를 표현합니다. 형식의 동작이 중요한 경우에는 [클래스](../keywords/class.md)를 정의하는 것이 좋습니다. 클래스 형식은 ‘참조 의미 체계’를 갖습니다.  즉, 클래스 형식의 변수는 인스턴스 자체가 아닌 해당 형식의 인스턴스에 대한 참조를 포함합니다.

## <a name="limitations-with-the-design-of-a-structure-type"></a>구조체 형식 설계의 제한 사항

구조체 형식을 설계할 때는 [클래스](../keywords/class.md) 형식과 같은 기능을 사용할 수 있으나, 다음과 같은 예외가 적용됩니다.

- 매개 변수가 없는 생성자를 선언할 수 없습니다. 모든 구조체 형식은 이미 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자를 제공합니다.

- 인스턴스 필드 또는 속성은 선언과 동시에 초기화할 수 없습니다. 단, [static](../keywords/static.md) 또는 [const](../keywords/const.md) 필드 또는 정적 속성은 선언과 동시에 초기화할 수 있습니다.

- 구조체 형식의 생성자는 해당 형식의 모든 인스턴스 필드를 초기화해야 합니다.

- 구조체 형식은 다른 클래스 또는 구조체 형식에서 상속할 수 없으며, 클래스의 기본이 될 수 없습니다. 단, 구조체 형식은 [인터페이스](../keywords/interface.md)를 구현할 수 있습니다.

- 구조체 형식 내에서 [종료자](../../programming-guide/classes-and-structs/destructors.md)를 선언할 수 없습니다.

## <a name="instantiation-of-a-structure-type"></a>구조체 형식의 인스턴스화

C#에서는 선언된 변수를 사용하려면 먼저 초기화해야 합니다. 구조체 형식 변수는 `null`일 수 없으므로([nulla 허용 변수 값 형식](nullable-value-types.md)의 변수인 경우 제외), 해당 형식의 인스턴스를 인스턴스화해야 합니다. 이 작업은 몇 가지 방법으로 수행할 수 있습니다.

일반적으로, 구조체 형식은 [`new`](../operators/new-operator.md) 연산자를 사용하여 적절한 생성자를 호출함으로써 인스턴스화합니다. 모든 구조체 형식은 하나 이상의 생성자를 갖습니다. 이는 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자입니다. [default](../operators/default.md) 연산자 또는 리터럴을 사용하여 해당 형식의 기본값을 생성할 수도 있습니다.

구조체 형식의 모든 인스턴스 필드가 액세스 가능한 경우, `new` 연산자 없이 인스턴스화할 수도 있습니다. 이 경우 인스턴스를 처음 사용하기 전에 모든 인스턴스 필드를 초기화해야 합니다. 다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.

[!code-csharp[without new](~/samples/csharp/language-reference/builtin-types/StructType.cs#WithoutNew)]

[기본 제공 값 형식](value-types.md#built-in-value-types)의 경우, 해당 리터럴을 사용하여 해당 형식의 값을 지정합니다.

## <a name="passing-structure-type-variables-by-reference"></a>참조를 통해 구조체 형식 변수 전달

구조체 형식 변수를 메서드에 인수로 전달하거나 메서드에서 구조체 형식 값을 반환할 경우, 구조체 형식의 인스턴스 전체가 복사됩니다. 이로 인해 구조체 형식이 많이 사용되는 고성능 시나리오에서 코드의 성능이 저하될 수 있습니다. 구조체 형식 변수를 참조를 통해 전달하면 값이 복사되지 않도록 할 수 있습니다. 참조를 통해 인수를 전달해야 한다는 사실을 나타내려면 [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) 또는 [`in`](../keywords/in-parameter-modifier.md) 메서드 매개 변수 한정자를 사용합니다. 참조를 통해 메서드 결과를 반환하려면 [ref returns](../../programming-guide/classes-and-structs/ref-returns.md)를 사용합니다. 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.

## <a name="conversions"></a>변환

모든 구조체 형식에는 <xref:System.ValueType?displayProperty=nameWithType> 및 <xref:System.Object?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다. 구조체 형식과 구조체 형식이 구현하는 인터페이스 간에도 boxing 및 unboxing 변환이 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [구조체](~/_csharplang/spec/structs.md) 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [디자인 지침 - 클래스와 구조체 간의 선택](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [디자인 지침-구조체 디자인](../../../standard/design-guidelines/struct.md)
- [클래스 및 구조체](../../programming-guide/classes-and-structs/index.md)
