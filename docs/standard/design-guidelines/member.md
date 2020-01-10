---
title: 멤버 디자인 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709272"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="a4fa9-102">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a4fa9-102">Member Design Guidelines</span></span>
<span data-ttu-id="a4fa9-103">메서드, 속성, 이벤트, 생성자 및 필드는 집합적으로 멤버 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fa9-103">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="a4fa9-104">멤버는 궁극적으로 프레임 워크의 최종 사용자에 게 노출 되는 프레임 워크 기능을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fa9-104">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="a4fa9-105">멤버는 가상 또는 비가상, 구체적 또는 추상, 정적 또는 인스턴스일 수 있으며 다양 한 액세스 가능성 범위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4fa9-105">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="a4fa9-106">이러한 모든 기능을 다양 하 게 제공 하지만, 동시에는 프레임 워크 디자이너의 일부를 표현을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fa9-106">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="a4fa9-107">이 장에서는 모든 형식의 멤버를 디자인할 때 따라야 하는 기본 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4fa9-107">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4fa9-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a4fa9-108">In This Section</span></span>  
 [<span data-ttu-id="a4fa9-109">멤버 오버로드</span><span class="sxs-lookup"><span data-stu-id="a4fa9-109">Member Overloading</span></span>](../../../docs/standard/design-guidelines/member-overloading.md)  
 [<span data-ttu-id="a4fa9-110">속성 디자인</span><span class="sxs-lookup"><span data-stu-id="a4fa9-110">Property Design</span></span>](../../../docs/standard/design-guidelines/property.md)  
 [<span data-ttu-id="a4fa9-111">생성자 디자인</span><span class="sxs-lookup"><span data-stu-id="a4fa9-111">Constructor Design</span></span>](../../../docs/standard/design-guidelines/constructor.md)  
 [<span data-ttu-id="a4fa9-112">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="a4fa9-112">Event Design</span></span>](../../../docs/standard/design-guidelines/event.md)  
 [<span data-ttu-id="a4fa9-113">필드 디자인</span><span class="sxs-lookup"><span data-stu-id="a4fa9-113">Field Design</span></span>](../../../docs/standard/design-guidelines/field.md)  
 [<span data-ttu-id="a4fa9-114">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="a4fa9-114">Extension Methods</span></span>](../../../docs/standard/design-guidelines/extension-methods.md)  
 [<span data-ttu-id="a4fa9-115">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="a4fa9-115">Operator Overloads</span></span>](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [<span data-ttu-id="a4fa9-116">매개 변수 디자인</span><span class="sxs-lookup"><span data-stu-id="a4fa9-116">Parameter Design</span></span>](../../../docs/standard/design-guidelines/parameter-design.md)  
 <span data-ttu-id="a4fa9-117">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="a4fa9-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a4fa9-118">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a4fa9-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4fa9-119">참조</span><span class="sxs-lookup"><span data-stu-id="a4fa9-119">See also</span></span>

- [<span data-ttu-id="a4fa9-120">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a4fa9-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
