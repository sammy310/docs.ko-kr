---
description: 액세스 가능성 수준 - C# 참조
title: 액세스 가능성 수준 - C# 참조
ms.date: 12/06/2017
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
ms.openlocfilehash: 509902e9998af421c0afd31070b1be36d64df0f8
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604595"
---
# <a name="accessibility-levels-c-reference"></a><span data-ttu-id="d8823-103">액세스 가능성 수준(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d8823-103">Accessibility Levels (C# Reference)</span></span>

<span data-ttu-id="d8823-104">액세스 한정자 `public`, `protected`, `internal` 또는 `private`을 사용하여 멤버에 대해 다음과 같이 선언된 접근성 수준 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-104">Use the access modifiers, `public`, `protected`, `internal`, or `private`, to specify one of the following declared accessibility levels for members.</span></span>  
  
|<span data-ttu-id="d8823-105">선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="d8823-105">Declared accessibility</span></span>|<span data-ttu-id="d8823-106">의미</span><span class="sxs-lookup"><span data-stu-id="d8823-106">Meaning</span></span>|  
|----------------------------|-------------|  
|[`public`](public.md)|<span data-ttu-id="d8823-107">액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-107">Access is not restricted.</span></span>|  
|[`protected`](protected.md)|<span data-ttu-id="d8823-108">액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-108">Access is limited to the containing class or types derived from the containing class.</span></span>|  
|[`internal`](internal.md)|<span data-ttu-id="d8823-109">액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-109">Access is limited to the current assembly.</span></span>|  
|[`protected internal`](protected-internal.md)|<span data-ttu-id="d8823-110">액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-110">Access is limited to the current assembly or types derived from the containing class.</span></span>|  
|[`private`](private.md)|<span data-ttu-id="d8823-111">액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-111">Access is limited to the containing type.</span></span>|  
|[`private protected`](private-protected.md)|<span data-ttu-id="d8823-112">액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-112">Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span> <span data-ttu-id="d8823-113">C# 7.2부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-113">Available since C# 7.2.</span></span> |  
  
 <span data-ttu-id="d8823-114">`protected internal` 또는 `private protected` 조합을 사용할 경우를 제외하고 멤버 또는 형식에는 액세스 한정자가 하나만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-114">Only one access modifier is allowed for a member or type, except when you use the `protected internal` or `private protected` combinations.</span></span>  
  
 <span data-ttu-id="d8823-115">네임스페이스에는 액세스 한정자가 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-115">Access modifiers are not allowed on namespaces.</span></span> <span data-ttu-id="d8823-116">네임스페이스에는 액세스 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-116">Namespaces have no access restrictions.</span></span>  
  
 <span data-ttu-id="d8823-117">멤버 선언이 발생한 컨텍스트에 따라 특정 선언된 액세스 가능성만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-117">Depending on the context in which a member declaration occurs, only certain declared accessibilities are permitted.</span></span> <span data-ttu-id="d8823-118">액세스 한정자가 멤버 선언에서 지정되지 않으면 기본 액세스 가능성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-118">If no access modifier is specified in a member declaration, a default accessibility is used.</span></span>  
  
 <span data-ttu-id="d8823-119">다른 형식에 중첩되지 않은 최상위 형식에는 `internal` 또는 `public` 액세스 가능성만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-119">Top-level types, which are not nested in other types, can only have `internal` or `public` accessibility.</span></span> <span data-ttu-id="d8823-120">이러한 형식에 대한 기본 액세스 가능성은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-120">The default accessibility for these types is `internal`.</span></span>  
  
 <span data-ttu-id="d8823-121">다음 표에 나와 있는 대로 다른 형식의 멤버인 중첩 형식에는 선언된 액세스 가능성이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-121">Nested types, which are members of other types, can have declared accessibilities as indicated in the following table.</span></span>  
  
|<span data-ttu-id="d8823-122">소속 그룹</span><span class="sxs-lookup"><span data-stu-id="d8823-122">Members of</span></span>|<span data-ttu-id="d8823-123">기본 멤버 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="d8823-123">Default member accessibility</span></span>|<span data-ttu-id="d8823-124">멤버의 허용된 선언된 액세스 가능성</span><span class="sxs-lookup"><span data-stu-id="d8823-124">Allowed declared accessibility of the member</span></span>|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|<span data-ttu-id="d8823-125">None</span><span class="sxs-lookup"><span data-stu-id="d8823-125">None</span></span>|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`\*<br /><br /> `protected internal` <br /><br />`private protected`|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  

<span data-ttu-id="d8823-126">\*: `private` 액세스 가능성이 있는 `interface` 멤버에는 기본 구현이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-126">\* An `interface` member with `private` accessibility must have a default implementation.</span></span>

<span data-ttu-id="d8823-127">중첩된 형식의 액세스 가능성은 액세스 가능 도메인에 따라 다릅니다. [액세스 가능성 도메인](./accessibility-domain.md)은 멤버에 대해 선언된 액세스 가능성 및 한 수준 위 형식의 액세스 가능성 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-127">The accessibility of a nested type depends on its [accessibility domain](./accessibility-domain.md), which is determined by both the declared accessibility of the member and the accessibility domain of the immediately containing type.</span></span> <span data-ttu-id="d8823-128">그러나 중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 벗어날 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8823-128">However, the accessibility domain of a nested type cannot exceed that of the containing type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d8823-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d8823-129">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8823-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8823-130">See also</span></span>

- [<span data-ttu-id="d8823-131">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d8823-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d8823-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d8823-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d8823-133">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d8823-133">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d8823-134">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="d8823-134">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d8823-135">내게 필요한 옵션 도메인</span><span class="sxs-lookup"><span data-stu-id="d8823-135">Accessibility Domain</span></span>](./accessibility-domain.md)
- [<span data-ttu-id="d8823-136">내게 필요한 옵션 수준 사용에 대한 제한</span><span class="sxs-lookup"><span data-stu-id="d8823-136">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="d8823-137">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="d8823-137">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="d8823-138">public</span><span class="sxs-lookup"><span data-stu-id="d8823-138">public</span></span>](./public.md)
- [<span data-ttu-id="d8823-139">private</span><span class="sxs-lookup"><span data-stu-id="d8823-139">private</span></span>](./private.md)
- [<span data-ttu-id="d8823-140">protected</span><span class="sxs-lookup"><span data-stu-id="d8823-140">protected</span></span>](./protected.md)
- [<span data-ttu-id="d8823-141">internal</span><span class="sxs-lookup"><span data-stu-id="d8823-141">internal</span></span>](./internal.md)
