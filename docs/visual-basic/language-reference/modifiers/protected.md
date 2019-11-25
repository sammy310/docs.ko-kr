---
title: Protected
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
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351309"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="cf259-102">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf259-102">Protected (Visual Basic)</span></span>

<span data-ttu-id="cf259-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span><span class="sxs-lookup"><span data-stu-id="cf259-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf259-104">주의</span><span class="sxs-lookup"><span data-stu-id="cf259-104">Remarks</span></span>

<span data-ttu-id="cf259-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span><span class="sxs-lookup"><span data-stu-id="cf259-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="cf259-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span><span class="sxs-lookup"><span data-stu-id="cf259-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="cf259-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span><span class="sxs-lookup"><span data-stu-id="cf259-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="cf259-108">To limit access to an element in this manner, you can declare it with `Protected`.</span><span class="sxs-lookup"><span data-stu-id="cf259-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="cf259-109">The `Protected` access modifier can be combined with two other modifiers:</span><span class="sxs-lookup"><span data-stu-id="cf259-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="cf259-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span><span class="sxs-lookup"><span data-stu-id="cf259-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="cf259-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span><span class="sxs-lookup"><span data-stu-id="cf259-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="cf259-112">규칙</span><span class="sxs-lookup"><span data-stu-id="cf259-112">Rules</span></span>

<span data-ttu-id="cf259-113">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="cf259-113">**Declaration Context.**</span></span> <span data-ttu-id="cf259-114">You can use `Protected` only at the class level.</span><span class="sxs-lookup"><span data-stu-id="cf259-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="cf259-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span><span class="sxs-lookup"><span data-stu-id="cf259-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="cf259-116">동작</span><span class="sxs-lookup"><span data-stu-id="cf259-116">Behavior</span></span>

- <span data-ttu-id="cf259-117">**Access Level.**</span><span class="sxs-lookup"><span data-stu-id="cf259-117">**Access Level.**</span></span> <span data-ttu-id="cf259-118">All code in a class can access its elements.</span><span class="sxs-lookup"><span data-stu-id="cf259-118">All code in a class can access its elements.</span></span> <span data-ttu-id="cf259-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span><span class="sxs-lookup"><span data-stu-id="cf259-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="cf259-120">This is true for all generations of derivation.</span><span class="sxs-lookup"><span data-stu-id="cf259-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="cf259-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span><span class="sxs-lookup"><span data-stu-id="cf259-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="cf259-122">Protected access is not a superset or subset of friend access.</span><span class="sxs-lookup"><span data-stu-id="cf259-122">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="cf259-123">**Access Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="cf259-123">**Access Modifiers.**</span></span> <span data-ttu-id="cf259-124">The keywords that specify access level are called *access modifiers*.</span><span class="sxs-lookup"><span data-stu-id="cf259-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="cf259-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cf259-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="cf259-126">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf259-126">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="cf259-127">Class 문</span><span class="sxs-lookup"><span data-stu-id="cf259-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="cf259-128">Const 문</span><span class="sxs-lookup"><span data-stu-id="cf259-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="cf259-129">Declare 문</span><span class="sxs-lookup"><span data-stu-id="cf259-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="cf259-130">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="cf259-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="cf259-131">Dim 문</span><span class="sxs-lookup"><span data-stu-id="cf259-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="cf259-132">Enum 문</span><span class="sxs-lookup"><span data-stu-id="cf259-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="cf259-133">Event 문</span><span class="sxs-lookup"><span data-stu-id="cf259-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="cf259-134">Function 문</span><span class="sxs-lookup"><span data-stu-id="cf259-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="cf259-135">Interface 문</span><span class="sxs-lookup"><span data-stu-id="cf259-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="cf259-136">Property 문</span><span class="sxs-lookup"><span data-stu-id="cf259-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="cf259-137">Structure 문</span><span class="sxs-lookup"><span data-stu-id="cf259-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="cf259-138">Sub 문</span><span class="sxs-lookup"><span data-stu-id="cf259-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="cf259-139">참조</span><span class="sxs-lookup"><span data-stu-id="cf259-139">See also</span></span>

- [<span data-ttu-id="cf259-140">Public</span><span class="sxs-lookup"><span data-stu-id="cf259-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="cf259-141">Friend</span><span class="sxs-lookup"><span data-stu-id="cf259-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="cf259-142">전용</span><span class="sxs-lookup"><span data-stu-id="cf259-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="cf259-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="cf259-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="cf259-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="cf259-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="cf259-145">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf259-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="cf259-146">절차</span><span class="sxs-lookup"><span data-stu-id="cf259-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="cf259-147">구조체</span><span class="sxs-lookup"><span data-stu-id="cf259-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="cf259-148">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="cf259-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
