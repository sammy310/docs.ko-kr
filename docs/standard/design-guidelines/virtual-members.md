---
description: '자세한 정보: 가상 멤버'
title: 가상 멤버
ms.date: 10/22/2008
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 7618686764fb3a24ef53e5168b871366b7ffb5bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641787"
---
# <a name="virtual-members"></a><span data-ttu-id="00042-103">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="00042-103">Virtual Members</span></span>

<span data-ttu-id="00042-104">가상 멤버는 재정의할 수 있으므로 서브클래스의 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00042-104">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="00042-105">가상 멤버는 제공하는 확장성 측면에서 콜백과 매우 유사하지만 실행 성능과 메모리 사용 측면에서는 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="00042-105">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="00042-106">또한 가상 멤버는 특별한 종류의 기존 형식을 만들어야 하는 시나리오(특수화)에서 더욱 자연스럽게 느껴집니다.</span><span class="sxs-lookup"><span data-stu-id="00042-106">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>

 <span data-ttu-id="00042-107">가상 멤버는 콜백과 이벤트보다 성능이 우수하지만 비가상 메서드보다는 성능이 우수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00042-107">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>

 <span data-ttu-id="00042-108">가상 멤버의 주요 단점은 컴파일 시에만 가상 멤버의 동작을 수정할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="00042-108">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="00042-109">콜백의 동작은 런타임에 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00042-109">The behavior of a callback can be modified at runtime.</span></span>

 <span data-ttu-id="00042-110">가상 멤버에 대한 모든 호출은 예기치 않은 방식으로 재정의할 수 있고 임의 코드를 실행할 수 있기 때문에 콜백(콜백 이상일 수도 있음)과 같은 가상 멤버는 디자인, 테스트, 유지 관리 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="00042-110">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="00042-111">또한 가상 멤버의 계약을 명확하게 정의하려면 일반적으로 훨씬 더 큰 노력이 필요하므로 디자인 및 문서화 비용이 더 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="00042-111">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>

 <span data-ttu-id="00042-112">❌ 멤버를 가상으로 설정해야 할 합당한 이유가 없고 가상 멤버 디자인, 테스트, 유지 관리와 관련된 모든 비용을 파악하고 있지 않다면 멤버를 가상으로 설정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="00042-112">❌ DO NOT make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>

 <span data-ttu-id="00042-113">가상 멤버는 호환성을 손상하지 않고 변경할 수 있다는 측면에서 관대하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00042-113">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="00042-114">또한 대부분 가상 멤버에 대한 호출이 인라인이 아니기 때문에 비가상 멤버보다 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="00042-114">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>

 <span data-ttu-id="00042-115">✔️ 확장성을 꼭 필요한 항목으로만 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00042-115">✔️ CONSIDER limiting extensibility to only what is absolutely necessary.</span></span>

 <span data-ttu-id="00042-116">✔️ 가상 멤버에는 퍼블릭 접근성보다 보호된 접근성을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="00042-116">✔️ DO prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="00042-117">퍼블릭 멤버는 보호된 가상 멤버를 호출하여 확장성(필요한 경우)을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00042-117">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>

 <span data-ttu-id="00042-118">클래스의 퍼블릭 멤버는 해당 클래스의 직접 소비자에게 올바른 기능 세트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00042-118">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="00042-119">가상 멤버는 서브클래스에서 재정의하도록 설계되었으며 보호된 접근성은 모든 가상 확장 포인트의 범위를 사용할 수 있는 위치로 지정하는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="00042-119">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>

 <span data-ttu-id="00042-120">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="00042-120">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="00042-121">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="00042-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="00042-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00042-122">See also</span></span>

- [<span data-ttu-id="00042-123">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="00042-123">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="00042-124">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="00042-124">Designing for Extensibility</span></span>](designing-for-extensibility.md)
