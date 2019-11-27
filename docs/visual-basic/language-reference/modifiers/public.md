---
title: Public
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351289"
---
# <a name="public-visual-basic"></a><span data-ttu-id="c142b-102">Public(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c142b-102">Public (Visual Basic)</span></span>
<span data-ttu-id="c142b-103">하나 이상의 선언 된 프로그래밍 요소에 액세스 제한이 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c142b-104">설명</span><span class="sxs-lookup"><span data-stu-id="c142b-104">Remarks</span></span>  
 <span data-ttu-id="c142b-105">클래스 라이브러리와 같은 구성 요소 또는 구성 요소 집합을 게시 하는 경우 일반적으로 어셈블리와 상호 작용 하는 코드에서 프로그래밍 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="c142b-106">요소에 대 한 무제한 액세스를 설정 하기 위해 `Public`를 사용 하 여 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="c142b-107">공용 액세스는 프로그래밍 요소에 대 한 액세스를 제한 하지 않아도 되는 일반적인 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="c142b-108">인터페이스, 모듈, 클래스 또는 구조체 내에서 선언 된 요소에 대 한 액세스 수준은 기본적으로 `Public` (그렇지 않은 경우)로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c142b-109">규칙</span><span class="sxs-lookup"><span data-stu-id="c142b-109">Rules</span></span>  
  
- <span data-ttu-id="c142b-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="c142b-110">**Declaration Context.**</span></span> <span data-ttu-id="c142b-111">`Public`는 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="c142b-112">즉, `Public` 요소에 대 한 선언 컨텍스트는 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 하 고 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c142b-113">동작</span><span class="sxs-lookup"><span data-stu-id="c142b-113">Behavior</span></span>  
  
- <span data-ttu-id="c142b-114">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="c142b-114">**Access Level.**</span></span> <span data-ttu-id="c142b-115">모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 `Public` 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="c142b-116">**기본 액세스.**</span><span class="sxs-lookup"><span data-stu-id="c142b-116">**Default Access.**</span></span> <span data-ttu-id="c142b-117">프로시저 내의 지역 변수는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="c142b-118">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="c142b-118">**Access Modifiers.**</span></span> <span data-ttu-id="c142b-119">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="c142b-120">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c142b-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="c142b-121">`Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c142b-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c142b-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="c142b-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="c142b-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="c142b-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="c142b-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="c142b-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="c142b-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="c142b-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="c142b-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="c142b-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="c142b-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="c142b-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="c142b-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="c142b-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="c142b-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="c142b-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c142b-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="c142b-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="c142b-131">Module 문</span><span class="sxs-lookup"><span data-stu-id="c142b-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="c142b-132">Operator 문</span><span class="sxs-lookup"><span data-stu-id="c142b-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="c142b-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="c142b-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c142b-134">Structure 문</span><span class="sxs-lookup"><span data-stu-id="c142b-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="c142b-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="c142b-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c142b-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="c142b-136">See also</span></span>

- [<span data-ttu-id="c142b-137">Protected</span><span class="sxs-lookup"><span data-stu-id="c142b-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="c142b-138">Friend</span><span class="sxs-lookup"><span data-stu-id="c142b-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="c142b-139">Private</span><span class="sxs-lookup"><span data-stu-id="c142b-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="c142b-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="c142b-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="c142b-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="c142b-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="c142b-142">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="c142b-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="c142b-143">절차</span><span class="sxs-lookup"><span data-stu-id="c142b-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="c142b-144">구조체</span><span class="sxs-lookup"><span data-stu-id="c142b-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c142b-145">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="c142b-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
