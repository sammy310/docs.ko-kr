---
title: 추상 클래스 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 018dd353024e75e9819f5a97008f2f422ecad291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739060"
---
# <a name="abstract-class-design"></a><span data-ttu-id="b480f-102">추상 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="b480f-102">Abstract Class Design</span></span>

<span data-ttu-id="b480f-103">추상 형식에서 public 또는 protected internal 생성자를 정의 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="b480f-103">❌ DO NOT define public or protected internal constructors in abstract types.</span></span>

 <span data-ttu-id="b480f-104">생성자는 사용자가 형식의 인스턴스를 만들어야 하는 경우에만 public 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="b480f-105">추상 형식의 인스턴스를 만들 수 없기 때문에 public 생성자가 포함 된 추상 형식이 잘못 디자인 되 고 사용자의 잘못 된 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>

 <span data-ttu-id="b480f-106">추상 클래스에서 protected 또는 internal 생성자를 정의 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-106">✔️ DO define a protected or an internal constructor in abstract classes.</span></span>

 <span data-ttu-id="b480f-107">Protected 생성자는 보다 일반적 이며, 하위 형식이 만들어질 때 기본 클래스에서 자체 초기화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>

 <span data-ttu-id="b480f-108">내부 생성자를 사용 하 여 추상 클래스의 구체적인 구현을 클래스를 정의 하는 어셈블리로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>

 <span data-ttu-id="b480f-109">제공 하는 각 추상 클래스에서 상속 되는 하나 이상의 구체적 형식을 제공 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-109">✔️ DO provide at least one concrete type that inherits from each abstract class that you ship.</span></span>

 <span data-ttu-id="b480f-110">이렇게 하면 추상 클래스 디자인의 유효성을 검사 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="b480f-111">예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType>은 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b480f-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>

 <span data-ttu-id="b480f-112">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="b480f-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b480f-113">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b480f-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b480f-114">참조</span><span class="sxs-lookup"><span data-stu-id="b480f-114">See also</span></span>

- [<span data-ttu-id="b480f-115">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b480f-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="b480f-116">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b480f-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
