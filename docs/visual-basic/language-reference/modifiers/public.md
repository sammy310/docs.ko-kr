---
title: 공용
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415351"
---
# <a name="public-visual-basic"></a><span data-ttu-id="d4df4-102">Public(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4df4-102">Public (Visual Basic)</span></span>
<span data-ttu-id="d4df4-103">하나 이상의 선언 된 프로그래밍 요소에 액세스 제한이 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4df4-104">설명</span><span class="sxs-lookup"><span data-stu-id="d4df4-104">Remarks</span></span>  
 <span data-ttu-id="d4df4-105">클래스 라이브러리와 같은 구성 요소 또는 구성 요소 집합을 게시 하는 경우 일반적으로 어셈블리와 상호 작용 하는 코드에서 프로그래밍 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="d4df4-106">요소에 대 한 무제한 액세스를 설정 하려면를 사용 하 여 선언 하면 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="d4df4-107">공용 액세스는 프로그래밍 요소에 대 한 액세스를 제한 하지 않아도 되는 일반적인 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="d4df4-108">선언 하지 않으면 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언 된 요소의 액세스 수준이 기본적으로로 설정 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d4df4-109">규칙</span><span class="sxs-lookup"><span data-stu-id="d4df4-109">Rules</span></span>  
  
- <span data-ttu-id="d4df4-110">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="d4df4-110">**Declaration Context.**</span></span> <span data-ttu-id="d4df4-111">는 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="d4df4-112">즉, 요소에 대 한 선언 컨텍스트는 `Public` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 하며 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d4df4-113">동작</span><span class="sxs-lookup"><span data-stu-id="d4df4-113">Behavior</span></span>  
  
- <span data-ttu-id="d4df4-114">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4df4-114">**Access Level.**</span></span> <span data-ttu-id="d4df4-115">모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 요소에 액세스할 수 있습니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="d4df4-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="d4df4-116">**기본 액세스.**</span><span class="sxs-lookup"><span data-stu-id="d4df4-116">**Default Access.**</span></span> <span data-ttu-id="d4df4-117">프로시저 내의 지역 변수는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="d4df4-118">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4df4-118">**Access Modifiers.**</span></span> <span data-ttu-id="d4df4-119">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="d4df4-120">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4df4-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="d4df4-121">`Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4df4-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d4df4-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="d4df4-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="d4df4-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="d4df4-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="d4df4-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="d4df4-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="d4df4-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="d4df4-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d4df4-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="d4df4-131">Module 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="d4df4-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d4df4-132">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="d4df4-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d4df4-133">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d4df4-134">Structure 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-134">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="d4df4-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="d4df4-135">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d4df4-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4df4-136">See also</span></span>

- [<span data-ttu-id="d4df4-137">보호</span><span class="sxs-lookup"><span data-stu-id="d4df4-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="d4df4-138">Friend</span><span class="sxs-lookup"><span data-stu-id="d4df4-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="d4df4-139">프라이빗</span><span class="sxs-lookup"><span data-stu-id="d4df4-139">Private</span></span>](private.md)
- [<span data-ttu-id="d4df4-140">개인 보호</span><span class="sxs-lookup"><span data-stu-id="d4df4-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="d4df4-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d4df4-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="d4df4-142">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="d4df4-142">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d4df4-143">절차</span><span class="sxs-lookup"><span data-stu-id="d4df4-143">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d4df4-144">구조체</span><span class="sxs-lookup"><span data-stu-id="d4df4-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d4df4-145">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="d4df4-145">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
