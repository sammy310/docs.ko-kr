---
description: '자세한 정보: 봉인'
title: 봉인
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: 94673f793aa7373e1076e13cbda900fba83786f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731723"
---
# <a name="sealing"></a><span data-ttu-id="738e5-103">봉인</span><span class="sxs-lookup"><span data-stu-id="738e5-103">Sealing</span></span>

<span data-ttu-id="738e5-104">개체 지향 프레임워크의 기능 중 하나는 프레임워크 디자이너에서 예상할 수 없는 방식으로 개발자가 프레임워크를 확장하고 사용자 지정할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-104">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="738e5-105">이 기능은 확장 가능한 디자인의 강력한 기능인 동시에 위험 요소이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-105">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="738e5-106">따라서 프레임워크를 디자인할 때 확장성이 필요하면 신중하게 디자인하고 위험한 경우에는 확장성을 제한하는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-106">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="738e5-107">확장성을 방지하는 강력한 메커니즘은 봉인입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-107">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="738e5-108">클래스 또는 개별 멤버를 봉인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-108">You can seal either the class or individual members.</span></span> <span data-ttu-id="738e5-109">클래스를 봉인하면 사용자가 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-109">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="738e5-110">멤버를 봉인하면 사용자가 특정 멤버를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-110">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="738e5-111">❌ 클래스를 봉인해야 할 적합한 이유가 없다면 봉인하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="738e5-111">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="738e5-112">확장성 시나리오를 고려할 수 없기 때문에 클래스를 봉인하는 것은 적합한 이유가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-112">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="738e5-113">프레임워크 사용자는 편의성 멤버 추가 등의 명백하지 않은 다양한 이유로 클래스에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-113">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="738e5-114">사용자가 형식에서 상속하려고 하는 명백하지 않은 이유에 대한 예는 [봉인되지 않은 클래스](unsealed-classes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="738e5-114">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="738e5-115">클래스를 봉인하는 적합한 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-115">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="738e5-116">클래스가 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-116">The class is a static class.</span></span> <span data-ttu-id="738e5-117">[정적 클래스 디자인](static-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="738e5-117">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="738e5-118">클래스가 상속된 보호된 멤버에 보안상 중요한 비밀을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-118">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="738e5-119">클래스가 많은 가상 멤버를 상속하며 개별적으로 봉인하는 비용이 클래스를 봉인되지 않은 상태로 유지하는 이점보다 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-119">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="738e5-120">클래스가 매우 빠른 런타임 조회를 필요로 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-120">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="738e5-121">봉인된 특성은 봉인되지 않은 특성보다 성능 수준이 약간 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-121">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="738e5-122">[특성](attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="738e5-122">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="738e5-123">❌ 봉인된 형식에서 보호된 멤버나 가상 멤버를 선언하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="738e5-123">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="738e5-124">정의에 따라 봉인된 형식에서는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-124">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="738e5-125">즉, 봉인된 형식의 보호된 멤버는 호출할 수 없고 봉인된 형식의 가상 메서드는 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-125">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="738e5-126">✔️ 재정의하는 멤버는 봉인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-126">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="738e5-127">가상 멤버([가상 멤버](virtual-members.md)에서 설명) 도입으로 발생할 수 있는 문제는 재정의에도 적용되지만 정도는 약간 더 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-127">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="738e5-128">재정의를 봉인하면 상속 계층 구조의 해당 지점부터 이러한 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-128">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="738e5-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="738e5-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="738e5-130">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="738e5-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="738e5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="738e5-131">See also</span></span>

- [<span data-ttu-id="738e5-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="738e5-132">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="738e5-133">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="738e5-133">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="738e5-134">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="738e5-134">Unsealed Classes</span></span>](unsealed-classes.md)
