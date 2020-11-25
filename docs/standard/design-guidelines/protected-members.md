---
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
ms.openlocfilehash: a6f36ac4f994fdc3211cac619cc0b20f7b0335b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730957"
---
# <a name="protected-members"></a><span data-ttu-id="7ac8c-102">보호된 멤버</span><span class="sxs-lookup"><span data-stu-id="7ac8c-102">Protected Members</span></span>

<span data-ttu-id="7ac8c-103">보호 된 멤버 자체는 확장성을 제공 하지 않지만 하위 클래스를 보다 강력 하 게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="7ac8c-104">이러한 옵션을 사용 하 여 기본 public 인터페이스를 불필요 하 게 복잡 하 게 하지 않고 고급 사용자 지정 옵션을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>

 <span data-ttu-id="7ac8c-105">"Protected" 라는 이름은 거짓 보안을 제공할 수 있기 때문에 프레임 워크 디자이너는 보호 된 멤버를 주의 해 서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="7ac8c-106">모든 사용자는 봉인 되지 않은 클래스를 서브클래싱하 고 보호 된 멤버에 액세스할 수 있으므로 public 멤버에 사용 되는 동일한 모든 방어 코딩 사례가 보호 된 멤버에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>

 <span data-ttu-id="7ac8c-107">고급 사용자 지정을 위해 보호 된 멤버를 사용 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-107">✔️ CONSIDER using protected members for advanced customization.</span></span>

 <span data-ttu-id="7ac8c-108">보안, 설명서 및 호환성 분석을 위해 봉인 되지 않은 클래스의 보호 된 멤버를 public으로 처리 하는 ✔️.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-108">✔️ DO treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>

 <span data-ttu-id="7ac8c-109">누구나 클래스에서 상속 하 고 보호 된 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac8c-109">Anyone can inherit from a class and access the protected members.</span></span>

 <span data-ttu-id="7ac8c-110">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="7ac8c-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="7ac8c-111">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="7ac8c-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="7ac8c-112">참조</span><span class="sxs-lookup"><span data-stu-id="7ac8c-112">See also</span></span>

- [<span data-ttu-id="7ac8c-113">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="7ac8c-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="7ac8c-114">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="7ac8c-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
