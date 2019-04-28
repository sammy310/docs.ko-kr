---
title: 추상화(추상 형식 및 인터페이스)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: KrzysztofCwalina
ms.openlocfilehash: fcf566c24677630fdbb1fcd0eb7628f830b3be2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789222"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="d0663-102">추상화(추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="d0663-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="d0663-103">추상 형식인 계약에 설명 하지만 계약의 전체 구현을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="d0663-104">추상화는 일반적으로 추상 클래스 또는 인터페이스를 구현 하 고 여기에 잘 정의 된 계약을 구현 하는 형식의 필요한 의미 체계를 설명 하는 참조 설명서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="d0663-105">.NET Framework의 가장 중요 한 추상화 같습니다 <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, 및 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="d0663-106">추상화의 계약을 지 원하는 구체적 형식 구현 및 프레임 워크 Api 사용 (작동 중에)이 구체적인 형식을 사용 하 여 프레임 워크를 확장할 수 있습니다를 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="d0663-107">시간 테스트를 견딜 수 있는 의미 있고 유용한 추상화를 디자인 하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="d0663-108">주요 문제는 멤버를 더 이상 더 적은 수의 올바른 집합을 가져오는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="d0663-109">추상화에 멤버가 너무 많은 경우 어렵거나 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="d0663-110">약속된 기능에 너무 적은 멤버가 있으면 많은 흥미로운 시나리오에서 쓸모 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="d0663-111">프레임 워크에서 너무 많은 추상화에는 프레임 워크의 유용성도 부정적인 영향을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="d0663-112">구체적인 구현과 추상화에서 작동 하는 Api의 큰 그림에 맞추는 방법을 알 수 없는 추상화를 이해 하기 어려운 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="d0663-113">또한 추상화 및 해당 멤버의 이름은 반드시 추상 종종을 사용 하면 복잡 하 고 차갑고 첫 번째 용도의 광범위 한 컨텍스트를 알 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="d0663-114">그러나 추상화 기타 확장성 메커니즘과 없습니다 자주 일치 하는 매우 강력한 확장성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="d0663-115">이들은 플러그 인과 같은 많은 아키텍처 패턴의 핵심 반전 (IoC) 제어, 파이프라인 및 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="d0663-116">프레임 워크의 테스트 용이성에 매우 중요 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="d0663-117">적절 한 추상화를 사용 하면 단위 테스트 목적으로 많은 종속성을 스텁 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="d0663-118">요약 하자면, 추상화 많았던 다양 한 최신 개체 지향 프레임 워크를 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="d0663-119">**X DO NOT** 여러 구체적인 구현 및 Api를 사용 하는 추상화를 개발 하 여 테스트 하지 않는 한 추상화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="d0663-120">**✓ DO** 추상화를 디자인할 때, 추상 클래스와 인터페이스를 신중 하 게 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="d0663-121">**✓ CONSIDER** 추상화의 구체적인 구현에 대 한 참조 테스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="d0663-122">이러한 테스트는 구현 계약을 올바르게 구현 하는지 여부를 테스트 하도록 사용자를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0663-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="d0663-123">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d0663-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d0663-124">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="d0663-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0663-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0663-125">See also</span></span>

- [<span data-ttu-id="d0663-126">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d0663-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="d0663-127">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="d0663-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
