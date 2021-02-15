---
description: '자세한 정보: 봉인되지 않은 클래스'
title: 봉인되지 않은 클래스
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 6fe30c3a2ef8df6b983d857b9502805e90ab83dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641826"
---
# <a name="unsealed-classes"></a><span data-ttu-id="95519-103">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="95519-103">Unsealed Classes</span></span>

<span data-ttu-id="95519-104">봉인된 클래스는 상속될 수 없으며 확장성을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="95519-104">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="95519-105">반대로 상속될 수 있는 클래스를 봉인되지 않은 클래스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95519-105">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="95519-106">✔️ 비용은 저렴하지만 뛰어난 확장성을 프레임워크에 제공하는 좋은 방법으로 가상 멤버나 보호된 멤버가 추가되지 않는 봉인되지 않은 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="95519-106">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="95519-107">개발자는 종종 사용자 지정 생성자, 새 메서드, 메서드 오버로드와 같은 편리한 멤버를 추가하기 위해 봉인되지 않은 클래스에서 상속하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95519-107">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="95519-108">예를 들어 `System.Messaging.MessageQueue`는 봉인되지 않았으므로 이를 통해 사용자는 특정 큐 경로로 기본 설정되는 사용자 지정 큐를 만들거나 특정 시나리오에 맞게 API를 간소화하는 사용자 지정 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95519-108">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="95519-109">클래스는 대부분의 프로그래밍 언어에서 기본적으로 봉인되지 않으며, 프레임워크에서 대부분의 클래스에 권장되는 기본값이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="95519-109">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="95519-110">봉인되지 않은 형식에서 제공하는 확장성은 프레임워크 사용자의 인정을 받고 있으며 봉인되지 않은 형식과 관련하여 상대적으로 낮은 테스트 비용으로 인해 제공 비용이 매우 저렴합니다.</span><span class="sxs-lookup"><span data-stu-id="95519-110">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="95519-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="95519-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="95519-112">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="95519-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="95519-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95519-113">See also</span></span>

- [<span data-ttu-id="95519-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="95519-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="95519-115">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="95519-115">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="95519-116">봉인</span><span class="sxs-lookup"><span data-stu-id="95519-116">Sealing</span></span>](sealing.md)
