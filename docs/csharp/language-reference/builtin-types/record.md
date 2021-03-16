---
title: 레코드 - C# 참조
description: C#의 레코드 형식에 대해 알아봅니다.
ms.date: 02/25/2021
f1_keywords:
- record_CSharpKeyword
helpviewer_keywords:
- record keyword [C#]
- record type [C#]
ms.openlocfilehash: 10fe7bcc1f3239b7a6bde0abcac41b177467cf0a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260031"
---
# <a name="records-c-reference"></a>레코드(C# 참조)

C# 9부터 `record` 키워드를 사용하여 데이터를 캡슐화하는 기본 제공 기능을 제공하는 [참조 형식](reference-types.md)을 정의합니다. 위치 매개 변수 또는 표준 속성 구문을 사용하여 변경할 수 없는 속성이 있는 레코드 형식을 만들 수 있습니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalRecord":::
:::code language="csharp" source="snippets/shared/RecordType.cs" id="ImmutableRecord":::

변경할 수 있는 속성 및 필드를 사용하여 레코드 형식을 만들 수도 있습니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MutableRecord":::

레코드는 변경할 수 있지만 주로 변경할 수 없는 데이터 모델을 지원하기 위한 것입니다. 레코드 형식은 다음과 같은 기능을 제공합니다.

* [변경할 수 없는 속성을 사용하여 참조 형식을 만드는 간결한 구문](#positional-syntax-for-property-definition)
* 데이터 중심 참조 형식에 유용한 기본 제공 동작:
  * [값 같음](#value-equality)
  * [비파괴적 변형을 위한 간결한 구문](#nondestructive-mutation)
  * [표시를 위한 기본 제공 형식](#built-in-formatting-for-display)
* [상속 계층 구조 지원](#inheritance)

[구조 형식](struct.md)을 사용하여 값 같음을 제공하고 동작이 거의 또는 전혀 발생하지 않는 데이터 중심 형식을 디자인할 수도 있습니다. 그러나 비교적 규모가 큰 데이터 모델의 경우 구조체 형식에는 몇 가지 단점이 있습니다.

* 상속을 지원하지 않습니다.
* 값 같음을 판별하는 효율성이 낮습니다. 값 형식의 경우 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 메서드는 리플렉션을 사용하여 모든 필드를 찾습니다. 레코드의 경우 컴파일러가 `Equals` 메서드를 생성합니다. 실제로 레코드에서 값 같음을 구현하는 것이 어느 정도 더 빠릅니다.
* 모든 인스턴스는 모든 데이터의 전체 복사본을 포함하기 때문에 일부 시나리오에서는 더 많은 메모리를 사용합니다. 레코드 형식은 [참조 형식](reference-types.md)이므로 레코드 인스턴스는 데이터에 대한 참조만 포함합니다.

## <a name="positional-syntax-for-property-definition"></a>속성 정의에 대한 위치 구문

위치 매개 변수를 사용하여 레코드의 속성을 선언하고 인스턴스를 만들 때 속성 값을 초기화할 수 있습니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InstantiatePositional":::

속성 정의에 위치 구문을 사용하는 경우 컴파일러가 다음을 만듭니다.

* 레코드 선언에 제공된 각 위치 매개 변수에 대한 공용 초기화 전용 자동 구현 속성. [초기화 전용](../../whats-new/csharp-9.md#init-only-setters) 속성은 생성자에서만 또는 속성 이니셜라이저를 사용하여 설정할 수 있습니다.
* 매개 변수가 레코드 선언의 위치 매개 변수와 일치하는 기본 생성자.
* 레코드 선언에 제공된 각 위치 매개 변수에 대한 `out` 매개 변수를 사용하는 `Deconstruct` 메서드. 이 메서드는 둘 이상의 위치 매개 변수가 있는 경우에만 제공됩니다. 메서드는 위치 구문을 사용하여 정의된 속성을 분해합니다. 표준 속성 구문을 사용하여 정의된 속성은 무시됩니다.

생성된 자동 구현 속성 정의가 원하는 내용이 아니면 동일한 이름의 속성을 직접 정의할 수 있습니다. 그러면 생성된 생성자 및 분해자에서 이 속성 정의를 사용합니다. 예를 들어 다음 예제에서는 `FirstName` 위치 속성 `internal`을 `public` 대신 만듭니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalWithManualProperty":::

레코드 형식은 위치 속성을 선언할 필요가 없습니다. 다음 예제와 같이 위치 속성 없이 레코드를 선언하고 추가 필드 및 속성을 선언할 수 있습니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="MixedSyntax":::

표준 속성 구문을 사용하여 속성을 정의하지만 액세스 한정자를 생략하면 속성은 암시적으로 `public`입니다.
<!-- Todo -- Explain issues surrounding use of attributes on positional properties. -->

## <a name="immutability"></a>불변성

레코드 형식이 반드시 변경 불가능해야 하는 것은 아닙니다. `readonly`가 아닌 `set` 접근자 및 필드를 사용하여 속성을 선언할 수 있습니다. 그러나 레코드는 변경할 수 있지만 이를 통해 변경할 수 없는 데이터 모델을 쉽게 만들 수 있습니다.

불변성은 데이터 중심 형식이 스레드로부터 안전해야 하거나 해시 테이블에서 동일하게 남아 있는 해시 코드를 사용하는 경우에 유용할 수 있습니다. 하지만 불변성이 모든 데이터 시나리오에 적합한 것은 아닙니다. 예를 들어, [Entity Framework Core](/ef/core/)는 변경할 수 없는 엔터티 형식을 사용한 업데이트를 지원하지 않습니다.

위치 매개 변수에서 생성되든 또는 `init` 접근자를 지정하여 생성되든 상관없이 초기화 전용 속성에는 ‘단순 불변성’이 있습니다. 초기화 후에는 값 형식 속성의 값 또는 참조 형식 속성의 참조를 변경할 수 없습니다. 그러나 참조 형식 속성이 참조하는 데이터는 변경할 수 있습니다. 다음 예제에서는 참조 형식 변경 불가능 속성의 콘텐츠(이 경우에는 배열)를 변경할 수 있음을 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ShallowImmutability":::

레코드 형식에 고유한 기능이 컴파일러 합성 메서드로 구현되고, 이러한 메서드는 개체 상태를 수정하여 불변성을 손상하지 않습니다.

## <a name="value-equality"></a>값 같음

값 같음은 형식이 일치하고 모든 속성 및 필드 값이 일치하는 경우 레코드 형식의 두 변수가 같다는 것을 의미합니다. 다른 참조 형식의 경우 같음은 ID를 의미합니다. 즉, 참조 형식의 두 변수는 같은 개체를 참조하는 경우 같습니다.

일부 데이터 모델에서는 참조 같음이 필요합니다. 예를 들어, [Entity Framework Core](/ef/core/)는 참조 같음을 사용하여 개념적으로 하나의 엔터티에 해당하는 엔터티 형식의 인스턴스를 하나만 사용하는지 확인합니다. 이러한 이유로 레코드 형식은 Entity Framework Core에서 엔터티 형식으로 사용하기에 적절하지 않습니다.

다음 예제에서는 레코드 형식의 값 같음을 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="Equality":::

값 같음을 구현하기 위해 컴파일러는 다음 메서드를 합성합니다.

* <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>의 재정의.

  두 매개 변수가 모두 Null이 아닌 경우 이 메서드가 <xref:System.Object.Equals(System.Object,System.Object)?displayProperty=nameWithType> 정적 메서드의 기본으로 사용됩니다.

* 매개 변수가 레코드 종류인 가상 `Equals` 메서드. 이 메서드는 <xref:System.IEquatable%601>를 구현합니다.

* <xref:System.Object.GetHashCode?displayProperty=nameWithType>의 재정의.

* 연산자 `==` 및 `!=`의 재정의.

`class` 형식에서 같음 메서드 및 연산자를 수동으로 재정의하여 값 같음을 얻을 수 있지만, 해당 코드를 개발하고 테스트하는 데는 시간이 많이 걸리고 오류가 발생하기 쉽습니다. 이 기능을 기본 제공하면 속성 또는 필드가 추가되거나 변경될 때 사용자 지정 재정의 코드를 업데이트하지 않는 버그가 발생하지 않습니다.

사용자 고유의 구현을 작성하여 이러한 합성된 메서드를 대체할 수 있습니다. 레코드 종류에 합성 메서드의 시그니처와 일치하는 메서드가 있는 경우 해당 메서드는 컴파일러에서 합성되지 않습니다.

레코드 형식에서 `Equals`의 고유한 구현을 제공하는 경우 `GetHashCode`의 구현도 제공하세요.

## <a name="nondestructive-mutation"></a>비파괴적 변경

레코드 인스턴스의 변경 불가능한 속성을 변경해야 하는 경우에는 `with` 식을 사용하여 ‘비파괴적 변형’을 수행할 수 있습니다. `with` 식은 기존 레코드 인스턴스의 지정된 속성 및 필드가 수정된 복사본인 새 레코드 인스턴스를 만듭니다. 다음 예제와 같이 [개체 이니셜라이저](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) 구문을 사용하여 변경할 값을 지정합니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressions":::

`with` 식은 위치 속성 또는 표준 속성 구문을 사용하여 만든 속성을 설정할 수 있습니다. 비위치 속성에는 `with` 식에서 변경할 `init` 또는 `set` 접근자가 있어야 합니다.

`with` 식의 결과는 ‘단순 복사본’입니다. 즉, 참조 속성의 경우 인스턴스에 대한 참조만 복사됩니다. 원본 레코드와 복사본은 모두 동일한 인스턴스를 참조합니다.

이 기능을 구현하기 위해 컴파일러는 clone 메서드와 복사 생성자를 합성합니다. 생성자는 복사할 레코드의 인스턴스를 사용하여 clone 메서드를 호출합니다. `with` 식을 사용하는 경우 컴파일러는 복사 생성자를 호출하는 코드를 만든 다음 `with` 식에 지정된 속성을 설정합니다.

다른 복사 동작이 필요한 경우 사용자 고유의 복사 생성자를 작성할 수 있습니다. 이렇게 하면 컴파일러는 생성자를 합성하지 않습니다. 레코드가 `sealed`면 생성자를 `private`로 설정하고 그렇지 않으면 `protected`로 설정합니다.

Clone 메서드는 재정의할 수 없으며 `Clone`이라는 멤버는 만들 수 없습니다. Clone 메서드의 실제 이름은 컴파일러에서 생성합니다.

## <a name="built-in-formatting-for-display"></a>표시를 위한 기본 제공 형식

레코드 형식에는 공용 속성 및 필드의 이름과 값을 표시하는 컴파일러 생성 <xref:System.Object.ToString%2A> 메서드가 있습니다. `ToString` 메서드는 다음 형식의 문자열을 반환합니다.

> \<record type name> { \<property name> = \<value>, \<property name> = \<value>, ...}

참조 형식의 경우 속성이 참조하는 개체의 형식 이름이 속성 값 대신 표시됩니다. 다음 예제에서는 배열이 참조 형식이므로 `System.String[]`이 실제 배열 요소 값 대신 표시됩니다.

```
Person { FirstName = Nancy, LastName = Davolio, ChildNames = System.String[] } 
```

이 기능을 구현하기 위해 컴파일러는 가상 `PrintMembers` 메서드와 <xref:System.Object.ToString%2A> 재정의를 합성합니다.
`ToString` 재정의는 형식 이름과 그 뒤의 여는 괄호를 사용하여 <xref:System.Text.StringBuilder> 개체를 만듭니다. `PrintMembers`를 호출하여 속성 이름 및 값을 추가한 다음 닫는 괄호를 추가합니다. 다음 예제에서는 합성된 재정의에 포함된 것과 유사한 코드를 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringOverrideDefault":::

`PrintMembers` 또는 `ToString` 재정의의 고유한 구현을 제공할 수 있습니다. 예제는 이 문서의 뒷부분에 나오는 [파생 레코드의 `PrintMembers` 형식](#printmembers-formatting-in-derived-records) 섹션에 나와 있습니다.

## <a name="inheritance"></a>상속

레코드는 다른 레코드에서 상속될 수 있습니다. 그러나 레코드는 클래스에서 상속될 수 없고 클래스는 레코드에서 상속될 수 없습니다.

### <a name="positional-parameters-in-derived-record-types"></a>파생 레코드 형식의 위치 매개 변수

파생 레코드는 기본 레코드 기본 생성자의 모든 매개 변수에 대한 위치 매개 변수를 선언합니다. 기본 레코드는 이러한 속성을 선언하고 초기화합니다. 파생 레코드는 이러한 속성을 숨기지는 않지만 기본 레코드에 선언되지 않은 매개 변수의 속성만 만들고 초기화합니다.

다음 예제에서는 위치 속성 구문을 사용한 상속을 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PositionalInheritance":::

### <a name="equality-in-inheritance-hierarchies"></a>상속 계층 구조에서의 같음

두 레코드 변수가 같으려면 런타임 형식이 동일해야 합니다. 포함하는 변수의 형식은 다를 수 있습니다. 다음 코드 예제가 이 내용을 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="InheritanceEquality":::

예제에서 모든 인스턴스에는 동일한 속성 및 동일한 속성 값이 있습니다. 그러나 모두 `Person` 형식 변수이지만 `student == teacher`는 `False`를 반환하고, 하나는 `Person` 변수이고 하나는 `Student` 변수이지만 `student == student2`는 `True`를 반환합니다.

이 동작을 구현하기 위해 컴파일러는 레코드 형식과 일치하는 <xref:System.Type> 개체를 반환하는 `EqualityContract` 속성을 합성합니다. 이렇게 하면 같음 메서드가 같음을 확인할 때 개체의 런타임 형식을 비교할 수 있습니다. 레코드의 기본 형식이 `object`이면 이 속성은 `virtual`입니다. 기본 형식이 또 다른 레코드 형식이면 이 속성은 재정의입니다. 레코드 형식이 `sealed`이면 이 속성은 `sealed`입니다.

파생 형식의 두 인스턴스를 비교하는 경우 합성된 같음 메서드는 기본 및 파생 형식의 모든 속성에 서 같음을 확인합니다. 합성된 `GetHashCode` 메서드는 기본 형식 및 파생 레코드 형식에 선언된 모든 속성과 필드의 `GetHashCode` 메서드를 사용합니다.

### <a name="with-expressions-in-derived-records"></a>파생 레코드의 `with` 식

합성된 clone 메서드는 [공변 반환 형식](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)을 사용하므로 `with` 식의 결과는 식의 피연산자와 동일한 런타임 형식을 갖습니다. 런타임 형식의 속성은 모두 복사되지만 다음 예제와 같이 컴파일 시간 형식의 속성만 설정할 수 있습니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="WithExpressionInheritance":::

### <a name="printmembers-formatting-in-derived-records"></a>파생 레코드의 `PrintMembers` 형식

파생 레코드 형식의 합성된 `PrintMembers` 메서드는 기본 구현을 호출합니다. 그러면 다음 예제와 같이 파생된 형식과 기본 형식의 모든 공용 속성 및 필드가 `ToString` 출력에 포함됩니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="ToStringInheritance":::

`PrintMembers` 메서드의 고유한 구현을 제공할 수 있습니다. 이렇게 하려면 다음 서명을 사용합니다.

* `object`에서 파생되는 `sealed` 레코드(기본 레코드를 선언하지 않음): `private bool PrintMembers(StringBuilder builder)`
* 다른 레코드에서 파생되는 `sealed` 레코드: `protected sealed override bool PrintMembers(StringBuilder builder)`
* `sealed`가 아니고 개체에서 파생된 레코드: `protected virtual bool PrintMembers(StringBuilder builder);`
* `sealed`가 아니고 다른 레코드에서 파생된 레코드: `protected override bool PrintMembers(StringBuilder builder);`

다음은 합성된 `PrintMembers` 메서드를 대체하는 코드의 예제입니다. 하나는 개체에서 파생되는 레코드 형식이고 다른 하나는 다른 레코드에서 파생되는 레코드 형식에 대한 것입니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="PrintMembersImplementation":::

### <a name="deconstructor-behavior-in-derived-records"></a>파생 레코드의 분해자 동작

파생 레코드의 `Deconstruct` 메서드는 컴파일 시간 형식의 모든 위치 속성 값을 반환합니다. 변수 형식이 기본 레코드인 경우 개체가 파생 형식으로 캐스팅되는 경우를 제외하고는 기본 레코드 속성만 분해됩니다. 다음 예제에서는 파생 레코드에 대해 분해자를 호출하는 방법을 보여 줍니다.

:::code language="csharp" source="snippets/shared/RecordType.cs" id="DeconstructorInheritance":::

## <a name="generic-constraints"></a>제네릭 제약 조건

형식이 레코드가 되어야 하는 제네릭 제약 조건은 없습니다. 레코드는 `class` 제약 조건을 만족합니다. 레코드 형식의 특정 계층 구조에 대한 제약 조건을 만들려면 기본 클래스와 동일한 방식으로 기본 레코드에 제약 조건을 추가합니다. 자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [클래스](~/_csharplang/spec/classes.md) 섹션을 참조하세요.

C# 9 이상에 도입된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.

- [레코드](~/_csharplang/proposals/csharp-9.0/records.md)
- [초기화 전용 setter](~/_csharplang/proposals/csharp-9.0/init.md)
- [공변 반환](~/_csharplang/proposals/csharp-9.0/covariant-returns.md)

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [디자인 지침 - 클래스와 구조체 간의 선택](../../../standard/design-guidelines/choosing-between-class-and-struct.md)
- [디자인 지침-구조체 디자인](../../../standard/design-guidelines/struct.md)
- [클래스 및 구조체](../../programming-guide/classes-and-structs/index.md)
- [`with` 식](../operators/with-expression.md)
