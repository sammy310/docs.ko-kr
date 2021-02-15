---
description: '자세한 정보: 추상화(추상 형식 및 인터페이스)'
title: 추상화(추상 형식 및 인터페이스)
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: 8dc82f004d655429e842c63fab4defff0fd74ab2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642443"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="2d2d0-103">추상화(추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="2d2d0-103">Abstractions (Abstract Types and Interfaces)</span></span>

<span data-ttu-id="2d2d0-104">추상화는 계약을 설명하지만 계약의 전체 구현을 제공하지는 않는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-104">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="2d2d0-105">일반적으로 추상화는 추상 클래스 또는 인터페이스로 구현되며, 계약을 구현하는 형식의 필수 의미 체계를 설명하는 잘 정의된 참조 설명서 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-105">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="2d2d0-106">.NET Framework에서 가장 중요한 몇 가지 추상화로는 <xref:System.IO.Stream><xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.Object>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-106">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>

 <span data-ttu-id="2d2d0-107">추상화의 계약을 지원하는 구체적인 형식을 구현하고 추상화를 사용하거나 추상화에서 작동하는 프레임워크 API에서 이 구체적인 형식을 사용하여 프레임워크를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-107">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>

 <span data-ttu-id="2d2d0-108">시간 테스트를 견딜 수 있는 의미 있고 유용한 추상화는 디자인하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-108">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="2d2d0-109">가장 어려운 점은 올바른 멤버 세트를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-109">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="2d2d0-110">추상화에 너무 많은 멤버가 있으면 구현하기 어렵거나 구현이 불가능할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-110">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="2d2d0-111">약속된 기능에 너무 적은 멤버가 사용되면 많은 흥미로운 시나리오에서 쓸모가 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-111">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>

 <span data-ttu-id="2d2d0-112">한 프레임워크에 너무 많은 추상화가 있으면 프레임워크의 유용성에도 부정적인 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-112">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="2d2d0-113">추상화에서 작동하는 API 및 구체적 구현이라는 더 큰 그림에 어떻게 적용되는지를 이해하지 못하면 추상화를 이해하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-113">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="2d2d0-114">또한 추상화의 이름과 해당 멤버도 당연히 추상이기 때문에 추상화 사용의 더 광범위한 컨텍스트를 먼저 이해하지 못하면 매우 복잡하고 접근하기 어려운 개념이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-114">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>

 <span data-ttu-id="2d2d0-115">그러나 추상화는 다른 확장성 메커니즘에서 제공할 수 없는 매우 강력한 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-115">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="2d2d0-116">추상화는 플러그 인, IoC(Inversion of Control), 파이프라인 등의 많은 아키텍처 패턴의 핵심에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-116">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="2d2d0-117">또한 프레임워크의 테스트 가능성에도 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-117">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="2d2d0-118">적절한 추상화를 사용하면 유닛 테스트를 위해 많은 종속성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-118">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="2d2d0-119">요약하자면 추상화는 최신 개체 지향 프레임워크의 인기 있는 풍부한 기능을 책임집니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-119">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>

 <span data-ttu-id="2d2d0-120">❌ 추상화를 사용하는 API 및 여러 가지 구체적인 구현을 개발하여 테스트하는 경우가 아니라면 추상화를 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-120">❌ DO NOT provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>

 <span data-ttu-id="2d2d0-121">✔️ 추상화를 설계할 때는 추상 클래스와 인터페이스 중에서 신중하게 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-121">✔️ DO choose carefully between an abstract class and an interface when designing an abstraction.</span></span>

 <span data-ttu-id="2d2d0-122">✔️ 추상화의 구체적인 구현을 위해 참조 테스트를 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-122">✔️ CONSIDER providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="2d2d0-123">이러한 테스트를 통해 사용자는 구현에서 계약을 올바르게 구현하는지를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2d0-123">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>

 <span data-ttu-id="2d2d0-124">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="2d2d0-124">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2d2d0-125">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2d2d0-125">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2d2d0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d2d0-126">See also</span></span>

- [<span data-ttu-id="2d2d0-127">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="2d2d0-127">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="2d2d0-128">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="2d2d0-128">Designing for Extensibility</span></span>](designing-for-extensibility.md)
