---
title: Sub 문(Visual Basic)
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
ms.openlocfilehash: 6984e7e9f8695ff5bccdde01171733e740a5d6a7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965958"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="7a6bd-102">Sub 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a6bd-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="7a6bd-103">선언 하 고 이름, 매개 변수를 정의 하는 코드는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a6bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a6bd-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="7a6bd-105">요소</span><span class="sxs-lookup"><span data-stu-id="7a6bd-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="7a6bd-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-106">Optional.</span></span> <span data-ttu-id="7a6bd-107">참조 [특성 목록](attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="7a6bd-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-108">Optional.</span></span> <span data-ttu-id="7a6bd-109">부분 메서드 정의 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="7a6bd-110">참조 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="7a6bd-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-111">Optional.</span></span> <span data-ttu-id="7a6bd-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="7a6bd-113">공용</span><span class="sxs-lookup"><span data-stu-id="7a6bd-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="7a6bd-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="7a6bd-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="7a6bd-115">Friend</span><span class="sxs-lookup"><span data-stu-id="7a6bd-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="7a6bd-116">전용</span><span class="sxs-lookup"><span data-stu-id="7a6bd-116">Private</span></span>](../modifiers/private.md)  
  
    - [<span data-ttu-id="7a6bd-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="7a6bd-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="7a6bd-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="7a6bd-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="7a6bd-119">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="7a6bd-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-120">Optional.</span></span> <span data-ttu-id="7a6bd-121">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="7a6bd-122">오버로드</span><span class="sxs-lookup"><span data-stu-id="7a6bd-122">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="7a6bd-123">재정의</span><span class="sxs-lookup"><span data-stu-id="7a6bd-123">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="7a6bd-124">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="7a6bd-124">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="7a6bd-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7a6bd-125">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="7a6bd-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="7a6bd-126">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="7a6bd-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-127">Optional.</span></span> <span data-ttu-id="7a6bd-128">참조 [공유](../modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-128">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="7a6bd-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-129">Optional.</span></span> <span data-ttu-id="7a6bd-130">참조 [그림자](../modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-130">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="7a6bd-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-131">Optional.</span></span> <span data-ttu-id="7a6bd-132">참조 [비동기](../modifiers/async.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-132">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="7a6bd-133">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-133">Required.</span></span> <span data-ttu-id="7a6bd-134">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-134">Name of the procedure.</span></span> <span data-ttu-id="7a6bd-135">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="7a6bd-136">생성자를 클래스에 대 한 프로시저를 만들려면의 이름을 설정를 `Sub` 하는 절차는 `New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="7a6bd-137">자세한 내용은 참조 하세요. [개체 수명: 개체가 만들어지고 제거 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="7a6bd-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-138">Optional.</span></span> <span data-ttu-id="7a6bd-139">제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="7a6bd-140">참조 [유형 목록](type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-140">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="7a6bd-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-141">Optional.</span></span> <span data-ttu-id="7a6bd-142">이 절차의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="7a6bd-143">참조 [매개 변수 목록](parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-143">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="7a6bd-144">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-144">Optional.</span></span> <span data-ttu-id="7a6bd-145">하나 이상의이 절차를 구현 함을 나타냅니다 `Sub` 절차,이 절차의 포함 하는 클래스 또는 구조체에서 구현 된 인터페이스에 정의 된 각각.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="7a6bd-146">참조 [문을 구현](implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-146">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="7a6bd-147">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="7a6bd-148">구현할 `Sub` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-148">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="7a6bd-149">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-149">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="7a6bd-150">파트</span><span class="sxs-lookup"><span data-stu-id="7a6bd-150">Part</span></span>|<span data-ttu-id="7a6bd-151">설명</span><span class="sxs-lookup"><span data-stu-id="7a6bd-151">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="7a6bd-152">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-152">Required.</span></span> <span data-ttu-id="7a6bd-153">이 프로시저에 의해 구현 된 인터페이스의 이름을 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="7a6bd-154">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-154">Required.</span></span> <span data-ttu-id="7a6bd-155">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-155">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="7a6bd-156">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-156">Optional.</span></span> <span data-ttu-id="7a6bd-157">이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="7a6bd-158">참조 [처리](handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-158">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="7a6bd-159">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="7a6bd-160">이 프로시저에서 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-160">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="7a6bd-161">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-161">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="7a6bd-162">파트</span><span class="sxs-lookup"><span data-stu-id="7a6bd-162">Part</span></span>|<span data-ttu-id="7a6bd-163">설명</span><span class="sxs-lookup"><span data-stu-id="7a6bd-163">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="7a6bd-164">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-164">Required.</span></span> <span data-ttu-id="7a6bd-165">클래스 또는 구조의 이벤트를 발생 시키는 데이터 형식으로 선언 하는 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="7a6bd-166">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-166">Required.</span></span> <span data-ttu-id="7a6bd-167">이 프로시저에서 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-167">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="7a6bd-168">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-168">Optional.</span></span> <span data-ttu-id="7a6bd-169">이 프로시저 내에서 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-169">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="7a6bd-170">이 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-170">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a6bd-171">설명</span><span class="sxs-lookup"><span data-stu-id="7a6bd-171">Remarks</span></span>  
 <span data-ttu-id="7a6bd-172">프로시저 내에서 실행 되는 모든 코드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="7a6bd-173">사용 된 `Sub` 프로시저가 호출 코드에 값을 반환 하지 않을 경우.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="7a6bd-174">사용 된 `Function` 프로시저 값을 반환 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-174">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="7a6bd-175">Sub 프로시저를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-175">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="7a6bd-176">정의할 수는 `Sub` 모듈 수준 에서만 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="7a6bd-177">Sub 프로시저 선언 컨텍스트 클래스, 구조체, 모듈 또는 인터페이스에 따라서 수 있어야 하 고 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="7a6bd-178">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="7a6bd-179">`Sub` 프로시저는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="7a6bd-180">액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-180">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="7a6bd-181">프로시저를 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스 또는 구조체 있어야를 `Implements` 바로 뒤에 오는 문을 해당 `Class` 또는 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="7a6bd-182">합니다 `Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="7a6bd-183">그러나 사용 되는 인터페이스는 다음과 같이 정의 됩니다. 이름을 합니다 `Sub` (에서 `definedname`)이이 프로시저의 이름과 일치 하지 않아도 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="7a6bd-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="7a6bd-184">Sub 프로시저에서 반환</span><span class="sxs-lookup"><span data-stu-id="7a6bd-184">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="7a6bd-185">경우는 `Sub` 프로시저가 호출 코드에 반환 되 면 실행이 호출 하는 문 다음에 나오는 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="7a6bd-186">다음 예제에서는에서 반환 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-186">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="7a6bd-187">합니다 `Exit Sub` 하 고 `Return` 문을 사용 하면 즉시 종료를 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="7a6bd-188">임의 개수의 `Exit Sub` 하 고 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Sub` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="7a6bd-189">Sub 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-189">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="7a6bd-190">호출을 `Sub` 문에서 프로시저 이름을 사용 하 여 해당 이름을 해당 인수 목록의 괄호를 사용 하 여 다음 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="7a6bd-191">모든 인수를 지정 하지 않으면 하는 경우에 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="7a6bd-192">그러나 코드는 항상 괄호를 포함 하는 경우 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-192">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="7a6bd-193">A `Sub` 프로시저와 `Function` 프로시저 매개 변수를 포함할 수 있으며 일련의 문 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="7a6bd-194">그러나를 `Function` 프로시저 반환 값 및 `Sub` 프로시저 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="7a6bd-195">따라서 사용할 수 없습니다는 `Sub` 식에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="7a6bd-196">사용할 수는 `Call` 호출할 때 키워드는 `Sub` 프로시저 되지만 해당 키워드는 대부분의 용도로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="7a6bd-197">자세한 내용은 [Call 문을](call-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-197">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="7a6bd-198">Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="7a6bd-199">이런 이유로 인수 목록에 다른 프로시저를 호출 하는 식이 포함 된 경우 해서는 안 됩니다 가정 식도 특정 순서로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="7a6bd-200">비동기 Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="7a6bd-200">Async Sub Procedures</span></span>  
 <span data-ttu-id="7a6bd-201">비동기 기능을 사용 하면 명시적 콜백을 사용 하거나 여러 개의 함수 또는 람다 식에서 코드를 수동으로 분할 하지 않고 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="7a6bd-202">사용 하 여 프로시저를 표시 하는 경우는 [비동기](../modifiers/async.md) 한정자를 사용할 수는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 절차에서 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="7a6bd-203">도달 하면 컨트롤이 `Await` 식에는 `Async` 프로시저 호출자에 게 제어가 반환 및 대기 중인된 작업이 완료 될 때까지 프로시저가 진행이 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="7a6bd-204">작업이 완료 되 면 실행 절차에서 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-204">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a6bd-205">`Async` 프로시저가 호출자 중 하나는 첫 번째 대기 된 개체를 아직 완료 되지 발견 될 때 또는 끝에 반환는 `Async` 프로시저에 도달 중 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="7a6bd-206">표시할 수도 있습니다는 [Function 문](function-statement.md) 사용 하 여는 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="7a6bd-207">`Async` 함수는 반환 형식으로 지정할 수 있습니다 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="7a6bd-208">예로 나중에이 항목에서는 프로그램 `Async` 의 반환 형식을 가진 함수 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="7a6bd-209">`Async` `Sub` 프로시저는 주로 이벤트 처리기에 대 한 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="7a6bd-210">`Async` `Sub` 프로시저 대기할 수 없습니다 및 호출자는 `Async` `Sub` 프로시저 예외를 catch 할 수 없습니다는 `Sub` 프로시저 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="7a6bd-211">`Async` 프로시저는 모든 선언할 수 없습니다 [ByRef](../modifiers/byref.md) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="7a6bd-212">에 대 한 자세한 내용은 `Async` 절차를 참조 하세요 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md)합니다 [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a6bd-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a6bd-213">예제</span><span class="sxs-lookup"><span data-stu-id="7a6bd-213">Example</span></span>  
 <span data-ttu-id="7a6bd-214">다음 예제에서는 합니다 `Sub` 을 이름, 매개 변수 및 코드의 본문을 형성 하는 정의 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="7a6bd-215">예제</span><span class="sxs-lookup"><span data-stu-id="7a6bd-215">Example</span></span>  
 <span data-ttu-id="7a6bd-216">다음 예에서 `DelayAsync` 되는 `Async` `Function` 반환 형식이 있는 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7a6bd-217">`DelayAsync` 에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="7a6bd-218">따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 합니다. `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="7a6bd-219">반환 형식 이므로 `Task(Of Integer)`를 평가 합니다 `Await` 식 `DoSomethingAsync` 문에 다음과 같이 정수가 생성: `Dim result As Integer = Await delayTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="7a6bd-220">`startButton_Click` 절차는의 예는 `Async Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="7a6bd-221">때문에 `DoSomethingAsync` 되는 `Async` 함수에 대 한 호출에 대 한 작업 `DoSomethingAsync` 다음 문 에서처럼 대기 해야 합니다: `Await DoSomethingAsync()`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="7a6bd-222">합니다 `startButton_Click` `Sub` 프로시저를 사용 하 여 정의 되어야 합니다는 `Async` 한정자 있기 때문에 `Await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7a6bd-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7a6bd-223">참고자료</span><span class="sxs-lookup"><span data-stu-id="7a6bd-223">See also</span></span>
- [<span data-ttu-id="7a6bd-224">Implements 문</span><span class="sxs-lookup"><span data-stu-id="7a6bd-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="7a6bd-225">Function 문</span><span class="sxs-lookup"><span data-stu-id="7a6bd-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7a6bd-226">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="7a6bd-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="7a6bd-227">Dim 문</span><span class="sxs-lookup"><span data-stu-id="7a6bd-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="7a6bd-228">Call 문</span><span class="sxs-lookup"><span data-stu-id="7a6bd-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="7a6bd-229">Of</span><span class="sxs-lookup"><span data-stu-id="7a6bd-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="7a6bd-230">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="7a6bd-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="7a6bd-231">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="7a6bd-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="7a6bd-232">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7a6bd-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="7a6bd-233">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="7a6bd-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
