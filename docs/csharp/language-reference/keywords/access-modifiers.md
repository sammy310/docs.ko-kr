---
description: 액세스 한정자 - C# 참조
title: 액세스 한정자 - C# 참조
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: e941fc673c508f10863ee49b6544d6886bd594a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168818"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="d1e13-103">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d1e13-103">Access Modifiers (C# Reference)</span></span>

<span data-ttu-id="d1e13-104">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-104">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="d1e13-105">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-105">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="d1e13-106">액세스 한정자를 사용하여 다음 여섯 가지 접근성 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-106">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="d1e13-107">[`public`](public.md): 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-107">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="d1e13-108">[`protected`](protected.md): 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-108">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="d1e13-109">[`internal`](internal.md): 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-109">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="d1e13-110">[`protected internal`](protected-internal.md): 액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-110">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="d1e13-111">[`private`](private.md): 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-111">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="d1e13-112">[`private protected`](private-protected.md): 액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-112">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="d1e13-113">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-113">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="d1e13-114">[접근성 수준](./accessibility-levels.md): 네 가지 액세스 한정자를 사용하여 여섯 가지 접근성 수준을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-114">[Accessibility Levels](./accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="d1e13-115">[접근성 도메인](./accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-115">[Accessibility Domain](./accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="d1e13-116">[접근성 수준 사용에 대한 제한](./restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 사항 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="d1e13-116">[Restrictions on Using Accessibility Levels](./restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e13-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1e13-117">See also</span></span>

- [<span data-ttu-id="d1e13-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d1e13-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d1e13-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d1e13-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d1e13-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d1e13-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d1e13-121">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="d1e13-121">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="d1e13-122">액세스 키워드</span><span class="sxs-lookup"><span data-stu-id="d1e13-122">Access Keywords</span></span>](base.md)
- [<span data-ttu-id="d1e13-123">한정자</span><span class="sxs-lookup"><span data-stu-id="d1e13-123">Modifiers</span></span>](index.md)
