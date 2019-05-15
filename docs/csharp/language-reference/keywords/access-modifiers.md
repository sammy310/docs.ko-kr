---
title: 액세스 한정자 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 587f1b03292db643d721e599ea93c39ba188117d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593000"
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="45c62-102">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="45c62-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="45c62-103">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="45c62-104">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-104">This section introduces the four access modifiers:</span></span>  
  
- `public`
- `protected`
- `internal`
- `private`
  
 <span data-ttu-id="45c62-105">액세스 한정자를 사용하여 다음 여섯 가지 접근성 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="45c62-106">[`public`](public.md): 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="45c62-107">[`protected`](protected.md): 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="45c62-108">[`internal`](internal.md): 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="45c62-109">[`protected internal`](protected-internal.md): 액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="45c62-110">[`private`](private.md): 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="45c62-111">[`private protected`](private-protected.md): 액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="45c62-112">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-112">This section also introduces the following:</span></span>  
  
- <span data-ttu-id="45c62-113">[액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md): 네 가지 액세스 한정자를 사용하여 여섯 가지 액세스 가능성 수준을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
- <span data-ttu-id="45c62-114">[액세스 가능성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
- <span data-ttu-id="45c62-115">[액세스 가능성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="45c62-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c62-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45c62-116">See also</span></span>

- [<span data-ttu-id="45c62-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="45c62-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="45c62-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="45c62-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="45c62-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="45c62-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="45c62-120">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="45c62-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="45c62-121">액세스 키워드</span><span class="sxs-lookup"><span data-stu-id="45c62-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)
- [<span data-ttu-id="45c62-122">한정자</span><span class="sxs-lookup"><span data-stu-id="45c62-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
