---
title: 확장성을 위한 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 406c15b6ce42b637ed1bbb61761d05e040995579
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280246"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="5d1ab-102">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="5d1ab-102">Designing for Extensibility</span></span>
<span data-ttu-id="5d1ab-103">프레임 워크를 설계할 때 중요 한 한 가지 측면은 프레임 워크의 확장성을 신중 하 게 고려 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="5d1ab-104">이렇게 하려면 다양 한 확장성 메커니즘과 관련 된 비용 및 혜택을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="5d1ab-105">이 장은 프레임 워크의 요구 사항을 가장 잘 충족할 수 있는 하위 클래스, 이벤트, 가상 멤버, 콜백 등의 확장성 메커니즘을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="5d1ab-106">여러 가지 방법으로 프레임 워크에서 확장성을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="5d1ab-107">강력 하지만 비용이 저렴 하지만 매우 강력 하지만 비용이 저렴 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="5d1ab-108">지정 된 확장성 요구 사항에 대 한 요구 사항을 충족 하는 최소 비용 확장성 메커니즘을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="5d1ab-109">일반적으로 나중에 확장성을 더 추가할 수 있지만, 주요 변경 사항을 도입 하지 않고 다시 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d1ab-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d1ab-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5d1ab-110">In This Section</span></span>  
 [<span data-ttu-id="5d1ab-111">봉인 되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="5d1ab-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="5d1ab-112">보호 된 멤버</span><span class="sxs-lookup"><span data-stu-id="5d1ab-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="5d1ab-113">이벤트 및 콜백</span><span class="sxs-lookup"><span data-stu-id="5d1ab-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="5d1ab-114">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="5d1ab-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="5d1ab-115">추상화 (추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="5d1ab-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="5d1ab-116">추상화 구현을 위한 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="5d1ab-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="5d1ab-117">봉인</span><span class="sxs-lookup"><span data-stu-id="5d1ab-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="5d1ab-118">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="5d1ab-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5d1ab-119">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5d1ab-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d1ab-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d1ab-120">See also</span></span>

- [<span data-ttu-id="5d1ab-121">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5d1ab-121">Framework Design Guidelines</span></span>](index.md)
