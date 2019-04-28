---
title: 봉인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: KrzysztofCwalina
ms.openlocfilehash: c8aeb5ce3d93755f30bf68732592a08d7af54957
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762065"
---
# <a name="sealing"></a><span data-ttu-id="156fc-102">봉인</span><span class="sxs-lookup"><span data-stu-id="156fc-102">Sealing</span></span>
<span data-ttu-id="156fc-103">개체 지향 프레임 워크의 기능 중 하나에 개발자가 확장 하 고 프레임 워크 디자이너에서 예기치 않은 방식으로 사용자 지정할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="156fc-104">이 기능과 확장 가능한 디자인 하는 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="156fc-105">프레임 워크를 디자인할 때, 따라서, 원할 경우 신중 하 게 확장성에 대 한 디자인 및 위험한 경우 확장성 제한에 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="156fc-106">확장성을 방지 하는 강력한 메커니즘을 봉인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="156fc-107">클래스 또는 개별 멤버를 봉인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="156fc-108">클래스를 봉인 사용자를 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="156fc-109">멤버를 봉인 사용자를에서 특정 멤버를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="156fc-110">**X DO NOT** 이유가 할 필요 없이 클래스를 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="156fc-111">이유가 아닙니다 확장성 시나리오를 생각할 수 없습니다 때문에 클래스를 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="156fc-112">프레임 워크 사용자 편의 멤버를 추가 하는 등 다양 한 nonobvious 이유로 클래스에서 상속 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="156fc-113">참조 [봉인 되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md) nonobvious 이유의 예제를 보려면 사용자 형식에서 상속 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="156fc-114">봉인 클래스에 대 한 좋은 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-114">Good reasons for sealing a class include the following:</span></span>  
  
- <span data-ttu-id="156fc-115">클래스는 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-115">The class is a static class.</span></span> <span data-ttu-id="156fc-116">참조 [정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
- <span data-ttu-id="156fc-117">클래스는 상속 된 보호 된 멤버의 보안과 관련 된 비밀을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
- <span data-ttu-id="156fc-118">클래스는 여러 가상 멤버를 상속 하 고 비용을 개별적으로 봉인 클래스 봉인 되지 않은 유지 이점 보다 클 것입니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
- <span data-ttu-id="156fc-119">클래스에는 매우 빠른 런타임 조회를 필요로 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="156fc-120">Sealed 특성 경우 봉인 되지 않은 것 보다 약간 더 높은 성능 수준</span><span class="sxs-lookup"><span data-stu-id="156fc-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="156fc-121">참조 [특성](../../../docs/standard/design-guidelines/attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="156fc-122">**X DO NOT** 보호 또는 가상 멤버를 sealed 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="156fc-123">기본적으로 sealed 형식에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="156fc-124">즉, sealed 형식에 대해 보호 된 멤버를 호출할 수 없습니다를 sealed 형식에 대해 가상 메서드를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="156fc-125">**✓ CONSIDER** 재정의할 수 있는 멤버가 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="156fc-126">가상 멤버 소개에서 발생할 수 있는 문제 (에서 설명한 [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)) 약간 낮은 수준으로 지원 하지만 재정의를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="156fc-127">재정의가 봉인 하면 상속 계층의 해당 지점에서 시작 하는 이러한 문제 로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="156fc-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="156fc-128">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="156fc-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="156fc-129">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="156fc-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="156fc-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="156fc-130">See also</span></span>

- [<span data-ttu-id="156fc-131">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="156fc-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="156fc-132">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="156fc-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="156fc-133">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="156fc-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
