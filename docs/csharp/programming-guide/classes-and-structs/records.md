---
title: 레코드 - C# 프로그래밍 가이드
description: 레코드 형식 및 이를 만드는 방법에 관한 자세한 정보
ms.date: 02/26/2021
helpviewer_keywords:
- records [C#]
- C# language, records
ms.openlocfilehash: a45ed08da18e58f11793d6874d7275d9f5216be4
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260044"
---
# <a name="records-c-programming-guide"></a>레코드(C# 프로그래밍 가이드)

[레코드](../../language-reference/builtin-types/record.md)는 데이터 모델을 사용하기 위한 특수 구문 및 동작을 제공하는 [클래스](../../language-reference/keywords/class.md)입니다. 클래스에 관한 자세한 내용은 [클래스(C# 프로그래밍 가이드)](classes.md)를 참조하세요.

## <a name="when-to-use-records"></a>레코드를 사용하는 경우

다음 시나리오에서는 클래스 대신 레코드를 사용하는 것이 좋습니다.

* 개체를 변경할 수 없는 참조 형식을 정의하려는 경우
* [값 같음](../statements-expressions-operators/equality-comparisons.md#value-equality) 여부에 따라 달라지는 데이터 모델을 정의하려는 경우

### <a name="immutability"></a>불변성

변경할 수 없는 형식은 인스턴스화된 후 개체의 속성 또는 필드 값을 변경하는 것을 방지하는 형식입니다. 불변성은 형식이 스레드로부터 안전해야 하거나 해시 테이블에서 동일하게 남아 있는 해시 코드를 사용하는 경우에 유용할 수 있습니다. 레코드는 변경할 수 없는 형식을 만들고 사용하기 위한 간결한 구문을 제공합니다.

불변성은 모든 데이터 시나리오에 적합하지 않습니다. 예를 들어, [Entity Framework Core](/ef/core/)는 변경할 수 없는 엔터티 형식을 사용한 업데이트를 지원하지 않습니다.

### <a name="value-equality"></a>값 같음

레코드의 경우 값 같음은 형식이 일치하고 모든 속성 및 필드 값이 일치하는 경우 레코드 형식의 두 변수가 같다는 것을 의미합니다. 클래스와 같은 다른 참조 형식의 경우 같음은 [참조 같음](../statements-expressions-operators/equality-comparisons.md#reference-equality)을 의미합니다. 즉, 클래스 형식의 두 변수는 같은 개체를 참조하는 경우 같습니다. 두 레코드 인스턴스의 같음을 확인하는 메서드와 연산자에서 값 같음을 사용합니다.

일부 데이터 모델은 값 같음을 사용하지 않습니다. 예를 들어, [Entity Framework Core](/ef/core/)는 참조 같음을 사용하여 개념적으로 하나의 엔터티에 해당하는 엔터티 형식의 인스턴스를 하나만 사용하는지 확인합니다. 이 이유로 레코드 형식은 Entity Framework Core에서 엔터티 형식으로 사용하기에 적절하지 않습니다.

## <a name="how-records-differ-from-classes"></a>클래스와 레코드의 차이점

클래스를 [선언](classes.md#declaring-classes) 및 [인스턴스화](classes.md#creating-objects)하는 동일한 구문을 레코드에서 사용할 수 있습니다. `class` 키워드를 `record` 키워드로 대체하면 됩니다. 마찬가지로, 상속 관계를 표현하는 동일한 구문이 레코드에서 지원됩니다. 레코드가 클래스와 다른 점은 다음과 같습니다.

* [위치 매개 변수](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition)를 사용하여 변경할 수 없는 속성으로 형식을 만들고 인스턴스화할 수 있습니다.
* 클래스에서 참조 같음 또는 같지 않음(예: <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> 및 `==`)을 나타내는 동일한 메서드와 연산자가 레코드에서 [값 같음 또는 같지 않음](../../language-reference/builtin-types/record.md#value-equality)을 나타냅니다.
* [`with` 식](../../language-reference/builtin-types/record.md#nondestructive-mutation)을 사용하여 선택된 속성에 새 값을 포함하는 변경할 수 없는 개체의 복사본을 만들 수 있습니다.
* 레코드의 `ToString` 메서드는 개체 형식 이름과 모든 퍼블릭 속성의 이름과 값을 표시하는 형식 문자열을 만듭니다.
* 레코드는 [다른 레코드에서 상속](../../language-reference/builtin-types/record.md#inheritance)될 수 있습니다. 레코드는 클래스에서 상속될 수 없으며 클래스는 레코드에서 상속될 수 없습니다.

## <a name="examples"></a>예제

다음 예제에서는 위치 매개 변수를 사용하여 레코드를 선언하고 인스턴스화하는 퍼블릭 레코드를 정의합니다. 그런 다음, 형식 이름 및 속성 값을 출력합니다.

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="InstantiatePositional":::

다음 예제에서는 레코드에서 값 같음을 보여 줍니다.

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="Equality":::

다음 예제에서는 `with` 식을 사용하여 변경할 수 없는 개체를 복사하고 속성 중 하나를 변경하는 방법을 보여 줍니다.

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="WithExpressions":::

자세한 내용은 [레코드(C# 참조)](../../language-reference/builtin-types/record.md)를 참조하세요.
  
## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [클래스(C# 프로그래밍 가이드)](classes.md)
- [레코드(C# 참조)](../../language-reference/builtin-types/record.md)
- [C# 프로그래밍 가이드](../index.md)
- [개체 지향 프로그래밍](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [다형성](polymorphism.md)
- [식별자 이름](../inside-a-program/identifier-names.md)
- [멤버](members.md)
- [메서드](methods.md)
- [생성자](constructors.md)
- [종료자](destructors.md)
- [개체](objects.md)
