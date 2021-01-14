---
title: 구조체 형식 - C# 참조
description: C#의 구조체 형식에 관한 자세한 정보
ms.date: 10/23/2020
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- struct type [C#]
- structure type [C#]
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 2ceac94c04dd8deb169e836f09928dfd9a38ac35
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025435"
---
# <a name="structure-types-c-reference"></a>구조체 형식(C# 참조)

‘구조체 형식’은 데이터와 관련 기능을 캡슐화할 수 있는 [값 형식](value-types.md)입니다.   구조체 형식은 `struct` 키워드를 사용하여 정의합니다.

[!code-csharp[struct example](snippets/shared/StructType.cs#StructExample)]

구조체 형식은 ‘값 의미 체계’를 갖습니다.  즉, 구조체 형식의 변수는 해당 형식의 인스턴스를 포함합니다. 기본적으로 변수 값은 할당 시에, 인수를 메서드에 전달할 때, 그리고 메서드 결과를 반환할 때 복사됩니다. 구조체 형식 변수의 경우, 해당 형식의 인스턴스가 복사됩니다. 자세한 내용은 [값 형식](value-types.md)을 참조하세요.

구조체 형식은 일반적으로 동작을 거의 제공하지 않거나 전혀 제공하지 않는 작은 데이터 중심 형식을 설계하는 데 사용합니다. 예를 들어, .NET에서는 구조체 형식을 사용하여 숫자([정수](integral-numeric-types.md)와 [실수](floating-point-numeric-types.md)), [부울 값](bool.md), [유니코드 문자](char.md), [시간 인스턴스](xref:System.DateTime)를 표현합니다. 형식의 동작이 중요한 경우에는 [클래스](../keywords/class.md)를 정의하는 것이 좋습니다. 클래스 형식은 ‘참조 의미 체계’를 갖습니다.  즉, 클래스 형식의 변수는 인스턴스 자체가 아닌 해당 형식의 인스턴스에 대한 참조를 포함합니다.

구조체 형식에는 값 의미 체계가 있기 때문에 *변경할 수* 없는 구조체 형식을 정의하는 것이 좋습니다.

## <a name="readonly-struct"></a>`readonly` 구조체

C# 7.2부터 `readonly` 한정자를 사용하여 구조체 형식을 변경할 수 없도록 선언합니다. `readonly` 구조체의 모든 데이터 멤버는 다음과 같이 읽기 전용이어야 합니다.

- 모든 필드 선언에는 [`readonly` 한정자](../keywords/readonly.md)가 있어야 합니다.
- 자동 구현된 속성을 포함하여 모든 속성은 읽기 전용이어야 합니다. C# 9.0 이상에서는 속성에 [`init` 접근자](../../whats-new/csharp-9.md#init-only-setters)가 있을 수 있습니다.

이렇게 하면 `readonly` 구조체의 멤버가 구조체의 상태를 수정하지 않습니다. C# 8.0 이상에서는 생성자를 제외한 다른 인스턴스 멤버는 암시적으로 [`readonly`](#readonly-instance-members)임을 의미합니다.

> [!NOTE]
> `readonly` 구조체에서 변경 가능한 참조 형식의 데이터 멤버는 여전히 자체 상태를 변경할 수 있습니다. 예를 들어 <xref:System.Collections.Generic.List%601> 인스턴스를 바꿀 수는 없지만 새 요소를 추가할 수는 있습니다.

다음 코드는 C# 9.0 이상에서 사용할 수 있는 init 전용 속성 setter를 사용하여 `readonly` 구조체를 정의합니다.

[!code-csharp[readonly struct](snippets/shared/StructType.cs#ReadonlyStruct)]

## <a name="readonly-instance-members"></a>`readonly` 인스턴스 멤버

C# 8.0부터 `readonly` 한정자를 사용하여 인스턴스 멤버가 구조체의 상태를 수정하지 않도록 선언할 수도 있습니다. 전체 구조체 형식을 `readonly`로 선언할 수 없는 경우 `readonly` 한정자를 사용하여 구조체의 상태를 수정하지 않는 인스턴스 멤버를 표시합니다.

`readonly` 인스턴스 멤버 내에서 구조체의 인스턴스 필드에 할당할 수 없습니다. 그러나 `readonly` 멤버는`readonly`가 아닌 멤버를 호출할 수 있습니다. 이 경우 컴파일러는 구조체 인스턴스의 복사본을 만들고 해당 복사본에서 `readonly`가 아닌 멤버를 호출합니다. 따라서 원래 구조체 인스턴스는 수정되지 않습니다.

일반적으로 다음 종류의 인스턴스 멤버에 `readonly` 한정자를 적용합니다.

- 메서드:

  [!code-csharp[readonly method](snippets/shared/StructType.cs#ReadonlyMethod)]

  <xref:System.Object?displayProperty=nameWithType>에 선언된 메서드를 재정의하는 메서드에 `readonly` 한정자를 적용할 수도 있습니다.

  [!code-csharp[readonly override](snippets/shared/StructType.cs#ReadonlyOverride)]

- 속성 및 인덱서:

  [!code-csharp[readonly property get](snippets/shared/StructType.cs#ReadonlyProperty)]

  속성 또는 인덱서의 두 접근자에 모두 `readonly` 한정자를 적용해야 하는 경우 속성 또는 인덱서의 선언에 해당 한정자를 적용합니다.

  > [!NOTE]
  > 컴파일러는 속성 선언에 `readonly` 한정자가 있는지 여부와 관계없이 [자동 구현 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md)의 `get` 접근자를 `readonly`로 선언합니다.

  C# 9.0 이상에서는 `init` 접근자를 사용하여 속성 또는 인덱서에 `readonly` 한정자를 적용할 수 있습니다.

  :::code language="csharp" source="snippets/shared/StructType.cs" id="ReadonlyWithInit":::

구조체 형식의 정적 멤버에는 `readonly` 한정자를 적용할 수 없습니다.

컴파일러는 성능 최적화를 위해 `readonly` 한정자를 사용할 수 있습니다. 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.

## <a name="limitations-with-the-design-of-a-structure-type"></a>구조체 형식 설계의 제한 사항

구조체 형식을 설계할 때는 [클래스](../keywords/class.md) 형식과 같은 기능을 사용할 수 있으나, 다음과 같은 예외가 적용됩니다.

- 매개 변수가 없는 생성자를 선언할 수 없습니다. 모든 구조체 형식은 이미 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자를 제공합니다.

- 인스턴스 필드 또는 속성은 선언과 동시에 초기화할 수 없습니다. 단, [static](../keywords/static.md) 또는 [const](../keywords/const.md) 필드 또는 정적 속성은 선언과 동시에 초기화할 수 있습니다.

- 구조체 형식의 생성자는 해당 형식의 모든 인스턴스 필드를 초기화해야 합니다.

- 구조체 형식은 다른 클래스 또는 구조체 형식에서 상속할 수 없으며, 클래스의 기본이 될 수 없습니다. 단, 구조체 형식은 [인터페이스](../keywords/interface.md)를 구현할 수 있습니다.

- 구조체 형식 내에서 [종료자](../../programming-guide/classes-and-structs/destructors.md)를 선언할 수 없습니다.

## <a name="instantiation-of-a-structure-type"></a>구조체 형식의 인스턴스화

C#에서는 선언된 변수를 사용하려면 먼저 초기화해야 합니다. 구조체 형식 변수는 `null`일 수 없으므로([null 허용 값 형식](nullable-value-types.md)의 변수인 경우 제외), 해당 형식의 인스턴스를 인스턴스화해야 합니다. 이 작업은 몇 가지 방법으로 수행할 수 있습니다.

일반적으로, 구조체 형식은 [`new`](../operators/new-operator.md) 연산자를 사용하여 적절한 생성자를 호출함으로써 인스턴스화합니다. 모든 구조체 형식은 하나 이상의 생성자를 갖습니다. 이는 해당 형식의 [기본값](default-values.md)을 생성하는 매개 변수 없는 암시적 생성자입니다. [기본값 식](../operators/default.md)을 사용하여 형식의 기본값을 생성할 수도 있습니다.

구조체 형식의 모든 인스턴스 필드가 액세스 가능한 경우, `new` 연산자 없이 인스턴스화할 수도 있습니다. 이 경우 인스턴스를 처음 사용하기 전에 모든 인스턴스 필드를 초기화해야 합니다. 다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.

[!code-csharp[without new](snippets/shared/StructType.cs#WithoutNew)]

[기본 제공 값 형식](value-types.md#built-in-value-types)의 경우, 해당 리터럴을 사용하여 해당 형식의 값을 지정합니다.

## <a name="passing-structure-type-variables-by-reference"></a>참조를 통해 구조체 형식 변수 전달

구조체 형식 변수를 메서드에 인수로 전달하거나 메서드에서 구조체 형식 값을 반환할 경우, 구조체 형식의 인스턴스 전체가 복사됩니다. 이로 인해 구조체 형식이 많이 사용되는 고성능 시나리오에서 코드의 성능이 저하될 수 있습니다. 구조체 형식 변수를 참조를 통해 전달하면 값이 복사되지 않도록 할 수 있습니다. 참조를 통해 인수를 전달해야 한다는 사실을 나타내려면 [`ref`](../keywords/ref.md#passing-an-argument-by-reference), [`out`](../keywords/out-parameter-modifier.md) 또는 [`in`](../keywords/in-parameter-modifier.md) 메서드 매개 변수 한정자를 사용합니다. 참조를 통해 메서드 결과를 반환하려면 [ref returns](../../programming-guide/classes-and-structs/ref-returns.md)를 사용합니다. 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../write-safe-efficient-code.md)을 참조하세요.

## <a name="ref-struct"></a>`ref` 구조체

C# 7.2부터 구조체 형식 선언에 `ref` 한정자를 사용할 수 있습니다. `ref` 구조체 형식의 인스턴스는 스택에 할당되며 관리되는 힙으로 이스케이프할 수 없습니다. 이를 위해 컴파일러는 다음과 같이 `ref` 구조체 형식의 사용을 제한합니다.

- `ref` 구조체는 배열의 요소 형식일 수 없습니다.
- `ref` 구조체는 클래스의 필드 또는 비 `ref` 구조체의 선언된 형식일 수 없습니다.
- `ref` 구조체는 인터페이스를 구현할 수 없습니다.
- `ref` 구조체는 <xref:System.ValueType?displayProperty=nameWithType> 또는 <xref:System.Object?displayProperty=nameWithType>에 boxing할 수 없습니다.
- `ref` 구조체는 형식 인수일 수 없습니다.
- [람다 식](../operators/lambda-expressions.md) 또는 [로컬 함수](../../programming-guide/classes-and-structs/local-functions.md)에서 `ref` 구조체 변수를 캡처할 수 없습니다.
- [`async`](../keywords/async.md) 메서드에서는 `ref` 구조체 변수를 사용할 수 없습니다. 그러나 동기 메서드에서는 `ref` 구조체 변수(예: <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601>를 반환하는 변수)를 사용할 수 있습니다.
- [반복기](../../iterators.md)에서는 `ref` 구조체 변수를 사용할 수 없습니다.

일반적으로 `ref` 구조체 형식의 데이터 멤버도 포함하는 형식이 필요한 경우 `ref` 구조체 형식을 정의합니다.

[!code-csharp[ref struct](snippets/shared/StructType.cs#RefStruct)]

`ref` 구조체를 [`readonly`](#readonly-struct)로 선언하려면 형식 선언에서 `readonly` 및 `ref` 한정자를 결합합니다(`readonly` 한정자는 `ref` 한정자 앞에 와야함).

[!code-csharp[readonly ref struct](snippets/shared/StructType.cs#ReadonlyRef)]

.NET에서 `ref` 구조체의 예는 <xref:System.Span%601?displayProperty=nameWithType> 및 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>입니다.

## <a name="struct-constraint"></a>구조체 제약 조건

[`struct` 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)의 `struct` 키워드를 사용하여 형식 매개 변수가 null을 허용하지 않는 값 형식이라고 지정할 수도 있습니다. 구조체 형식과 [열거형](enum.md) 형식 모두 `struct` 제약 조건을 충족합니다.

## <a name="conversions"></a>변환

모든 구조체 형식([`ref` 구조체](#ref-struct) 형식 제외)에는 <xref:System.ValueType?displayProperty=nameWithType> 및 <xref:System.Object?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다. 구조체 형식과 구조체 형식이 구현하는 인터페이스 간에도 boxing 및 unboxing 변환이 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [구조체](~/_csharplang/spec/structs.md) 섹션을 참조하세요.

C# 7.2 이상에 도입된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.

- [읽기 전용 구조체](~/_csharplang/proposals/csharp-7.2/readonly-ref.md#readonly-structs)
- [읽기 전용 인스턴스 멤버](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)
- [ref 유사 형식에 대한 컴파일 시간 안전성](~/_csharplang/proposals/csharp-7.2/span-safety.md)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [디자인 지침 - 클래스와 구조체 간의 선택](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [디자인 지침-구조체 디자인](../../../standard/design-guidelines/struct.md)
- [클래스 및 구조체](../../programming-guide/classes-and-structs/index.md)
