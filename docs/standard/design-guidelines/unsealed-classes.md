---
title: 봉인되지 않은 클래스
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: 8a5f1142674f83b5ef77f9f7e7e3518afd475e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709012"
---
# <a name="unsealed-classes"></a><span data-ttu-id="a73e4-102">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="a73e4-102">Unsealed Classes</span></span>
<span data-ttu-id="a73e4-103">Sealed 클래스는에서 상속 될 수 없으며 확장성을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="a73e4-104">반면에서 상속할 수 있는 클래스는 봉인 되지 않은 클래스 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="a73e4-105">**✓ CONSIDER** 저렴 한 제공할 수 있는 좋은 방법 아직 훨씬 좋습니다 프레임 워크를 확장 하는 대로 가상 또는 보호 된 멤버를 추가 없이 봉인 되지 않은 클래스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="a73e4-106">개발자는 종종 사용자 지정 생성자, 새 메서드 또는 메서드 오버 로드와 같은 편리한 멤버를 추가 하기 위해 봉인 되지 않은 클래스에서 상속 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="a73e4-107">예를 들어 `System.Messaging.MessageQueue`은 봉인 되지 않으므로 사용자가 특정 큐 경로에 대 한 기본 사용자 지정 큐를 만들거나 특정 시나리오에 대 한 API를 간소화 하는 사용자 지정 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="a73e4-108">대부분의 프로그래밍 언어에서 클래스는 기본적으로 봉인 되지 않으므로 프레임 워크의 대부분의 클래스에 권장 되는 기본값 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73e4-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="a73e4-109">봉인 되지 않은 형식에서 제공 하는 확장성은 프레임 워크 사용자에 게 많은 감사를 보내고 봉인 되지 않은 형식과 관련 하 여 상대적으로 낮은 테스트 비용으로 인해 제공 하기에 많은 비용이 듭니다</span><span class="sxs-lookup"><span data-stu-id="a73e4-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="a73e4-110">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="a73e4-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a73e4-111">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a73e4-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73e4-112">참조</span><span class="sxs-lookup"><span data-stu-id="a73e4-112">See also</span></span>

- [<span data-ttu-id="a73e4-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a73e4-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a73e4-114">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="a73e4-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="a73e4-115">봉인</span><span class="sxs-lookup"><span data-stu-id="a73e4-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
