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
author: KrzysztofCwalina
ms.openlocfilehash: 6eec3bb4575b89c6476e6c3410050c705141777f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785556"
---
# <a name="abstract-class-design"></a><span data-ttu-id="b2566-102">추상 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="b2566-102">Abstract Class Design</span></span>
<span data-ttu-id="b2566-103">**X DO NOT** 추상 형식에 public 또는 protected 내부 생성자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="b2566-104">생성자는 사용자가 형식의 인스턴스를 만들어야 하는 경우에 공용 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="b2566-105">추상 형식의 인스턴스를 만들 수 없으므로, public 생성자를 사용 하는 추상 형식이 아닌 경우 올바르게 설계 및 사용자에 게 잘못 된</span><span class="sxs-lookup"><span data-stu-id="b2566-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="b2566-106">**✓ DO** 추상 클래스에는 protected 또는 내부 생성자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="b2566-107">생성자는 protected 생성자는 좀 더 자주 및 하위 형식을 만들면 자체 초기화 작업을 수행 하는 기본 클래스를 사용 하는 단순히 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="b2566-108">추상 클래스를 정의 하는 어셈블리 클래스의 구체적 구현 제한 하는 내부 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="b2566-109">**✓ DO** 배송 된 각 추상 클래스에서 상속 하는 구체적인 형식이 하나 이상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="b2566-110">이 사용이 하면 추상 클래스의 디자인 유효성 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="b2566-111">예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType> 구현인는 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b2566-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="b2566-112">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="b2566-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b2566-113">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="b2566-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2566-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2566-114">See also</span></span>

- [<span data-ttu-id="b2566-115">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b2566-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="b2566-116">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b2566-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
