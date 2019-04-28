---
title: Private Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920499"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="a9935-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9935-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="a9935-103">`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a9935-104">`Private Protected` 멤버를 포함 하는 어셈블리가 있는 경우만 포함 하는 클래스에서 파생 된 형식 뿐만 아니라 모든 멤버에 포함 하는 클래스를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="a9935-105">지정할 수 있습니다 `Private Protected` 클래스의 멤버에만 적용할 수 없습니다 `Private Protected` 구조체의 멤버에 구조체를 상속할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="a9935-106">`Private Protected` 액세스 한정자는 Visual Basic 15.5 이상에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="a9935-107">를 사용 하려면 Visual Basic 프로젝트에 다음 요소를 추가할 수 있습니다 (\*.vbproj) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="a9935-108">Visual Basic 15.5 하기만 이상 시스템에 설치 되어, 최신 버전의 Visual Basic 컴파일러를 지 원하는 모든 언어 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a9935-109">자세한 내용은 참조 [Visual Basic 언어 버전을 설정](../../language-reference/configure-language-version.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a9935-110">Visual Studio에서에서 F1 도움말을 선택 하 `private protected` 에 대 한 도움말을 제공 [사설](private.md) 하거나 [보호](protected.md).</span><span class="sxs-lookup"><span data-stu-id="a9935-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="a9935-111">IDE 복합 단어를 사용 하지 않고 커서 아래에 있는 단일 토큰을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="a9935-112">규칙</span><span class="sxs-lookup"><span data-stu-id="a9935-112">Rules</span></span>

- <span data-ttu-id="a9935-113">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="a9935-113">**Declaration Context.**</span></span> <span data-ttu-id="a9935-114">사용할 수 있습니다 `Private Protected` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="a9935-115">즉, 선언 컨텍스트는 `Protected` 요소 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="a9935-116">동작</span><span class="sxs-lookup"><span data-stu-id="a9935-116">Behavior</span></span>

- <span data-ttu-id="a9935-117">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="a9935-117">**Access Level.**</span></span> <span data-ttu-id="a9935-118">클래스의 모든 코드가 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-118">All code in a class can access its elements.</span></span> <span data-ttu-id="a9935-119">모든 기본 클래스에서 파생 되는 동일한 어셈블리에 포함 된 모든 클래스의 코드에 액세스할 수는 `Private Protected` 요소의 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="a9935-120">그러나 기본 클래스에서 파생 되는 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스에 액세스할 수 없습니다 `Private Protected` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="a9935-121">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a9935-121">**Access Modifiers.**</span></span> <span data-ttu-id="a9935-122">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="a9935-123">액세스 한정자와 비교 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="a9935-124">`Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9935-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="a9935-125">[Class 문](../../../visual-basic/language-reference/statements/class-statement.md) 중첩된 된 클래스의</span><span class="sxs-lookup"><span data-stu-id="a9935-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="a9935-126">Const 문</span><span class="sxs-lookup"><span data-stu-id="a9935-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="a9935-127">Declare 문</span><span class="sxs-lookup"><span data-stu-id="a9935-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="a9935-128">[Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 클래스에서 중첩 된 대리자</span><span class="sxs-lookup"><span data-stu-id="a9935-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="a9935-129">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a9935-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="a9935-130">[Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md) 클래스에서 중첩 된 열거형의</span><span class="sxs-lookup"><span data-stu-id="a9935-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="a9935-131">Event 문</span><span class="sxs-lookup"><span data-stu-id="a9935-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="a9935-132">Function 문</span><span class="sxs-lookup"><span data-stu-id="a9935-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="a9935-133">[Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md) 인터페이스의 클래스에서 중첩</span><span class="sxs-lookup"><span data-stu-id="a9935-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="a9935-134">Property 문</span><span class="sxs-lookup"><span data-stu-id="a9935-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="a9935-135">[문을 구조체](../../../visual-basic/language-reference/statements/structure-statement.md) 클래스에서 중첩 된 구조의</span><span class="sxs-lookup"><span data-stu-id="a9935-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="a9935-136">Sub 문</span><span class="sxs-lookup"><span data-stu-id="a9935-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="a9935-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9935-137">See also</span></span>

- [<span data-ttu-id="a9935-138">공용</span><span class="sxs-lookup"><span data-stu-id="a9935-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a9935-139">보호됨</span><span class="sxs-lookup"><span data-stu-id="a9935-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a9935-140">Friend</span><span class="sxs-lookup"><span data-stu-id="a9935-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="a9935-141">전용</span><span class="sxs-lookup"><span data-stu-id="a9935-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a9935-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a9935-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="a9935-143">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="a9935-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a9935-144">절차</span><span class="sxs-lookup"><span data-stu-id="a9935-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a9935-145">구조체</span><span class="sxs-lookup"><span data-stu-id="a9935-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a9935-146">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="a9935-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
