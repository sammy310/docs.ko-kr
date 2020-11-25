---
title: 추상화(추상 형식 및 인터페이스)
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: f5169cf730dc987526765c9538978901d424814b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701408"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="ce480-102">추상화(추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="ce480-102">Abstractions (Abstract Types and Interfaces)</span></span>

<span data-ttu-id="ce480-103">추상화는 계약을 설명 하지만 계약의 전체 구현을 제공 하지 않는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="ce480-104">일반적으로 추상화는 추상 클래스 또는 인터페이스로 구현 되며, 계약을 구현 하는 형식의 필요한 의미 체계를 설명 하는 잘 정의 된 참조 설명서 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="ce480-105">.NET Framework에서 가장 중요 한 추상화 중 일부에는 <xref:System.IO.Stream> , 및가 포함 됩니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="ce480-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>

 <span data-ttu-id="ce480-106">추상화의 계약을 지 원하는 구체적인 형식을 구현 하 고 추상화를 사용 하는 프레임 워크 Api (운영)에서이 구체적인 형식을 사용 하 여 프레임 워크를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>

 <span data-ttu-id="ce480-107">시간 테스트를 견딜 수 있는 의미 있고 유용한 추상화는 디자인 하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="ce480-108">가장 어려운 문제는 멤버의 올바른 집합을 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="ce480-109">추상화에 멤버가 너무 많으면 구현이 어렵거나 구현할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="ce480-110">약속 된 기능에 대 한 멤버가 너무 적으면 많은 흥미로운 시나리오에서 쓸모가 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>

 <span data-ttu-id="ce480-111">프레임 워크에 너무 많은 추상화는 프레임 워크의 유용성에도 부정적인 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="ce480-112">추상화에 대해 작동 하는 구체적 구현 및 Api의 큰 그림에 얼마나 적합 한지 이해 하지 못하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="ce480-113">또한 추상화와 해당 멤버의 이름은 반드시 abstract로 설정 해야 하며,이는 종종 더 광범위 한 사용 컨텍스트를 이해 하지 않고 암호화 하 고 unapproachable 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>

 <span data-ttu-id="ce480-114">그러나 추상화는 다른 확장성 메커니즘이 자주 일치 하지 않는 매우 강력한 확장성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="ce480-115">플러그 인, IoC (반전 제어), 파이프라인 등의 많은 아키텍처 패턴의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="ce480-116">프레임 워크의 테스트 용이성에도 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="ce480-117">적절 한 추상화를 사용 하면 단위 테스트를 위해 많은 종속성을 스텁 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="ce480-118">요약 하자면, 추상화는 최신 개체 지향 프레임 워크의 풍부한 기능을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>

 <span data-ttu-id="ce480-119">❌ 추상화를 사용 하는 몇 가지 구체적인 구현 및 Api를 개발 하 여 테스트 하지 않는 한 추상화를 제공 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ce480-119">❌ DO NOT provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>

 <span data-ttu-id="ce480-120">추상화를 설계할 때 추상 클래스와 인터페이스 사이에서 신중 하 게 선택 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-120">✔️ DO choose carefully between an abstract class and an interface when designing an abstraction.</span></span>

 <span data-ttu-id="ce480-121">✔️ 추상화의 구체적인 구현에 대 한 참조 테스트를 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-121">✔️ CONSIDER providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="ce480-122">이러한 테스트를 통해 사용자는 구현에서 계약을 올바르게 구현 하는지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce480-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>

 <span data-ttu-id="ce480-123">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="ce480-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ce480-124">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ce480-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ce480-125">참조</span><span class="sxs-lookup"><span data-stu-id="ce480-125">See also</span></span>

- [<span data-ttu-id="ce480-126">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ce480-126">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="ce480-127">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="ce480-127">Designing for Extensibility</span></span>](designing-for-extensibility.md)
