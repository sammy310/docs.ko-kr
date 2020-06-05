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
ms.openlocfilehash: d66ed68004f8b6ef21ae703f02b317589814764b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398222"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="8cda8-102">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cda8-102">Protected (Visual Basic)</span></span>

<span data-ttu-id="8cda8-103">하나 이상의 선언 된 프로그래밍 요소가 자체 클래스 또는 파생 된 클래스 내 에서만 액세스할 수 있도록 지정 하는 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="8cda8-104">설명</span><span class="sxs-lookup"><span data-stu-id="8cda8-104">Remarks</span></span>

<span data-ttu-id="8cda8-105">클래스에 선언 된 프로그래밍 요소가 중요 한 데이터 또는 제한 된 코드를 포함 하 고 있고 요소에 대 한 액세스를 제한 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="8cda8-106">그러나 클래스가 상속 가능 하 고 파생 클래스의 계층 구조가 필요한 경우 이러한 파생 클래스에서 데이터 또는 코드에 액세스 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="8cda8-107">이 경우 기본 클래스와 모든 파생 클래스에서 요소에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="8cda8-108">이러한 방식으로 요소에 대 한 액세스를 제한 하려면로 선언할 수 있습니다 `Protected` .</span><span class="sxs-lookup"><span data-stu-id="8cda8-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="8cda8-109">`Protected`액세스 한정자는 다음과 같은 두 가지 한정자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="8cda8-110">[Protected Friend](protected-friend.md) 한정자는 클래스, 파생 클래스 및 클래스가 정의 된 동일한 어셈블리에서 클래스 멤버를 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="8cda8-111">[Private Protected](private-protected.md) 한정자를 사용 하면 파생 형식에서 클래스 멤버에 액세스할 수 있지만 포함 하는 어셈블리 내 에서만 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="8cda8-112">규칙</span><span class="sxs-lookup"><span data-stu-id="8cda8-112">Rules</span></span>

<span data-ttu-id="8cda8-113">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="8cda8-113">**Declaration Context.**</span></span> <span data-ttu-id="8cda8-114">`Protected`는 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="8cda8-115">즉, 요소에 대 한 선언 컨텍스트는 `Protected` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="8cda8-116">동작</span><span class="sxs-lookup"><span data-stu-id="8cda8-116">Behavior</span></span>

- <span data-ttu-id="8cda8-117">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="8cda8-117">**Access Level.**</span></span> <span data-ttu-id="8cda8-118">클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-118">All code in a class can access its elements.</span></span> <span data-ttu-id="8cda8-119">기본 클래스에서 파생 되는 모든 클래스의 코드는 기본 클래스의 모든 요소에 액세스할 수 있습니다 `Protected` .</span><span class="sxs-lookup"><span data-stu-id="8cda8-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="8cda8-120">이는 모든 파생 세대에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="8cda8-121">즉 `Protected` , 클래스가 기본 클래스의 기본 클래스 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="8cda8-122">보호 된 액세스는 friend 액세스의 상위 집합이 나 하위 집합이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-122">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="8cda8-123">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="8cda8-123">**Access Modifiers.**</span></span> <span data-ttu-id="8cda8-124">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="8cda8-125">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cda8-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="8cda8-126">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda8-126">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="8cda8-127">Class 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-127">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="8cda8-128">Const 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-128">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="8cda8-129">Declare 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-129">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="8cda8-130">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-130">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="8cda8-131">Dim 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-131">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="8cda8-132">Enum 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-132">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="8cda8-133">Event 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-133">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="8cda8-134">Function 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-134">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="8cda8-135">Interface 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-135">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="8cda8-136">Property Statement</span><span class="sxs-lookup"><span data-stu-id="8cda8-136">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="8cda8-137">Structure 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-137">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="8cda8-138">Sub 문</span><span class="sxs-lookup"><span data-stu-id="8cda8-138">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="8cda8-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cda8-139">See also</span></span>

- [<span data-ttu-id="8cda8-140">공용</span><span class="sxs-lookup"><span data-stu-id="8cda8-140">Public</span></span>](public.md)
- [<span data-ttu-id="8cda8-141">Friend</span><span class="sxs-lookup"><span data-stu-id="8cda8-141">Friend</span></span>](friend.md)
- [<span data-ttu-id="8cda8-142">프라이빗</span><span class="sxs-lookup"><span data-stu-id="8cda8-142">Private</span></span>](private.md)
- [<span data-ttu-id="8cda8-143">개인 보호</span><span class="sxs-lookup"><span data-stu-id="8cda8-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="8cda8-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8cda8-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="8cda8-145">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8cda8-145">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="8cda8-146">절차</span><span class="sxs-lookup"><span data-stu-id="8cda8-146">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="8cda8-147">구조체</span><span class="sxs-lookup"><span data-stu-id="8cda8-147">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8cda8-148">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="8cda8-148">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
