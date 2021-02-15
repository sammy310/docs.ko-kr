---
description: '자세한 정보: 추상 클래스 디자인'
title: 추상 클래스 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 5b1cd833bf43e5bf5731176243809393187e84d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642463"
---
# <a name="abstract-class-design"></a><span data-ttu-id="6c8c6-103">추상 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="6c8c6-103">Abstract Class Design</span></span>

<span data-ttu-id="6c8c6-104">❌ 추상 형식에서 퍼블릭 또는 보호된 내부 생성자를 정의하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-104">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="6c8c6-105">사용자가 형식의 인스턴스를 만들어야 하는 경우에만 생성자는 퍼블릭이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-105">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="6c8c6-106">추상 형식의 인스턴스를 만들 수 없기 때문에 퍼블릭 생성자가 있는 추상 형식은 잘못 설계된 것이며 사용자가 오해할 여지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-106">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="6c8c6-107">✔️ 추상 클래스에서 보호된 또는 내부 생성자를 정의하세요.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-107">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="6c8c6-108">보호된 생성자는 더 일반적이며 하위 형식을 만들 때 기본 클래스에서 자체적으로 초기화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-108">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="6c8c6-109">내부 생성자는 추상 클래스의 구체적인 구현을 클래스를 정의하는 어셈블리로 제한하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-109">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="6c8c6-110">✔️ 제공되는 각 추상 클래스에서 상속되는 구체적인 형식을 하나 이상 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-110">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="6c8c6-111">그러면 추상 클래스 디자인의 유효성을 검사하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-111">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="6c8c6-112">예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType>은 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="6c8c6-112">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="6c8c6-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="6c8c6-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6c8c6-114">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="6c8c6-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6c8c6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c8c6-115">See also</span></span>

- [<span data-ttu-id="6c8c6-116">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6c8c6-116">Type Design Guidelines</span></span>](type.md)
- [<span data-ttu-id="6c8c6-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6c8c6-117">Framework Design Guidelines</span></span>](index.md)
