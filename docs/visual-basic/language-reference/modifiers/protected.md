---
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
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351309"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="47084-102">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47084-102">Protected (Visual Basic)</span></span>

<span data-ttu-id="47084-103">하나 이상의 선언 된 프로그래밍 요소가 자체 클래스 또는 파생 된 클래스 내 에서만 액세스할 수 있도록 지정 하는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="47084-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="47084-104">주의</span><span class="sxs-lookup"><span data-stu-id="47084-104">Remarks</span></span>

<span data-ttu-id="47084-105">클래스에 선언 된 프로그래밍 요소가 중요 한 데이터 또는 제한 된 코드를 포함 하 고 있고 요소에 대 한 액세스를 제한 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="47084-106">그러나 클래스가 상속 가능 하 고 파생 클래스의 계층 구조가 필요한 경우 이러한 파생 클래스에서 데이터 또는 코드에 액세스 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="47084-107">이 경우 기본 클래스와 모든 파생 클래스에서 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47084-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="47084-108">이러한 방식으로 요소에 대 한 액세스를 제한 하기 위해 `Protected`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="47084-109">`Protected` 액세스 한정자는 다음과 같은 두 가지 한정자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="47084-110">[Protected Friend](protected-friend.md) 한정자는 클래스, 파생 클래스 및 클래스가 정의 된 동일한 어셈블리에서 클래스 멤버를 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47084-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="47084-111">[Private Protected](private-protected.md) 한정자를 사용 하면 파생 형식에서 클래스 멤버에 액세스할 수 있지만 포함 하는 어셈블리 내 에서만 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="47084-112">규칙</span><span class="sxs-lookup"><span data-stu-id="47084-112">Rules</span></span>

<span data-ttu-id="47084-113">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="47084-113">**Declaration Context.**</span></span> <span data-ttu-id="47084-114">클래스 수준 에서만 `Protected`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="47084-115">즉, `Protected` 요소에 대 한 선언 컨텍스트는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="47084-116">동작</span><span class="sxs-lookup"><span data-stu-id="47084-116">Behavior</span></span>

- <span data-ttu-id="47084-117">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="47084-117">**Access Level.**</span></span> <span data-ttu-id="47084-118">클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-118">All code in a class can access its elements.</span></span> <span data-ttu-id="47084-119">기본 클래스에서 파생 되는 모든 클래스의 코드는 기본 클래스의 모든 `Protected` 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="47084-120">이는 모든 파생 세대에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47084-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="47084-121">즉, 클래스가 기본 클래스의 기본 클래스 `Protected` 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="47084-122">보호 된 액세스는 friend 액세스의 상위 집합이 나 하위 집합이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="47084-122">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="47084-123">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="47084-123">**Access Modifiers.**</span></span> <span data-ttu-id="47084-124">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="47084-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="47084-125">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="47084-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="47084-126">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47084-126">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="47084-127">Class 문</span><span class="sxs-lookup"><span data-stu-id="47084-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="47084-128">Const 문</span><span class="sxs-lookup"><span data-stu-id="47084-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="47084-129">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="47084-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="47084-130">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="47084-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="47084-131">Dim 문</span><span class="sxs-lookup"><span data-stu-id="47084-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="47084-132">Enum 문</span><span class="sxs-lookup"><span data-stu-id="47084-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="47084-133">Event 문</span><span class="sxs-lookup"><span data-stu-id="47084-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="47084-134">Function 문</span><span class="sxs-lookup"><span data-stu-id="47084-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="47084-135">Interface 문</span><span class="sxs-lookup"><span data-stu-id="47084-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="47084-136">Property 문</span><span class="sxs-lookup"><span data-stu-id="47084-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="47084-137">Structure 문</span><span class="sxs-lookup"><span data-stu-id="47084-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="47084-138">Sub 문</span><span class="sxs-lookup"><span data-stu-id="47084-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="47084-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47084-139">See also</span></span>

- [<span data-ttu-id="47084-140">Public</span><span class="sxs-lookup"><span data-stu-id="47084-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="47084-141">Friend</span><span class="sxs-lookup"><span data-stu-id="47084-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="47084-142">Private</span><span class="sxs-lookup"><span data-stu-id="47084-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="47084-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="47084-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="47084-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="47084-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="47084-145">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="47084-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="47084-146">절차</span><span class="sxs-lookup"><span data-stu-id="47084-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="47084-147">구조체</span><span class="sxs-lookup"><span data-stu-id="47084-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="47084-148">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="47084-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
