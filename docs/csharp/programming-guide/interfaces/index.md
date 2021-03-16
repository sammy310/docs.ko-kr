---
title: 인터페이스 - C# 프로그래밍 가이드
description: C#의 인터페이스에는 비추상 클래스 또는 구조체에서 구현해야 하는 관련 기능 그룹에 대한 정의가 포함되어 있습니다.
ms.date: 02/20/2020
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 123c3768414ee9a577c49c218acfb7415d83572e
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605284"
---
# <a name="interfaces-c-programming-guide"></a>인터페이스(C# 프로그래밍 가이드)

인터페이스에는 비추상 [클래스](../../language-reference/keywords/class.md) 또는 [구조체](../../language-reference/builtin-types/struct.md)에서 구현해야 하는 관련 기능 그룹에 대한 정의가 포함되어 있습니다. 인터페이스에서는 구현이 있어야 하는 `static` 메서드를 정의할 수 있습니다. C# 8.0부터 인터페이스는 구성원에 대한 기본 구현을 정의할 수 있습니다. 인터페이스에서는 필드, 자동 구현 속성, 속성과 유사한 이벤트 등과 같은 인스턴스 데이터를 선언할 수 없습니다.

예를 들어 인터페이스를 사용하면 여러 소스의 동작을 클래스에 포함할 수 있습니다. 해당 기능은 언어가 클래스의 여러 상속을 지원하지 않기 때문에 C#에서 중요합니다. 또한 구조체는 다른 구조체나 클래스에서 실제로 상속할 수 없기 때문에 구조체에 대한 상속을 시뮬레이트하려는 경우 인터페이스를 사용해야 합니다.

다음 예제와 같이 [interface](../../language-reference/keywords/interface.md) 키워드를 사용하여 인터페이스를 정의합니다.

