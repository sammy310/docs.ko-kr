---
title: Sub 문
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346447"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="9a4e7-102">Sub 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="9a4e7-103">`Sub` 프로시저를 정의 하는 이름, 매개 변수 및 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a4e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a4e7-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="9a4e7-105">요소</span><span class="sxs-lookup"><span data-stu-id="9a4e7-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="9a4e7-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-106">Optional.</span></span> <span data-ttu-id="9a4e7-107">[특성 목록](attribute-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="9a4e7-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-108">Optional.</span></span> <span data-ttu-id="9a4e7-109">부분 메서드 정의를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="9a4e7-110">[부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="9a4e7-111">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-111">Optional.</span></span> <span data-ttu-id="9a4e7-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="9a4e7-113">Public</span><span class="sxs-lookup"><span data-stu-id="9a4e7-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="9a4e7-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9a4e7-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="9a4e7-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9a4e7-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="9a4e7-116">Private</span><span class="sxs-lookup"><span data-stu-id="9a4e7-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="9a4e7-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="9a4e7-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="9a4e7-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9a4e7-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="9a4e7-119">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="9a4e7-120">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-120">Optional.</span></span> <span data-ttu-id="9a4e7-121">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="9a4e7-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="9a4e7-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="9a4e7-123">재정의</span><span class="sxs-lookup"><span data-stu-id="9a4e7-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="9a4e7-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="9a4e7-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="9a4e7-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9a4e7-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="9a4e7-126">MyBase</span><span class="sxs-lookup"><span data-stu-id="9a4e7-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="9a4e7-127">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-127">Optional.</span></span> <span data-ttu-id="9a4e7-128">[공유](../modifiers/shared.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="9a4e7-129">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-129">Optional.</span></span> <span data-ttu-id="9a4e7-130">[그림자](../modifiers/shadows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="9a4e7-131">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-131">Optional.</span></span> <span data-ttu-id="9a4e7-132">[Async](../modifiers/async.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="9a4e7-133">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-133">Required.</span></span> <span data-ttu-id="9a4e7-134">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-134">Name of the procedure.</span></span> <span data-ttu-id="9a4e7-135">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="9a4e7-136">클래스에 대 한 생성자 프로시저를 만들려면 `Sub` 프로시저의 이름을 `New` 키워드로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="9a4e7-137">자세한 내용은 [개체 수명: 개체가 만들어지고 소멸 되는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="9a4e7-138">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-138">Optional.</span></span> <span data-ttu-id="9a4e7-139">제네릭 프로시저에 대 한 형식 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="9a4e7-140">[형식 목록](type-list.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="9a4e7-141">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-141">Optional.</span></span> <span data-ttu-id="9a4e7-142">이 프로시저의 매개 변수를 나타내는 지역 변수 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="9a4e7-143">[매개 변수 목록](parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="9a4e7-144">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-144">Optional.</span></span> <span data-ttu-id="9a4e7-145">이 프로시저가 하나 이상의 `Sub` 프로시저를 구현 하 고 각각이 프로시저의 포함 하는 클래스 또는 구조체에 의해 구현 되는 인터페이스에 정의 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="9a4e7-146">[Implements 문](implements-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="9a4e7-147">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="9a4e7-148">구현할 `Sub` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="9a4e7-149">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="9a4e7-150">파트</span><span class="sxs-lookup"><span data-stu-id="9a4e7-150">Part</span></span>|<span data-ttu-id="9a4e7-151">설명</span><span class="sxs-lookup"><span data-stu-id="9a4e7-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="9a4e7-152">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-152">Required.</span></span> <span data-ttu-id="9a4e7-153">이 프로시저에 포함 된 클래스 또는 구조체에 의해 구현 된 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="9a4e7-154">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-154">Required.</span></span> <span data-ttu-id="9a4e7-155">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="9a4e7-156">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-156">Optional.</span></span> <span data-ttu-id="9a4e7-157">이 프로시저가 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="9a4e7-158">[핸들](handles-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="9a4e7-159">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="9a4e7-160">이 프로시저가 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="9a4e7-161">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="9a4e7-162">파트</span><span class="sxs-lookup"><span data-stu-id="9a4e7-162">Part</span></span>|<span data-ttu-id="9a4e7-163">설명</span><span class="sxs-lookup"><span data-stu-id="9a4e7-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="9a4e7-164">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-164">Required.</span></span> <span data-ttu-id="9a4e7-165">이벤트를 발생 시키는 클래스 또는 구조체의 데이터 형식으로 선언 된 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="9a4e7-166">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-166">Required.</span></span> <span data-ttu-id="9a4e7-167">이 프로시저가 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="9a4e7-168">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="9a4e7-168">Optional.</span></span> <span data-ttu-id="9a4e7-169">이 프로시저 내에서 실행할 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="9a4e7-170">이 프로시저의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a4e7-171">주의</span><span class="sxs-lookup"><span data-stu-id="9a4e7-171">Remarks</span></span>

<span data-ttu-id="9a4e7-172">모든 실행 코드는 프로시저 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="9a4e7-173">호출 코드에 값을 반환 하지 않으려는 경우 `Sub` 프로시저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="9a4e7-174">값을 반환 하려는 경우 `Function` 프로시저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="9a4e7-175">Sub 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="9a4e7-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="9a4e7-176">모듈 수준 에서만 `Sub` 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="9a4e7-177">따라서 sub 프로시저의 선언 컨텍스트는 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="9a4e7-178">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="9a4e7-179">`Sub` 프로시저는 기본적으로 공용 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="9a4e7-180">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="9a4e7-181">프로시저에서 `Implements` 키워드를 사용 하는 경우 포함 하는 클래스 또는 구조체에 `Class` 또는 `Structure` 문 바로 다음에 오는 `Implements` 문이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="9a4e7-182">`Implements` 문은 `implementslist`에 지정 된 각 인터페이스를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="9a4e7-183">그러나 인터페이스가 `Sub` (`definedname`)를 정의 하는 이름은이 프로시저 (`name`)의 이름과 일치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="9a4e7-184">Sub 프로시저에서 반환</span><span class="sxs-lookup"><span data-stu-id="9a4e7-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="9a4e7-185">`Sub` 프로시저가 호출 코드로 반환 되 면 문을 호출한 문 뒤의 문으로 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="9a4e7-186">다음 예에서는 `Sub` 프로시저에서 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="9a4e7-187">`Exit Sub` 및 `Return` 문은 `Sub` 프로시저에서 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="9a4e7-188">프로시저의 어디에 든 많은 `Exit Sub` 및 `Return` 문이 표시 될 수 있으며 `Exit Sub` 문과 `Return` 문을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="9a4e7-189">Sub 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="9a4e7-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="9a4e7-190">문에 프로시저 이름을 사용 하 여 `Sub` 프로시저를 호출한 다음 해당 이름을 괄호 안의 인수 목록에 따라 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="9a4e7-191">인수를 제공 하지 않는 경우에만 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="9a4e7-192">그러나 항상 괄호를 포함 하는 경우 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="9a4e7-193">`Sub` 프로시저와 `Function` 프로시저는 매개 변수를 포함 하 고 일련의 문을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="9a4e7-194">그러나 `Function` 프로시저는 값을 반환 하 고 `Sub` 프로시저는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="9a4e7-195">따라서 식에 `Sub` 프로시저를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="9a4e7-196">`Sub` 프로시저를 호출할 때 `Call` 키워드를 사용할 수 있지만 대부분의 경우에는이 키워드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="9a4e7-197">자세한 내용은 [Call 문](call-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="9a4e7-198">때로는 산술 식을 다시 정렬 하 여 내부 효율성을 높이는 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="9a4e7-199">이러한 이유로 인수 목록에 다른 프로시저를 호출 하는 식이 포함 된 경우 해당 식이 특정 순서로 호출 된다고 가정 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="9a4e7-200">비동기 Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="9a4e7-200">Async Sub Procedures</span></span>

<span data-ttu-id="9a4e7-201">비동기 기능을 사용 하면 명시적 콜백을 사용 하거나 여러 함수 또는 람다 식에서 수동으로 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="9a4e7-202">[비동기](../modifiers/async.md) 한정자를 사용 하 여 프로시저를 표시 하는 경우 프로시저에서 [wait](../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="9a4e7-203">제어가 `Async` 프로시저의 `Await` 식에 도달 하면 제어가 호출자에 게 반환 되 고 대기 작업이 완료 될 때까지 프로시저의 진행률이 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="9a4e7-204">작업이 완료 되 면 프로시저에서 실행을 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="9a4e7-205">`Async` 프로시저는 아직 완료 되지 않은 첫 번째 대기 개체가 발생 하거나 `Async` 프로시저의 끝에 도달 하 여 먼저 발생 하는 경우를 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="9a4e7-206">`Async` 한정자를 사용 하 여 [함수 문을](function-statement.md) 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="9a4e7-207">`Async` 함수는 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>의 반환 형식을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="9a4e7-208">이 항목의 뒷부분에 나오는 예제에서는 반환 형식이 <xref:System.Threading.Tasks.Task%601>인 `Async` 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="9a4e7-209">`Async` `Sub` 프로시저는 기본적으로 값을 반환할 수 없는 이벤트 처리기에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="9a4e7-210">`Async` `Sub` 프로시저는 대기 수 없으며 `Async` `Sub` 프로시저의 호출자는 `Sub` 프로시저가 throw 하는 예외를 catch 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="9a4e7-211">`Async` 프로시저는 [ByRef](../modifiers/byref.md) 매개 변수를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="9a4e7-212">`Async` 프로시저에 대 한 자세한 내용은 [async 및 wait를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="9a4e7-213">예제</span><span class="sxs-lookup"><span data-stu-id="9a4e7-213">Example</span></span>

<span data-ttu-id="9a4e7-214">다음 예에서는 `Sub` 문을 사용 하 여 `Sub` 프로시저의 본문을 형성 하는 이름, 매개 변수 및 코드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="9a4e7-215">예제</span><span class="sxs-lookup"><span data-stu-id="9a4e7-215">Example</span></span>

<span data-ttu-id="9a4e7-216">다음 예제에서 `DelayAsync`는 <xref:System.Threading.Tasks.Task%601>의 반환 형식이 있는 `Async` `Function`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9a4e7-217">`DelayAsync` 에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="9a4e7-218">따라서 `DelayAsync`의 함수 선언에는 `Task(Of Integer)`의 반환 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="9a4e7-219">반환 형식은 `Task(Of Integer)`이므로 다음 문과 같이 `DoSomethingAsync`의 `Await` 식 계산에서는 정수를 생성 합니다. `Dim result As Integer = Await delayTask`는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="9a4e7-220">`startButton_Click` 프로시저는 `Async Sub` 프로시저의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="9a4e7-221">`DoSomethingAsync`은 `Async` 함수 이므로 다음 문과 같이 `DoSomethingAsync`에 대 한 호출 작업은 대기 이어야 합니다. `Await DoSomethingAsync()`는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="9a4e7-222">`Await` 식이 있으므로 `startButton_Click` `Sub` 프로시저에 `Async` 한정자를 사용 하 여 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a4e7-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9a4e7-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a4e7-223">See also</span></span>

- [<span data-ttu-id="9a4e7-224">Implements 문</span><span class="sxs-lookup"><span data-stu-id="9a4e7-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="9a4e7-225">Function 문</span><span class="sxs-lookup"><span data-stu-id="9a4e7-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="9a4e7-226">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="9a4e7-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="9a4e7-227">Dim 문</span><span class="sxs-lookup"><span data-stu-id="9a4e7-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="9a4e7-228">Call 문</span><span class="sxs-lookup"><span data-stu-id="9a4e7-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="9a4e7-229">Of</span><span class="sxs-lookup"><span data-stu-id="9a4e7-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="9a4e7-230">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="9a4e7-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="9a4e7-231">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="9a4e7-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="9a4e7-232">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9a4e7-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="9a4e7-233">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="9a4e7-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
