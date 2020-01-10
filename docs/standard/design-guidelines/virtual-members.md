---
title: 가상 멤버
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 2c1e6d9aeafa1c9d7ee4b0c2c626b6fd7be6cf99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708973"
---
# <a name="virtual-members"></a><span data-ttu-id="2c7b1-102">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="2c7b1-102">Virtual Members</span></span>
<span data-ttu-id="2c7b1-103">가상 멤버를 재정의할 수 있으므로 하위 클래스의 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-103">Virtual members can be overridden, thus changing the behavior of the subclass.</span></span> <span data-ttu-id="2c7b1-104">이러한 항목은 제공 하는 확장성 측면에서 콜백과 매우 유사 하지만 실행 성능과 메모리 사용 측면에서 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-104">They are quite similar to callbacks in terms of the extensibility they provide, but they are better in terms of execution performance and memory consumption.</span></span> <span data-ttu-id="2c7b1-105">또한 가상 멤버는 특수 한 종류의 기존 형식 (특수화)을 만들어야 하는 시나리오에서 보다 자연스럽 게 느껴질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-105">Also, virtual members feel more natural in scenarios that require creating a special kind of an existing type (specialization).</span></span>  
  
 <span data-ttu-id="2c7b1-106">가상 멤버는 콜백과 이벤트 보다 성능이 우수 하지만 비가상 메서드 보다는 성능이 더 우수 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-106">Virtual members perform better than callbacks and events, but do not perform better than non-virtual methods.</span></span>  
  
 <span data-ttu-id="2c7b1-107">가상 멤버의 주요 단점은 컴파일할 때 가상 멤버의 동작을 수정할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-107">The main disadvantage of virtual members is that the behavior of a virtual member can only be modified at the time of compilation.</span></span> <span data-ttu-id="2c7b1-108">콜백의 동작은 런타임에 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-108">The behavior of a callback can be modified at runtime.</span></span>  
  
 <span data-ttu-id="2c7b1-109">가상 멤버에 대 한 모든 호출은 예측할 수 없는 방식으로 재정의 될 수 있고 임의의 코드를 실행할 수 있기 때문에 콜백과 같은 가상 멤버는 디자인, 테스트 및 유지 관리 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-109">Virtual members, like callbacks (and maybe more than callbacks), are costly to design, test, and maintain because any call to a virtual member can be overridden in unpredictable ways and can execute arbitrary code.</span></span> <span data-ttu-id="2c7b1-110">또한 일반적으로 가상 멤버의 계약을 명확 하 게 정의 하는 데 더 많은 노력을 기울여야 하므로 이러한 작업을 디자인 하 고 문서화 하는 비용이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-110">Also, much more effort is usually required to clearly define the contract of virtual members, so the cost of designing and documenting them is higher.</span></span>  
  
 <span data-ttu-id="2c7b1-111">**X DO NOT** 그러려면 이유가 있고 디자인, 테스트 및 가상 멤버를 유지 관리와 관련 된 모든 비용에 대해 알고에 가상 멤버를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-111">**X DO NOT** make members virtual unless you have a good reason to do so and you are aware of all the costs related to designing, testing, and maintaining virtual members.</span></span>  
  
 <span data-ttu-id="2c7b1-112">가상 멤버는 호환성을 손상 시 키 지 않고 변경 내용을 적용할 수 있는 측면에서 더 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-112">Virtual members are less forgiving in terms of changes that can be made to them without breaking compatibility.</span></span> <span data-ttu-id="2c7b1-113">또한 가상 멤버에 대 한 호출은 인라인 되지 않으므로 가상 멤버가 아닌 멤버 보다 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-113">Also, they are slower than non-virtual members, mostly because calls to virtual members are not inlined.</span></span>  
  
 <span data-ttu-id="2c7b1-114">**✓ CONSIDER** 확장성 반드시 필요한 것만을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-114">**✓ CONSIDER** limiting extensibility to only what is absolutely necessary.</span></span>  
  
 <span data-ttu-id="2c7b1-115">**✓ DO** 가상 멤버에 대 한 공용 액세스 가능성을 통해 보호 된 액세스 가능성을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-115">**✓ DO** prefer protected accessibility over public accessibility for virtual members.</span></span> <span data-ttu-id="2c7b1-116">Public 멤버는 보호 된 가상 멤버를 호출 하 여 확장성 (필요한 경우)을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-116">Public members should provide extensibility (if required) by calling into a protected virtual member.</span></span>  
  
 <span data-ttu-id="2c7b1-117">클래스의 public 멤버는 해당 클래스의 직접 소비자에 게 올바른 기능 집합을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-117">The public members of a class should provide the right set of functionality for direct consumers of that class.</span></span> <span data-ttu-id="2c7b1-118">가상 멤버는 서브 클래스에서 재정의 되도록 설계 되었으며, 보호 된 액세스 가능성은 모든 가상 확장 지점을 사용할 수 있는 위치로 범위를 지정할 수 있는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2c7b1-118">Virtual members are designed to be overridden in subclasses, and protected accessibility is a great way to scope all virtual extensibility points to where they can be used.</span></span>  
  
 <span data-ttu-id="2c7b1-119">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="2c7b1-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2c7b1-120">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="2c7b1-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c7b1-121">참조</span><span class="sxs-lookup"><span data-stu-id="2c7b1-121">See also</span></span>

- [<span data-ttu-id="2c7b1-122">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="2c7b1-122">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="2c7b1-123">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="2c7b1-123">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
