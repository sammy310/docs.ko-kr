---
title: 프라이빗
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 5600744aeca79a54f51a1f9ecd0ef00fed4b00fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351326"
---
# <a name="private-visual-basic"></a><span data-ttu-id="85f37-102">Private(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85f37-102">Private (Visual Basic)</span></span>
<span data-ttu-id="85f37-103">하나 이상의 선언 된 프로그래밍 요소를 포함 된 형식 내에서 포함 하 여 해당 선언 컨텍스트 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f37-104">설명</span><span class="sxs-lookup"><span data-stu-id="85f37-104">Remarks</span></span>  
 <span data-ttu-id="85f37-105">프로그래밍 요소가 독점적인 기능을 나타내거나 기밀 데이터를 포함 하는 경우 일반적으로 해당 요소에 대 한 액세스를 최대한 엄격 하 게 제한 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="85f37-106">모듈, 클래스 또는 구조체를 정의 하는 구조체를 사용 하 여 액세스할 수 있도록 허용 하 여 최대 제한을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="85f37-107">이러한 방식으로 요소에 대 한 액세스를 제한 하기 위해 `Private`로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="85f37-108">[Private Protected](private-protected.md) 액세스 한정자를 사용 하 여 해당 클래스 내에서, 그리고 포함 하는 어셈블리에 있는 파생 클래스에서 멤버에 액세스할 수 있게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="85f37-109">규칙</span><span class="sxs-lookup"><span data-stu-id="85f37-109">Rules</span></span>  

- <span data-ttu-id="85f37-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="85f37-110">**Declaration Context.**</span></span> <span data-ttu-id="85f37-111">`Private`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="85f37-112">즉, `Private` 요소에 대 한 선언 컨텍스트는 모듈, 클래스 또는 구조체 여야 하며 소스 파일, 네임 스페이스, 인터페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="85f37-113">동작</span><span class="sxs-lookup"><span data-stu-id="85f37-113">Behavior</span></span>  
  
- <span data-ttu-id="85f37-114">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="85f37-114">**Access Level.**</span></span> <span data-ttu-id="85f37-115">선언 컨텍스트 내의 모든 코드는 해당 `Private` 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="85f37-116">여기에는 중첩 된 클래스 또는 열거형의 할당 식과 같은 포함 된 형식 내의 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="85f37-117">선언 컨텍스트 외부의 코드는 `Private` 요소에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="85f37-118">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="85f37-118">**Access Modifiers.**</span></span> <span data-ttu-id="85f37-119">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="85f37-120">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85f37-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="85f37-121">`Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="85f37-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="85f37-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="85f37-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="85f37-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="85f37-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="85f37-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="85f37-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="85f37-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="85f37-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="85f37-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="85f37-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="85f37-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="85f37-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="85f37-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="85f37-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="85f37-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="85f37-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="85f37-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="85f37-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="85f37-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="85f37-132">Structure 문</span><span class="sxs-lookup"><span data-stu-id="85f37-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="85f37-133">Sub 문</span><span class="sxs-lookup"><span data-stu-id="85f37-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="85f37-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="85f37-134">See also</span></span>

- [<span data-ttu-id="85f37-135">Public</span><span class="sxs-lookup"><span data-stu-id="85f37-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="85f37-136">Protected</span><span class="sxs-lookup"><span data-stu-id="85f37-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="85f37-137">Friend</span><span class="sxs-lookup"><span data-stu-id="85f37-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="85f37-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="85f37-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="85f37-139">Visual Basic의 [보호 된 Friend](./protected-friend.md)[액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="85f37-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="85f37-140">절차</span><span class="sxs-lookup"><span data-stu-id="85f37-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="85f37-141">구조체</span><span class="sxs-lookup"><span data-stu-id="85f37-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="85f37-142">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="85f37-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
