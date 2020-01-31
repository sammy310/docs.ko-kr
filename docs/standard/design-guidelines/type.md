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
# <a name="type-design-guidelines"></a><span data-ttu-id="6f41d-102">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6f41d-102">Type Design Guidelines</span></span>
<span data-ttu-id="6f41d-103">就 CLR 而言，它仅支持两种类型 — 引用类型和值类型。但出于探讨框架设计的目的，我们将类型划分为多个逻辑组，每种都有其特定的设计规则。</span><span class="sxs-lookup"><span data-stu-id="6f41d-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>

 <span data-ttu-id="6f41d-104">类是使用最普遍的引用类型。</span><span class="sxs-lookup"><span data-stu-id="6f41d-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="6f41d-105">多数框架中的大部分引用类型都是类。</span><span class="sxs-lookup"><span data-stu-id="6f41d-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="6f41d-106">类的广泛应用主要得益于其支持丰富的面向对象功能，以及普适性。</span><span class="sxs-lookup"><span data-stu-id="6f41d-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="6f41d-107">基类和抽象类是具备扩展性的特殊逻辑组。</span><span class="sxs-lookup"><span data-stu-id="6f41d-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>

 <span data-ttu-id="6f41d-108">接口也是一种类型。</span><span class="sxs-lookup"><span data-stu-id="6f41d-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="6f41d-109">接口可以被引用类型和值类型实现，因此可以充当这两种类型多态层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="6f41d-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="6f41d-110">此外，接口也可用于模拟多个继承，而 CLR 本身并不支持该功能。</span><span class="sxs-lookup"><span data-stu-id="6f41d-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>

 <span data-ttu-id="6f41d-111">结构是常见的值类型。结构应当用来定义类似于语言基元的小型简单类型。</span><span class="sxs-lookup"><span data-stu-id="6f41d-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>

 <span data-ttu-id="6f41d-112">枚举是一种特殊的值类型，它适用于定义一组数量有限的值，例如一周七天的名称、控制台颜色等。</span><span class="sxs-lookup"><span data-stu-id="6f41d-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>

 <span data-ttu-id="6f41d-113">静态类的作用是为静态成员提供容器。</span><span class="sxs-lookup"><span data-stu-id="6f41d-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="6f41d-114">它们通常用来为其他操作提供快捷方式。</span><span class="sxs-lookup"><span data-stu-id="6f41d-114">They are commonly used to provide shortcuts to other operations.</span></span>

 <span data-ttu-id="6f41d-115">委托、异常、属性、数组和集合是适用于特定用途的特殊引用类型。关于这些类型的设计准则与使用情况将在本书其他章节中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="6f41d-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>

 <span data-ttu-id="6f41d-116">✔️ 각 형식이 관련 되지 않은 기능의 임의 컬렉션이 아니라 잘 정의 된 관련 멤버 집합 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f41d-116">✔️ DO ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6f41d-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6f41d-117">In This Section</span></span>
 <span data-ttu-id="6f41d-118">[클래스와 구조체](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md) [추상 클래스](../../../docs/standard/design-guidelines/abstract-class.md) 를 선택 합니다. 추상 클래스 디자인 [정적 클래스](../../../docs/standard/design-guidelines/static-class.md) 디자인 [인터페이스](../../../docs/standard/design-guidelines/interface.md) 디자인 [구조체](../../../docs/standard/design-guidelines/struct.md) 디자인 [열거형](../../../docs/standard/design-guidelines/enum.md) 디자인 [중첩 형식](../../../docs/standard/design-guidelines/nested-types.md) *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="6f41d-118">[Choosing Between Class and Struct](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md) [Abstract Class Design](../../../docs/standard/design-guidelines/abstract-class.md) [Static Class Design](../../../docs/standard/design-guidelines/static-class.md) [Interface Design](../../../docs/standard/design-guidelines/interface.md) [Struct Design](../../../docs/standard/design-guidelines/struct.md) [Enum Design](../../../docs/standard/design-guidelines/enum.md) [Nested Types](../../../docs/standard/design-guidelines/nested-types.md) *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6f41d-119">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="6f41d-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6f41d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f41d-120">See also</span></span>

- [<span data-ttu-id="6f41d-121">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6f41d-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
