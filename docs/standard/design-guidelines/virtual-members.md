---
title: 가상 멤버
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 4943ddcdf1bc4e3e32c8d664cbcc5c50ae3959bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778710"
---
# <a name="virtual-members"></a><span data-ttu-id="3aaee-102">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="3aaee-102">Virtual Members</span></span>
<span data-ttu-id="3aaee-103">가상 멤버를 재정의할 수 있습니다 따라서 서브 클래스의 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="3aaee-104">콜백이 제공 되는 확장성 측면에서 매우 유사한 있지만 실행 성능 및 메모리 소비량 면에서 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="3aaee-105">또한 가상 멤버는 만들어야 하는 특별 한 종류의 기존 유형 (특수화의 경우) 시나리오에서 자연스럽 게 느낄 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="3aaee-106">가상 멤버 콜백과 이벤트 보다 성능이 우수 하지만 비가상 메서드 보다 더 잘 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="3aaee-107">가상 멤버의 주요 단점은 컴파일 시에 가상 멤버의 동작 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="3aaee-108">런타임 시 콜백의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="3aaee-109">콜백 (및 콜백을 보다 아마도) 등의 가상 멤버 비용이 많이 드는 디자인, 테스트 및 가상 멤버를 호출할 때 예기치 않은 방식으로 재정의할 수 있습니다를 임의 코드를 실행할 수 있으므로 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="3aaee-110">또한 훨씬 더 많은 노력이 명확 하 게 디자인 및 문서화 하는 비용을 더 높은 이므로 가상 멤버의 계약을 정의 하려면 일반적으로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="3aaee-111">**X DO NOT** 그러려면 이유가 있고 디자인, 테스트 및 가상 멤버를 유지 관리와 관련 된 모든 비용에 대해 알고에 가상 멤버를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="3aaee-112">가상 멤버는 호환성을 중단 하지 않고에 될 수 있는 변경 내용 측면에서 작은 관대 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="3aaee-113">또한 가상 멤버에 대 한 호출을 인라인 없는 때문에 대부분 비가상 멤버 보다 느린는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="3aaee-114">**✓ CONSIDER** 확장성 반드시 필요한 것만을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="3aaee-115">**✓ DO** 가상 멤버에 대 한 공용 액세스 가능성을 통해 보호 된 액세스 가능성을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="3aaee-116">공용 멤버 확장성을 제공 해야 (필요한 경우) 보호 된 가상 멤버를 호출 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="3aaee-117">클래스의 public 멤버는 해당 클래스의 직접 소비자에 대 한 올바른 기능 집합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="3aaee-118">가상 멤버는 하위 클래스에서 재정의 되도록 설계 하 고 보호 된 액세스 가능성은 편리 하 게 하는 모든 가상 확장성 지점을 사용할 수 있는 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="3aaee-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="3aaee-119">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="3aaee-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3aaee-120">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="3aaee-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aaee-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3aaee-121">See also</span></span>

- [<span data-ttu-id="3aaee-122">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="3aaee-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3aaee-123">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="3aaee-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
