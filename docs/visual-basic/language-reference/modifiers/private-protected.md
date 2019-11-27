---
title: 비공개 보호
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351338"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="4e037-102">개인 보호 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e037-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="4e037-103">`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="4e037-104">`Private Protected` 멤버는 포함 하는 클래스의 모든 멤버 뿐 아니라 포함 하는 클래스에서 파생 된 형식 뿐만 아니라 포함 하는 어셈블리에 있는 경우에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="4e037-105">`Private Protected`는 클래스의 멤버에만 지정할 수 있습니다. 구조체는 상속 될 수 없으므로 구조체의 멤버에 `Private Protected`을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="4e037-106">`Private Protected` 액세스 한정자는 Visual Basic 15.5 이상에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="4e037-107">이를 사용 하려면 Visual Basic 프로젝트 (\*.vbproj) 파일에 다음 요소를 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="4e037-108">Visual Basic 15.5 이상이 시스템에 설치 되어 있으면 최신 버전의 Visual Basic 컴파일러에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="4e037-109">자세한 내용은 [Visual Basic 언어 버전 설정](../../language-reference/configure-language-version.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e037-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4e037-110">Visual Studio에서는 `private protected`에 대 한 F1 도움말을 선택 하 여 [개인](private.md) 또는 [보호 된](protected.md)에 대 한 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="4e037-111">IDE는 복합 단어가 아니라 커서에서 단일 토큰을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="4e037-112">규칙</span><span class="sxs-lookup"><span data-stu-id="4e037-112">Rules</span></span>

- <span data-ttu-id="4e037-113">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="4e037-113">**Declaration Context.**</span></span> <span data-ttu-id="4e037-114">클래스 수준 에서만 `Private Protected`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="4e037-115">즉, `Protected` 요소에 대 한 선언 컨텍스트는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="4e037-116">동작</span><span class="sxs-lookup"><span data-stu-id="4e037-116">Behavior</span></span>

- <span data-ttu-id="4e037-117">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="4e037-117">**Access Level.**</span></span> <span data-ttu-id="4e037-118">클래스의 모든 코드는 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-118">All code in a class can access its elements.</span></span> <span data-ttu-id="4e037-119">기본 클래스에서 파생 되 고 동일한 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스의 모든 `Private Protected` 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="4e037-120">그러나 기본 클래스에서 파생 되 고 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스 `Private Protected` 요소에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="4e037-121">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="4e037-121">**Access Modifiers.**</span></span> <span data-ttu-id="4e037-122">액세스 수준을 지정 하는 키워드를 *액세스 한정자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="4e037-123">액세스 한정자의 비교는 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e037-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="4e037-124">`Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e037-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="4e037-125">중첩 된 클래스의 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4e037-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="4e037-126">Const 문</span><span class="sxs-lookup"><span data-stu-id="4e037-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="4e037-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="4e037-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="4e037-128">클래스에 중첩 된 대리자의 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4e037-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="4e037-129">Dim 문</span><span class="sxs-lookup"><span data-stu-id="4e037-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="4e037-130">클래스에 중첩 된 열거형의 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4e037-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="4e037-131">Event 문</span><span class="sxs-lookup"><span data-stu-id="4e037-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="4e037-132">Function 문</span><span class="sxs-lookup"><span data-stu-id="4e037-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="4e037-133">클래스에 중첩 된 인터페이스의 [인터페이스 문](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4e037-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="4e037-134">Property 문</span><span class="sxs-lookup"><span data-stu-id="4e037-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="4e037-135">클래스에 중첩 된 구조체의 [구조체 문](../../../visual-basic/language-reference/statements/structure-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4e037-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="4e037-136">Sub 문</span><span class="sxs-lookup"><span data-stu-id="4e037-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="4e037-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e037-137">See also</span></span>

- [<span data-ttu-id="4e037-138">Public</span><span class="sxs-lookup"><span data-stu-id="4e037-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="4e037-139">Protected</span><span class="sxs-lookup"><span data-stu-id="4e037-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="4e037-140">Friend</span><span class="sxs-lookup"><span data-stu-id="4e037-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="4e037-141">Private</span><span class="sxs-lookup"><span data-stu-id="4e037-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="4e037-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="4e037-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="4e037-143">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4e037-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="4e037-144">절차</span><span class="sxs-lookup"><span data-stu-id="4e037-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="4e037-145">구조체</span><span class="sxs-lookup"><span data-stu-id="4e037-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="4e037-146">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="4e037-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
