---
title: 봉인
ms.date: 10/22/2008
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: 29023ad431f9d05caf44e59f66eccee24bfa0433
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828688"
---
# <a name="sealing"></a><span data-ttu-id="6e937-102">봉인</span><span class="sxs-lookup"><span data-stu-id="6e937-102">Sealing</span></span>
<span data-ttu-id="6e937-103">개체 지향 프레임 워크의 기능 중 하나는 개발자가 프레임 워크 디자이너에서 예기치 않은 방식으로 확장 하 고 사용자 지정할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="6e937-104">이는 확장 가능한 디자인의 기능과 위험입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="6e937-105">프레임 워크를 설계할 때, 원하는 경우 확장성을 신중 하 게 디자인 하 고, 위험에 따라 확장성을 제한 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>

 <span data-ttu-id="6e937-106">확장성을 방지 하는 강력한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="6e937-107">클래스 또는 개별 멤버를 봉인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="6e937-108">클래스를 봉인 하면 사용자가 클래스에서 상속 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="6e937-109">멤버를 봉인 하면 사용자가 특정 멤버를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-109">Sealing a member prevents users from overriding a particular member.</span></span>

 <span data-ttu-id="6e937-110">❌ 적절 한 이유가 없는 클래스를 봉인 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6e937-110">❌ DO NOT seal classes without having a good reason to do so.</span></span>

 <span data-ttu-id="6e937-111">확장성 시나리오를 고려할 수 없기 때문에 클래스를 봉인 하는 것은 좋은 이유가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="6e937-112">편리한 멤버를 추가 하는 등의 다양 한 이유로 클래스에서 상속 하는 것과 같은 프레임 워크 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="6e937-113">사용자가 형식에서 상속 하려는 명백한 이유의 예는 봉인 되지 않은 [클래스](unsealed-classes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e937-113">See [Unsealed Classes](unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>

 <span data-ttu-id="6e937-114">클래스를 봉인 하는 좋은 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-114">Good reasons for sealing a class include the following:</span></span>

- <span data-ttu-id="6e937-115">클래스가 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-115">The class is a static class.</span></span> <span data-ttu-id="6e937-116">[정적 클래스 디자인](static-class.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e937-116">See [Static Class Design](static-class.md).</span></span>

- <span data-ttu-id="6e937-117">클래스는 보안에 중요 한 비밀을 상속 된 protected 멤버에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-117">The class stores security-sensitive secrets in inherited protected members.</span></span>

- <span data-ttu-id="6e937-118">클래스는 많은 가상 멤버를 상속 하 고 개별적으로 봉인 하는 비용은 클래스를 봉인 되지 않은 경우의 이점 보다 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>

- <span data-ttu-id="6e937-119">클래스는 매우 빠른 런타임 조회를 필요로 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="6e937-120">봉인 된 특성의 성능 수준은 봉인 되지 않은 특성 보다 약간 높습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="6e937-121">[특성](attributes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e937-121">See [Attributes](attributes.md).</span></span>

 <span data-ttu-id="6e937-122">❌ Protected 또는 virtual 멤버를 sealed 형식으로 선언 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6e937-122">❌ DO NOT declare protected or virtual members on sealed types.</span></span>

 <span data-ttu-id="6e937-123">정의에 따라 sealed 형식은에서 상속 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="6e937-124">이는 sealed 형식의 보호 된 멤버를 호출할 수 없고 sealed 형식의 가상 메서드를 재정의할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>

 <span data-ttu-id="6e937-125">재정의 하는 멤버를 봉인 하는 것을 고려 ✔️.</span><span class="sxs-lookup"><span data-stu-id="6e937-125">✔️ CONSIDER sealing members that you override.</span></span>

 <span data-ttu-id="6e937-126">가상 멤버를 도입할 때 발생할 수 있는 문제 ( [가상 멤버](virtual-members.md)에 설명 됨)는 약간 낮은 수준 이지만 재정의에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="6e937-127">재정의를 봉인 하면 상속 계층 구조의 해당 지점부터 시작 하 여 이러한 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e937-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>

 <span data-ttu-id="6e937-128">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="6e937-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6e937-129">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="6e937-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6e937-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e937-130">See also</span></span>

- [<span data-ttu-id="6e937-131">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6e937-131">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="6e937-132">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="6e937-132">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="6e937-133">봉인 되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="6e937-133">Unsealed Classes</span></span>](unsealed-classes.md)
