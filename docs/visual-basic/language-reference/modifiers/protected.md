---
description: '자세히 알아보기: Protected (Visual Basic)'
title: 보호됨
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 74a695e7c8ff06543a7118c935365e31af258171
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700938"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="4f6fd-103">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f6fd-103">Protected (Visual Basic)</span></span>

<span data-ttu-id="4f6fd-104">하나 이상의 선언 된 프로그래밍 요소가 자체 클래스 또는 파생 된 클래스 내 에서만 액세스할 수 있도록 지정 하는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-104">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f6fd-105">설명</span><span class="sxs-lookup"><span data-stu-id="4f6fd-105">Remarks</span></span>

<span data-ttu-id="4f6fd-106">클래스에 선언 된 프로그래밍 요소가 중요 한 데이터 또는 제한 된 코드를 포함 하 고 있고 요소에 대 한 액세스를 제한 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-106">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="4f6fd-107">그러나 클래스가 상속 가능 하 고 파생 클래스의 계층 구조가 필요한 경우 이러한 파생 클래스에서 데이터 또는 코드에 액세스 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-107">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="4f6fd-108">이 경우 기본 클래스와 모든 파생 클래스에서 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-108">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="4f6fd-109">이러한 방식으로 요소에 대 한 액세스를 제한 하려면로 선언할 수 있습니다 `Protected` .</span><span class="sxs-lookup"><span data-stu-id="4f6fd-109">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="4f6fd-110">`Protected`액세스 한정자는 다음과 같은 두 가지 한정자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-110">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="4f6fd-111">[Protected Friend](protected-friend.md) 한정자는 클래스, 파생 클래스 및 클래스가 정의 된 동일한 어셈블리에서 클래스 멤버를 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-111">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="4f6fd-112">[Private Protected](private-protected.md) 한정자를 사용 하면 파생 형식에서 클래스 멤버에 액세스할 수 있지만 포함 하는 어셈블리 내 에서만 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-112">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="4f6fd-113">규칙</span><span class="sxs-lookup"><span data-stu-id="4f6fd-113">Rules</span></span>

<span data-ttu-id="4f6fd-114">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="4f6fd-114">**Declaration Context.**</span></span> <span data-ttu-id="4f6fd-115">`Protected`는 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-115">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="4f6fd-116">즉, 요소에 대 한 선언 컨텍스트는 `Protected` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-116">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="4f6fd-117">동작</span><span class="sxs-lookup"><span data-stu-id="4f6fd-117">Behavior</span></span>

- <span data-ttu-id="4f6fd-118">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6fd-118">**Access Level.**</span></span> <span data-ttu-id="4f6fd-119">클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-119">All code in a class can access its elements.</span></span> <span data-ttu-id="4f6fd-120">기본 클래스에서 파생 되는 모든 클래스의 코드는 기본 클래스의 모든 요소에 액세스할 수 있습니다 `Protected` .</span><span class="sxs-lookup"><span data-stu-id="4f6fd-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="4f6fd-121">이는 모든 파생 세대에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="4f6fd-122">즉 `Protected` , 클래스가 기본 클래스의 기본 클래스 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="4f6fd-123">보호 된 액세스는 friend 액세스의 상위 집합이 나 하위 집합이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-123">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="4f6fd-124">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="4f6fd-124">**Access Modifiers.**</span></span> <span data-ttu-id="4f6fd-125">액세스 수준을 지정 하는 키워드를 *액세스 한정자* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="4f6fd-126">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="4f6fd-127">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f6fd-127">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="4f6fd-128">Class 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-128">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="4f6fd-129">Const 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-129">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="4f6fd-130">Declare 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-130">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="4f6fd-131">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-131">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="4f6fd-132">Dim 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-132">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="4f6fd-133">Enum 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-133">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="4f6fd-134">Event 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-134">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="4f6fd-135">Function 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-135">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="4f6fd-136">Interface 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-136">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="4f6fd-137">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4f6fd-137">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="4f6fd-138">Structure 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-138">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="4f6fd-139">Sub 문</span><span class="sxs-lookup"><span data-stu-id="4f6fd-139">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="4f6fd-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f6fd-140">See also</span></span>

- [<span data-ttu-id="4f6fd-141">공용</span><span class="sxs-lookup"><span data-stu-id="4f6fd-141">Public</span></span>](public.md)
- [<span data-ttu-id="4f6fd-142">Friend</span><span class="sxs-lookup"><span data-stu-id="4f6fd-142">Friend</span></span>](friend.md)
- [<span data-ttu-id="4f6fd-143">개인</span><span class="sxs-lookup"><span data-stu-id="4f6fd-143">Private</span></span>](private.md)
- [<span data-ttu-id="4f6fd-144">비공개 보호</span><span class="sxs-lookup"><span data-stu-id="4f6fd-144">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="4f6fd-145">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="4f6fd-145">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="4f6fd-146">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4f6fd-146">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="4f6fd-147">절차</span><span class="sxs-lookup"><span data-stu-id="4f6fd-147">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4f6fd-148">구조체</span><span class="sxs-lookup"><span data-stu-id="4f6fd-148">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4f6fd-149">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="4f6fd-149">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
