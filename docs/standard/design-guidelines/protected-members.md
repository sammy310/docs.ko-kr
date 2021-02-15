---
description: '자세한 정보: 보호된 멤버'
title: 보호된 멤버
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 5860828a5a469c77fbee001d01460a488fda4edf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731762"
---
# <a name="protected-members"></a><span data-ttu-id="448f1-103">보호된 멤버</span><span class="sxs-lookup"><span data-stu-id="448f1-103">Protected Members</span></span>

<span data-ttu-id="448f1-104">보호된 멤버는 그 자체로 확장성을 제공하지 않지만 서브클래스를 통해 확장성을 더 강력하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-104">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="448f1-105">보호된 멤버를 사용하면 기본 퍼블릭 인터페이스를 쓸데없이 복잡하게 만들지 않고도 고급 사용자 지정 옵션을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-105">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="448f1-106">“보호된”이라는 이름이 잘못된 보안의 의미를 제공할 수 있기 때문에 프레임워크 디자이너에서 보호된 멤버를 사용할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-106">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="448f1-107">누구나 봉인되지 않은 클래스를 서브클래싱하고 보호된 멤버에 액세스할 수 있으므로 퍼블릭 멤버에 사용되는 모든 동일한 방어적인 코딩 방식이 보호된 멤버에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-107">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="448f1-108">✔️ 고급 사용자 지정에는 보호된 멤버를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-108">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="448f1-109">✔️ 보안, 문서화, 호환성 분석을 위해 봉인되지 않은 클래스의 보호된 멤버를 퍼블릭으로 처리하세요.</span><span class="sxs-lookup"><span data-stu-id="448f1-109">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="448f1-110">누구나 클래스에서 상속하고 보호된 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448f1-110">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="448f1-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="448f1-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="448f1-112">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="448f1-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="448f1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448f1-113">See also</span></span>

- [<span data-ttu-id="448f1-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="448f1-114">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="448f1-115">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="448f1-115">Designing for Extensibility</span></span>](designing-for-extensibility.md)
