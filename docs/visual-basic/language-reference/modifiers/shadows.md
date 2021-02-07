---
description: '자세한 정보: 그림자 (Visual Basic)'
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 4a455a78c36e15db977936b81c22e7a5b03d107e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700847"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="022a3-103">Shadows(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="022a3-103">Shadows (Visual Basic)</span></span>

<span data-ttu-id="022a3-104">선언 된 프로그래밍 요소가 기본 클래스에서 동일 하 게 명명 된 요소 또는 오버 로드 된 요소 집합을 요소가 하 고 숨기도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-104">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="022a3-105">설명</span><span class="sxs-lookup"><span data-stu-id="022a3-105">Remarks</span></span>

<span data-ttu-id="022a3-106">숨김 ( *이름으로 숨기기* 라고도 함)의 주요 용도는 클래스 멤버의 정의를 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-106">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="022a3-107">기본 클래스는 이미 정의한 것과 동일한 이름으로 요소를 만드는 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="022a3-108">이 경우 `Shadows` 한정자는 클래스를 통해 참조가 새 기본 클래스 요소가 아닌 사용자가 정의한 멤버로 확인 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="022a3-109">숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-109">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="022a3-110">자세한 내용은 [Visual Basic에서 숨기기](../../programming-guide/language-features/declared-elements/shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="022a3-110">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="022a3-111">규칙</span><span class="sxs-lookup"><span data-stu-id="022a3-111">Rules</span></span>

- <span data-ttu-id="022a3-112">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="022a3-112">**Declaration Context.**</span></span> <span data-ttu-id="022a3-113">는 `Shadows` 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-113">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="022a3-114">즉, 요소에 대 한 선언 컨텍스트는 `Shadows` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-114">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="022a3-115">단일 선언문에서 하나의 섀도잉 요소만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-115">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="022a3-116">**결합된 한정자.**</span><span class="sxs-lookup"><span data-stu-id="022a3-116">**Combined Modifiers.**</span></span> <span data-ttu-id="022a3-117">`Shadows` `Overloads` `Overrides` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Static` .</span><span class="sxs-lookup"><span data-stu-id="022a3-117">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="022a3-118">**요소 형식.**</span><span class="sxs-lookup"><span data-stu-id="022a3-118">**Element Types.**</span></span> <span data-ttu-id="022a3-119">모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-119">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="022a3-120">다른 속성이 나 프로시저를 사용 하 여 속성 또는 프로시저를 숨기는 경우 매개 변수와 반환 형식이 기본 클래스 속성 또는 프로시저의 매개 변수와 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-120">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="022a3-121">**하.**</span><span class="sxs-lookup"><span data-stu-id="022a3-121">**Accessing.**</span></span> <span data-ttu-id="022a3-122">기본 클래스의 숨겨진 요소는 일반적으로 해당 요소를 숨기는 파생 클래스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-122">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="022a3-123">그러나 다음 고려 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-123">However, the following considerations apply.</span></span>

  - <span data-ttu-id="022a3-124">해당 요소를 참조 하는 코드에서 숨기는 요소에 액세스할 수 없는 경우 참조는 숨겨진 요소로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-124">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="022a3-125">예를 들어 `Private` 요소가 기본 클래스 요소를 숨기는 경우 요소에 액세스할 수 있는 권한이 없는 코드는 `Private` 대신 기본 클래스 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-125">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="022a3-126">요소를 숨기는 경우에도 기본 클래스의 형식으로 선언 된 개체를 통해 숨겨진 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-126">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="022a3-127">를 통해 액세스할 수도 있습니다 `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="022a3-127">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="022a3-128">`Shadows` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="022a3-128">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="022a3-129">Class 문</span><span class="sxs-lookup"><span data-stu-id="022a3-129">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="022a3-130">Const 문</span><span class="sxs-lookup"><span data-stu-id="022a3-130">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="022a3-131">Declare 문</span><span class="sxs-lookup"><span data-stu-id="022a3-131">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="022a3-132">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="022a3-132">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="022a3-133">Dim 문</span><span class="sxs-lookup"><span data-stu-id="022a3-133">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="022a3-134">Enum 문</span><span class="sxs-lookup"><span data-stu-id="022a3-134">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="022a3-135">Event 문</span><span class="sxs-lookup"><span data-stu-id="022a3-135">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="022a3-136">Function 문</span><span class="sxs-lookup"><span data-stu-id="022a3-136">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="022a3-137">Interface 문</span><span class="sxs-lookup"><span data-stu-id="022a3-137">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="022a3-138">Property Statement</span><span class="sxs-lookup"><span data-stu-id="022a3-138">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="022a3-139">Structure 문</span><span class="sxs-lookup"><span data-stu-id="022a3-139">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="022a3-140">Sub 문</span><span class="sxs-lookup"><span data-stu-id="022a3-140">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="022a3-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="022a3-141">See also</span></span>

- [<span data-ttu-id="022a3-142">공유</span><span class="sxs-lookup"><span data-stu-id="022a3-142">Shared</span></span>](shared.md)
- [<span data-ttu-id="022a3-143">정적</span><span class="sxs-lookup"><span data-stu-id="022a3-143">Static</span></span>](static.md)
- [<span data-ttu-id="022a3-144">개인</span><span class="sxs-lookup"><span data-stu-id="022a3-144">Private</span></span>](private.md)
- [<span data-ttu-id="022a3-145">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="022a3-145">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="022a3-146">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="022a3-146">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="022a3-147">New</span><span class="sxs-lookup"><span data-stu-id="022a3-147">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="022a3-148">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="022a3-148">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="022a3-149">오버로드</span><span class="sxs-lookup"><span data-stu-id="022a3-149">Overloads</span></span>](overloads.md)
- [<span data-ttu-id="022a3-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="022a3-150">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="022a3-151">재정의</span><span class="sxs-lookup"><span data-stu-id="022a3-151">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="022a3-152">Visual Basic에서 숨김</span><span class="sxs-lookup"><span data-stu-id="022a3-152">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
