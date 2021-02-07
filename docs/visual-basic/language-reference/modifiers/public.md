---
description: '자세한 정보: 공용 (Visual Basic)'
title: 공용
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 1083ca877cf99917291523fe10f6561784ff06a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700925"
---
# <a name="public-visual-basic"></a><span data-ttu-id="dfa3f-103">Public(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfa3f-103">Public (Visual Basic)</span></span>

<span data-ttu-id="dfa3f-104">하나 이상의 선언 된 프로그래밍 요소에 액세스 제한이 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-104">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfa3f-105">설명</span><span class="sxs-lookup"><span data-stu-id="dfa3f-105">Remarks</span></span>  

 <span data-ttu-id="dfa3f-106">클래스 라이브러리와 같은 구성 요소 또는 구성 요소 집합을 게시 하는 경우 일반적으로 어셈블리와 상호 작용 하는 코드에서 프로그래밍 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-106">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="dfa3f-107">요소에 대 한 무제한 액세스를 설정 하려면를 사용 하 여 선언 하면 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-107">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="dfa3f-108">공용 액세스는 프로그래밍 요소에 대 한 액세스를 제한 하지 않아도 되는 일반적인 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-108">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="dfa3f-109">선언 하지 않으면 인터페이스, 모듈, 클래스 또는 구조체 내에서 선언 된 요소의 액세스 수준이 기본적으로로 설정 `Public` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-109">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="dfa3f-110">규칙</span><span class="sxs-lookup"><span data-stu-id="dfa3f-110">Rules</span></span>  
  
- <span data-ttu-id="dfa3f-111">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="dfa3f-111">**Declaration Context.**</span></span> <span data-ttu-id="dfa3f-112">는 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-112">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="dfa3f-113">즉, 요소에 대 한 선언 컨텍스트는 `Public` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 하며 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-113">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="dfa3f-114">동작</span><span class="sxs-lookup"><span data-stu-id="dfa3f-114">Behavior</span></span>  
  
- <span data-ttu-id="dfa3f-115">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa3f-115">**Access Level.**</span></span> <span data-ttu-id="dfa3f-116">모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 요소에 액세스할 수 있습니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="dfa3f-116">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="dfa3f-117">**기본 액세스.**</span><span class="sxs-lookup"><span data-stu-id="dfa3f-117">**Default Access.**</span></span> <span data-ttu-id="dfa3f-118">프로시저 내의 지역 변수는 기본적으로 공용 액세스로 설정 되며 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-118">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="dfa3f-119">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="dfa3f-119">**Access Modifiers.**</span></span> <span data-ttu-id="dfa3f-120">액세스 수준을 지정 하는 키워드를 *액세스 한정자* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-120">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="dfa3f-121">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-121">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="dfa3f-122">`Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa3f-122">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="dfa3f-123">Class 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-123">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="dfa3f-124">Const 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-124">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="dfa3f-125">Declare 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-125">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="dfa3f-126">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-126">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="dfa3f-127">Dim 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-127">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="dfa3f-128">Enum 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-128">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="dfa3f-129">Event 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-129">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="dfa3f-130">Function 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-130">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="dfa3f-131">Interface 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-131">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="dfa3f-132">Module 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-132">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="dfa3f-133">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="dfa3f-133">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="dfa3f-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="dfa3f-134">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="dfa3f-135">Structure 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-135">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="dfa3f-136">Sub 문</span><span class="sxs-lookup"><span data-stu-id="dfa3f-136">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="dfa3f-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfa3f-137">See also</span></span>

- [<span data-ttu-id="dfa3f-138">보호됨</span><span class="sxs-lookup"><span data-stu-id="dfa3f-138">Protected</span></span>](protected.md)
- [<span data-ttu-id="dfa3f-139">Friend</span><span class="sxs-lookup"><span data-stu-id="dfa3f-139">Friend</span></span>](friend.md)
- [<span data-ttu-id="dfa3f-140">개인</span><span class="sxs-lookup"><span data-stu-id="dfa3f-140">Private</span></span>](private.md)
- [<span data-ttu-id="dfa3f-141">비공개 보호</span><span class="sxs-lookup"><span data-stu-id="dfa3f-141">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="dfa3f-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="dfa3f-142">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="dfa3f-143">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="dfa3f-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="dfa3f-144">절차</span><span class="sxs-lookup"><span data-stu-id="dfa3f-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="dfa3f-145">구조체</span><span class="sxs-lookup"><span data-stu-id="dfa3f-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dfa3f-146">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="dfa3f-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
