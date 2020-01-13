---
title: 액세스 한정자 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 754949e42771de30cc2dce7e4e610f70ada6dfd4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713851"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="23a98-102">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="23a98-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="23a98-103">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="23a98-104">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="23a98-105">액세스 한정자를 사용하여 다음 여섯 가지 접근성 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="23a98-106">[`public`](public.md): 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="23a98-107">[`protected`](protected.md): 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="23a98-108">[`internal`](internal.md): 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="23a98-109">[`protected internal`](protected-internal.md): 액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="23a98-110">[`private`](private.md): 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="23a98-111">[`private protected`](private-protected.md): 액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="23a98-112">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="23a98-113">[액세스 가능성 수준](./accessibility-levels.md): 네 가지 액세스 한정자를 사용하여 여섯 가지 액세스 가능성 수준을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-113">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="23a98-114">[액세스 가능성 도메인](./accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-114">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="23a98-115">[액세스 가능성 수준 사용에 대한 제한](./restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="23a98-115">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a98-116">참조</span><span class="sxs-lookup"><span data-stu-id="23a98-116">See also</span></span>

- [<span data-ttu-id="23a98-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="23a98-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="23a98-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="23a98-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="23a98-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="23a98-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="23a98-120">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="23a98-120">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="23a98-121">액세스 키워드</span><span class="sxs-lookup"><span data-stu-id="23a98-121">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="23a98-122">한정자</span><span class="sxs-lookup"><span data-stu-id="23a98-122">Modifiers</span></span>](index.md)
