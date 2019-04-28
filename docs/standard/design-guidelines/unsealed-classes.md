---
title: 봉인되지 않은 클래스
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: d7174de7ddf062b829672e04952c1010fcb74058
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778796"
---
# <a name="unsealed-classes"></a><span data-ttu-id="da461-102">봉인되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="da461-102">Unsealed Classes</span></span>
<span data-ttu-id="da461-103">봉인 된 클래스에서 상속 될 수 없습니다 및 확장성을 방해 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da461-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="da461-104">반면, 클래스에서 상속 되는 봉인 되지 않은 클래스 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="da461-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>  
  
 <span data-ttu-id="da461-105">**✓ CONSIDER** 저렴 한 제공할 수 있는 좋은 방법 아직 훨씬 좋습니다 프레임 워크를 확장 하는 대로 가상 또는 보호 된 멤버를 추가 없이 봉인 되지 않은 클래스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="da461-105">**✓ CONSIDER** using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>  
  
 <span data-ttu-id="da461-106">개발자가 사용자 지정 생성자, 새 메서드 또는 메서드 오버 로드와 같은 편리한 멤버를 추가 하기 위해 봉인 되지 않은 클래스에서 상속 하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="da461-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="da461-107">예를 들어 `System.Messaging.MessageQueue` 봉인 되지 않으며 따라서 사용자는 기본적으로 특정 큐 경로 사용자 지정 큐를 만들거나 특정 시나리오에 대 한 API를 간소화 하는 사용자 지정 메서드 추가 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da461-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>  
  
 <span data-ttu-id="da461-108">클래스는 대부분의 프로그래밍 언어에서 기본적으로 봉인 되지 않은 및 프레임 워크에서 대부분의 클래스에 대 한 권장 되는 기본값 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="da461-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="da461-109">봉인 되지 않은 형식에서 제공 하는 확장성 프레임 워크 사용자가 훨씬 학문적 이며 봉인 되지 않은 형식과 연결 된 상대적으로 낮은 테스트 비용으로 인해 제공 매우 저렴 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="da461-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>  
  
 <span data-ttu-id="da461-110">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="da461-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="da461-111">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="da461-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da461-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="da461-112">See also</span></span>

- [<span data-ttu-id="da461-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="da461-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="da461-114">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="da461-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [<span data-ttu-id="da461-115">봉인</span><span class="sxs-lookup"><span data-stu-id="da461-115">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)
