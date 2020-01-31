---
title: 형식 디자인 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: 2a3cca0139974cbc92ce85a19db73dfb3d13d1a0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743573"
---
# <a name="type-design-guidelines"></a>형식 디자인 지침
就 CLR 而言，它仅支持两种类型 — 引用类型和值类型。但出于探讨框架设计的目的，我们将类型划分为多个逻辑组，每种都有其特定的设计规则。

 类是使用最普遍的引用类型。 多数框架中的大部分引用类型都是类。 类的广泛应用主要得益于其支持丰富的面向对象功能，以及普适性。 基类和抽象类是具备扩展性的特殊逻辑组。

 接口也是一种类型。 接口可以被引用类型和值类型实现，因此可以充当这两种类型多态层次结构的根。 此外，接口也可用于模拟多个继承，而 CLR 本身并不支持该功能。

 结构是常见的值类型。结构应当用来定义类似于语言基元的小型简单类型。

 枚举是一种特殊的值类型，它适用于定义一组数量有限的值，例如一周七天的名称、控制台颜色等。

 静态类的作用是为静态成员提供容器。 它们通常用来为其他操作提供快捷方式。

 委托、异常、属性、数组和集合是适用于特定用途的特殊引用类型。关于这些类型的设计准则与使用情况将在本书其他章节中进行讨论。

 ✔️ 각 형식이 관련 되지 않은 기능의 임의 컬렉션이 아니라 잘 정의 된 관련 멤버 집합 인지 확인 합니다.

## <a name="in-this-section"></a>섹션 내용
 [클래스와 구조체](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md) [추상 클래스](../../../docs/standard/design-guidelines/abstract-class.md) 를 선택 합니다. 추상 클래스 디자인 [정적 클래스](../../../docs/standard/design-guidelines/static-class.md) 디자인 [인터페이스](../../../docs/standard/design-guidelines/interface.md) 디자인 [구조체](../../../docs/standard/design-guidelines/struct.md) 디자인 [열거형](../../../docs/standard/design-guidelines/enum.md) 디자인 [중첩 형식](../../../docs/standard/design-guidelines/nested-types.md) *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