[!code-csharp[Equatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#Equatable)]

인터페이스 이름은 유효한 C# [식별자 이름](../inside-a-program/identifier-names.md)이어야 합니다. 규칙에 따라 인터페이스 이름은 대문자 `I`로 시작합니다.

<xref:System.IEquatable%601> 인터페이스를 구현하는 모든 클래스나 구조체에는 인터페이스에서 지정한 서명과 일치하는 <xref:System.IEquatable%601.Equals%2A> 메서드에 대한 정의가 포함되어 있어야 합니다. 따라서 `IEquatable<T>`을 구현하는 클래스를 계산하여 클래스의 인스턴스에서 동일한 클래스의 다른 인스턴스와 동일한지 여부를 확인할 수 있는 `Equals` 메서드를 포함할 수 있습니다.

`IEquatable<T>`의 정의에서는 `Equals`에 대한 구현을 제공하지 않습니다. 클래스 또는 구조체는 여러 인터페이스를 구현할 수 있지만 클래스는 단일 클래스에서만 상속할 수 있습니다.

추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.

인터페이스에는 인스턴스 메서드, 속성, 이벤트, 인덱서 또는 이러한 네 가지 멤버 형식의 조합이 포함될 수 있습니다. 인터페이스에는 정적 생성자, 필드, 상수 또는 연산자가 포함될 수 있습니다. 예제에 대한 링크는[관련 단원](./index.md#BKMK_RelatedSections)을 참조하세요. 인터페이스에는 인스턴스 필드, 인스턴스 생성자 또는 종료자가 포함될 수 없습니다. 인터페이스 멤버는 기본적으로 공용이며, `public`, `protected`, `internal`, `private`, `protected internal` 또는 `private protected` 등의 접근성 한정자를 명시적으로 지정할 수 있습니다. `private` 멤버에는 기본 구현이 있어야 합니다.

인터페이스 멤버를 구현하려면 구현 클래스의 해당 멤버가 공용이고 비정적이어야 하며 인터페이스 멤버와 동일한 이름 및 서명을 사용해야 합니다.

클래스 또는 구조체에서 인터페이스를 구현하는 경우 클래스 또는 구조체에서 인터페이스에서 선언하는 모든 멤버의 구현을 제공해야 하지만 기본 구현은 제공하지 않습니다. 그러나 기본 클래스에서 인터페이스를 구현하는 경우에는 기본 클래스에서 파생되는 모든 클래스가 해당 구현을 상속합니다.

다음 예제에서는 <xref:System.IEquatable%601> 인터페이스의 구현을 보여 줍니다. 구현 클래스 `Car`는 <xref:System.IEquatable%601.Equals%2A> 메서드의 구현을 제공해야 합니다.

[!code-csharp[ImplementEquatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#ImplementEquatable)]

클래스의 속성 및 인덱서는 인터페이스에 정의된 속성이나 인덱서에 대해 추가 접근자를 정의할 수 있습니다. 예를 들어 인터페이스는 [get](../../language-reference/keywords/get.md) 접근자가 있는 속성을 선언할 수 있습니다. 인터페이스를 구현하는 클래스는 `get` 및 [set](../../language-reference/keywords/set.md) 접근자를 둘 다 사용하는 동일한 속성을 선언할 수 있습니다. 그러나 속성 또는 인덱서에서 명시적 구현을 사용하는 경우에는 접근자가 일치해야 합니다. 명시적 구현에 대한 자세한 내용은 [명시적 인터페이스 구현](explicit-interface-implementation.md) 및 [인터페이스 속성(C# 프로그래밍 가이드)](../classes-and-structs/interface-properties.md)을 참조하세요.

인터페이스는 하나 이상의 인터페이스에서 상속할 수 있습니다. 파생 인터페이스는 기본 인터페이스에서 멤버를 상속합니다. 파생 인터페이스를 구현하는 클래스는 파생 인터페이스의 기본 인터페이스 멤버 모두를 포함해 파생 인터페이스의 모든 멤버를 구현해야 합니다. 이 클래스는 파생 인터페이스나 해당하는 기본 인터페이스로 암시적으로 변환될 수 있습니다. 클래스는 상속하는 기본 클래스 또는 다른 인터페이스에서 상속하는 인터페이스를 통해 인터페이스를 여러 번 포함할 수 있습니다. 그러나 클래스는 인터페이스의 구현을 한 번만 제공할 수 있으며 클래스가 인터페이스를 클래스 정의의 일부로 선언하는 경우에만 제공할 수 있습니다(`class ClassName : InterfaceName`). 인터페이스를 구현하는 기본 클래스를 상속했기 때문에 인터페이스가 상속되는 경우 기본 클래스는 인터페이스 멤버의 구현을 제공합니다. 그러나 파생 클래스는 상속된 구현을 사용하는 대신 가상 인터페이스 멤버를 다시 구현할 수 있습니다. 인터페이스에서 메서드의 기본 구현을 선언하는 경우 해당 인터페이스를 구현하는 모든 클래스가 해당 구현을 상속합니다. 인터페이스에 정의된 구현은 가상이며 구현하는 클래스가 해당 구현을 재정의할 수 있습니다.

또한 기본 클래스는 가상 멤버를 사용하여 인터페이스 멤버를 구현할 수 있습니다. 이 경우 파생 클래스는 가상 멤버를 재정의하여 인터페이스 동작을 변경할 수 있습니다. 가상 멤버에 대한 자세한 내용은 [다형성](../classes-and-structs/polymorphism.md)을 참조하세요.

## <a name="interfaces-summary"></a>인터페이스 요약

인터페이스에는 다음과 같은 속성이 있습니다.

- 인터페이스는 일반적으로 추상 멤버만 갖는 추상 기본 클래스와 같습니다. 인터페이스를 구현하는 모든 클래스 또는 구조체는 모든 멤버를 구현해야 합니다. 필요에 따라 인터페이스에서 해당 멤버 일부 또는 모두의 기본 구현을 정의할 수 있습니다. 자세한 내용은 [기본 인터페이스 메서드](../../tutorials/default-interface-methods-versions.md)를 참조하세요.
- 인터페이스는 직접 인스턴스화할 수 없습니다. 해당 멤버는 인터페이스를 구현하는 클래스 또는 구조체에 의해 구현됩니다.
- 클래스 또는 구조체는 여러 인터페이스를 구현할 수 있습니다. 클래스는 기본 클래스를 상속할 수 있으며 하나 이상의 인터페이스를 제공할 수도 있습니다.

## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> 관련 섹션

- [인터페이스 속성](../classes-and-structs/interface-properties.md)  
- [인터페이스의 인덱서](../indexers/indexers-in-interfaces.md)  
- [인터페이스 이벤트를 구현하는 방법](../events/how-to-implement-interface-events.md)
- [클래스 및 구조체](../classes-and-structs/index.md)  
- [상속](../classes-and-structs/inheritance.md)  
- [인터페이스](../../language-reference/keywords/interface.md)
- [메서드](../classes-and-structs/methods.md)  
- [다형성](../classes-and-structs/polymorphism.md)  
- [추상/봉인된 클래스 및 클래스 멤버](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [속성](../classes-and-structs/properties.md)  
- [이벤트](../events/index.md)  
- [인덱서](../indexers/index.md)
  
## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [상속](../classes-and-structs/inheritance.md)
- [식별자 이름](../inside-a-program/identifier-names.md)
