---
description: '자세한 정보: Friend (Visual Basic)'
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: ef2444555c05d6a4b24048316e282d269d4b7f1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774592"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="435d1-103">Friend(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="435d1-103">Friend (Visual Basic)</span></span>

<span data-ttu-id="435d1-104">선언 된 프로그래밍 요소를 해당 선언이 포함 된 어셈블리 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-104">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="435d1-105">설명</span><span class="sxs-lookup"><span data-stu-id="435d1-105">Remarks</span></span>  

 <span data-ttu-id="435d1-106">대부분의 경우 클래스 및 구조체와 같은 프로그래밍 요소를 선언 하는 구성 요소 뿐만 아니라 전체 어셈블리에서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-106">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="435d1-107">그러나 어셈블리 외부의 코드에서 액세스할 수 없도록 하는 것이 좋습니다 (예: 응용 프로그램이 소유 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="435d1-107">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="435d1-108">이러한 방식으로 요소에 대 한 액세스를 제한 하려는 경우 한정자를 사용 하 여 해당 요소를 선언할 수 있습니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="435d1-108">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="435d1-109">동일한 어셈블리로 컴파일되는 다른 클래스, 구조체 및 모듈의 코드 `Friend` 는 해당 어셈블리의 모든 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-109">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="435d1-110">`Friend` 액세스는 응용 프로그램의 프로그래밍 요소에 대 한 기본 설정 수준 이며 `Friend` 인터페이스, 모듈, 클래스 또는 구조체의 기본 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-110">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="435d1-111">`Friend`는 모듈, 인터페이스 또는 네임 스페이스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-111">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="435d1-112">따라서 요소의 선언 컨텍스트는 `Friend` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 여야 합니다 .이는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-112">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="435d1-113">[Protected Friend](protected-friend.md) 액세스 한정자를 사용 하 여 클래스, 파생 클래스 및 클래스가 정의 된 동일한 어셈블리에서 클래스 멤버에 액세스할 수 있게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-113">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="435d1-114">해당 클래스 내와 동일한 어셈블리의 파생 클래스에서 멤버에 대 한 액세스를 제한 하려면 [Private Protected](private-protected.md) 액세스 한정자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-114">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="435d1-115">`Friend`및 다른 액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="435d1-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="435d1-116">다른 어셈블리를 friend 어셈블리로 지정 하 여로 표시 된 모든 형식 및 멤버에 액세스할 수 있도록 지정할 수 있습니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="435d1-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="435d1-117">자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="435d1-117">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="435d1-118">예제</span><span class="sxs-lookup"><span data-stu-id="435d1-118">Example</span></span>  

 <span data-ttu-id="435d1-119">다음 클래스는 한정자를 사용 하 여 `Friend` 동일한 어셈블리 내의 다른 프로그래밍 요소가 특정 멤버에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="435d1-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="435d1-120">사용량</span><span class="sxs-lookup"><span data-stu-id="435d1-120">Usage</span></span>  

 <span data-ttu-id="435d1-121">한정자는 다음 컨텍스트에서 사용할 수 있습니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="435d1-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="435d1-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="435d1-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="435d1-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="435d1-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="435d1-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="435d1-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="435d1-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="435d1-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="435d1-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="435d1-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="435d1-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="435d1-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="435d1-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="435d1-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="435d1-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="435d1-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="435d1-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="435d1-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="435d1-131">Module 문</span><span class="sxs-lookup"><span data-stu-id="435d1-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="435d1-132">Property Statement</span><span class="sxs-lookup"><span data-stu-id="435d1-132">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="435d1-133">Structure 문</span><span class="sxs-lookup"><span data-stu-id="435d1-133">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="435d1-134">Sub 문</span><span class="sxs-lookup"><span data-stu-id="435d1-134">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="435d1-135">참조</span><span class="sxs-lookup"><span data-stu-id="435d1-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="435d1-136">공용</span><span class="sxs-lookup"><span data-stu-id="435d1-136">Public</span></span>](public.md)
- [<span data-ttu-id="435d1-137">보호됨</span><span class="sxs-lookup"><span data-stu-id="435d1-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="435d1-138">개인</span><span class="sxs-lookup"><span data-stu-id="435d1-138">Private</span></span>](private.md)
- [<span data-ttu-id="435d1-139">비공개 보호</span><span class="sxs-lookup"><span data-stu-id="435d1-139">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="435d1-140">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="435d1-140">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="435d1-141">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="435d1-141">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="435d1-142">절차</span><span class="sxs-lookup"><span data-stu-id="435d1-142">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="435d1-143">구조체</span><span class="sxs-lookup"><span data-stu-id="435d1-143">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="435d1-144">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="435d1-144">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
