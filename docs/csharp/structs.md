---
title: 구조체 - C# 가이드
description: 구조체 형식 및 만드는 방법을 알아봅니다.
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: cdfe2a763058b8f568ede2ff93c918c2dae874f7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346898"
---
# <a name="structs"></a>구조체

*struct*가 값 형식입니다. 구조체를 만드는 경우 구조체가 할당된 변수에 구조체의 실제 데이터가 포함됩니다. 구조체를 새 변수에 할당하면 구조체가 복사됩니다. 따라서 새 변수와 원래 변수에 동일한 데이터의 두 가지 별도 복사본이 포함됩니다. 한 복사본의 변경 내용은 다른 복사본에 영향을 주지 않습니다.

값 형식 변수에는 해당 값이 직접 포함되므로, 변수가 선언된 컨텍스트에 관계없이 메모리가 인라인으로 할당됩니다. 값 형식 변수에 대한 별도 힙 할당이나 가비지 수집 오버헤드는 없습니다.

값 형식에는 [struct](language-reference/keywords/struct.md) 및 [enum](language-reference/builtin-types/enum.md)의 두 가지 범주가 있습니다.

기본 제공 숫자 형식은 구조체이며, 액세스할 수 있는 속성과 메서드가 있습니다.

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

하지만 단순 비집계 형식처럼 값을 선언하고 변수에 할당합니다.

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

값 형식은 *sealed*이므로, 예를 들어 <xref:System.Int32>에서 형식을 파생시킬 수 없으며 구조체는 <xref:System.ValueType>에서만 상속할 수 있기 때문에 사용자 정의 클래스 또는 구조체에서 상속하는 구조체를 정의할 수 없습니다. 그러나 구조체는 하나 이상의 인터페이스를 구현할 수 있습니다. 구조체 형식을 인터페이스 형식으로 캐스팅할 수 있습니다. 이 경우 *boxing* 작업은 관리되는 힙의 참조 형식 개체 내에 구조체를 래핑합니다. boxing 작업은 <xref:System.Object>를 입력 매개 변수로 사용하는 메서드에 값 형식을 전달할 때 발생합니다. 자세한 내용은 [boxing 및 unboxing](./programming-guide/types/boxing-and-unboxing.md )을 참조하세요.

[struct](./language-reference/keywords/struct.md) 키워드를 사용하여 고유한 사용자 지정 값 형식을 만듭니다. 일반적으로 구조체는 다음 예제와 같이 소규모 관련 변수 집합의 컨테이너로 사용됩니다.

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

.NET Framework의 값 형식에 대한 자세한 내용은 [CTS(공용 형식 시스템)](../standard/common-type-system.md)를 참조하세요.

구조체가 클래스보다 더 제한적이지만 구조체는 클래스와 동일한 구문을 대부분 공유합니다.

- 구조체 선언 내에서 필드가 `const` 또는 `static`으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.

- 구조체는 매개 변수 없는 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.

- 할당 시 구조체가 복사됩니다. 구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다. Dictionary<string, myStruct> 등의 값 형식 컬렉션으로 작업하는 경우 이 점을 명심해야 합니다.

- 구조체는 값 형식이고 클래스는 참조 형식입니다.

- 클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.

   > [!NOTE]
   > .NET Core 2.1 이상에서 구조체 형식은 [new 연산자](language-reference/operators/new-operator.md) 또는 [기본 리터럴](language-reference/operators/default.md#default-literal)을 사용하거나 각 프라이빗 필드를 초기화하여 인스턴스화되어야 합니다. 자세한 내용은 [버전 2.0에서 2.1로 마이그레이션 시 호환성이 손상되는 변경](../core/compatibility/2.0-2.1.md#corefx)을 참조하세요.

- 구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.

- 구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다. 모든 구조체는 <xref:System.Object>에서 상속하는 <xref:System.ValueType>에서 직접 상속합니다.

- 구조체는 클래스와 마찬가지로 인터페이스를 구현할 수 있습니다.

## <a name="nullable-value-types"></a>Nullable 값 형식

일반적인 값 형식은 [null](language-reference/keywords/null.md) 값을 가질 수 없습니다. 그러나 형식 뒤에 `?`를 추가하면 null 허용 값 형식을 예를 들어 `int?`는 [null](./language-reference/keywords/null.md) 값을 가질 수도 있는 `int` 형식입니다. nullable 값 형식은 제네릭 구조체 형식 <xref:System.Nullable%601>의 인스턴스입니다. nullable 값 형식은 특히 숫자 값이 null이거나 정의되지 않을 수 있는 데이터베이스에 데이터를 전달하는 경우에 유용합니다. 자세한 내용은 [nullable 값 형식](language-reference/builtin-types/nullable-value-types.md)을 참조하세요.

## <a name="see-also"></a>참조

- [클래스](programming-guide/classes-and-structs/classes.md)
- [기본 형식](basic-types.md)
