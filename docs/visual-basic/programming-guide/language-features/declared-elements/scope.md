---
title: 범위
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 1bee904996257474b7457b2aefb1f17d250933cb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410736"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="005e7-102">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-102">Scope in Visual Basic</span></span>

<span data-ttu-id="005e7-103">선언 된 요소의 *범위* 는 이름을 한정 하거나 [Imports 문 (.net 네임 스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)을 통해 사용할 수 있도록 하는 것을 제외 하 고이를 참조할 수 있는 모든 코드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="005e7-104">요소는 다음 수준 중 하나에서 범위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="005e7-105">Level</span><span class="sxs-lookup"><span data-stu-id="005e7-105">Level</span></span>|<span data-ttu-id="005e7-106">Description</span><span class="sxs-lookup"><span data-stu-id="005e7-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="005e7-107">블록 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-107">Block scope</span></span>|<span data-ttu-id="005e7-108">선언 된 코드 블록 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="005e7-109">프로시저 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-109">Procedure scope</span></span>|<span data-ttu-id="005e7-110">선언 된 프로시저 내의 모든 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="005e7-111">모듈 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-111">Module scope</span></span>|<span data-ttu-id="005e7-112">선언 된 모듈, 클래스 또는 구조체 내의 모든 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="005e7-113">네임 스페이스 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-113">Namespace scope</span></span>|<span data-ttu-id="005e7-114">선언 된 네임 스페이스의 모든 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="005e7-115">이러한 범위의 범위는 가장 좁은 (블록)에서 가장 넓은 (네임 스페이스)로 진행 됩니다. 여기서 가장 작은 *범위* 는 한정자 없이 요소를 참조할 수 있는 가장 작은 코드 집합을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="005e7-116">자세한 내용은이 페이지의 "범위 수준"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="005e7-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="005e7-117">범위 지정 및 변수 정의</span><span class="sxs-lookup"><span data-stu-id="005e7-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="005e7-118">요소를 선언할 때 요소의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="005e7-119">범위는 다음 요인에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="005e7-120">요소를 선언 하는 영역 (블록, 프로시저, 모듈, 클래스 또는 구조체)</span><span class="sxs-lookup"><span data-stu-id="005e7-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="005e7-121">요소의 선언이 포함 된 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="005e7-122">요소에 대해 선언 하는 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-122">The access level you declare for the element</span></span>

<span data-ttu-id="005e7-123">이름은 같지만 범위가 다른 변수를 정의할 때 주의 해야 합니다. 이렇게 하면 예기치 않은 결과가 발생할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="005e7-124">자세한 내용은 [References to Declared Elements](references-to-declared-elements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="005e7-124">For more information, see [References to Declared Elements](references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="005e7-125">범위 수준</span><span class="sxs-lookup"><span data-stu-id="005e7-125">Levels of Scope</span></span>

<span data-ttu-id="005e7-126">프로그래밍 요소는 선언 하는 지역 전체에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="005e7-127">동일한 지역의 모든 코드는 이름을 한정 하지 않고 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="005e7-128">블록 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-128">Block Scope</span></span>

<span data-ttu-id="005e7-129">블록은 다음과 같은 시작 및 종료 선언 문 내에 포함 된 문의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="005e7-130">`Do` 및 `Loop`</span><span class="sxs-lookup"><span data-stu-id="005e7-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="005e7-131">`For`[ `Each` ] 및`Next`</span><span class="sxs-lookup"><span data-stu-id="005e7-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="005e7-132">`If` 및 `End If`</span><span class="sxs-lookup"><span data-stu-id="005e7-132">`If` and `End If`</span></span>

- <span data-ttu-id="005e7-133">`Select` 및 `End Select`</span><span class="sxs-lookup"><span data-stu-id="005e7-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="005e7-134">`SyncLock` 및 `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="005e7-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="005e7-135">`Try` 및 `End Try`</span><span class="sxs-lookup"><span data-stu-id="005e7-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="005e7-136">`While` 및 `End While`</span><span class="sxs-lookup"><span data-stu-id="005e7-136">`While` and `End While`</span></span>

- <span data-ttu-id="005e7-137">`With` 및 `End With`</span><span class="sxs-lookup"><span data-stu-id="005e7-137">`With` and `End With`</span></span>

<span data-ttu-id="005e7-138">블록 내에서 변수를 선언 하는 경우 해당 블록 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="005e7-139">다음 예제에서 정수 변수의 범위는 `cube` 와 사이의 블록 이며 `If` 실행이 `End If` 블록 밖으로 전달 되는 경우를 더 이상 참조할 수 없습니다 `cube` .</span><span class="sxs-lookup"><span data-stu-id="005e7-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="005e7-140">변수의 범위가 블록으로 제한 되는 경우에도 여전히 전체 프로시저의 수명입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="005e7-141">프로시저를 실행 하는 동안 블록을 두 번 이상 입력 하는 경우 각 블록 변수는 이전 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="005e7-142">이러한 경우 예기치 않은 결과를 방지 하기 위해 블록의 시작 부분에서 블록 변수를 초기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="005e7-143">프로시저 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-143">Procedure Scope</span></span>

<span data-ttu-id="005e7-144">프로시저 내에서 선언 된 요소는 해당 프로시저 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="005e7-145">선언을 포함 하는 프로시저만이 프로시저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="005e7-146">이 수준의 변수는 *지역 변수*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="005e7-147">[Static](../../../language-reference/modifiers/static.md) 키워드를 사용 하거나 사용 하지 않고 [Dim 문으로](../../../language-reference/statements/dim-statement.md)선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-147">You declare them with the [Dim Statement](../../../language-reference/statements/dim-statement.md), with or without the [Static](../../../language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="005e7-148">프로시저 및 블록 범위는 밀접 하 게 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="005e7-149">프로시저 내에서 변수를 선언 하 고 해당 프로시저 내의 블록 외부에서 변수를 선언 하는 경우 해당 변수는 블록 범위가 있는 것으로 간주할 수 있습니다. 여기서 블록은 전체 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="005e7-150">변수가 있는 경우에도 모든 로컬 요소는 `Static` 해당 요소가 표시 되는 프로시저에 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="005e7-151">프로시저 내에서 [Public](../../../language-reference/modifiers/public.md) 키워드를 사용 하 여 요소를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-151">You cannot declare any element using the [Public](../../../language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="005e7-152">모듈 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-152">Module Scope</span></span>

<span data-ttu-id="005e7-153">편의를 위해 모듈, 클래스 및 구조에는 단일 용어 *모듈 수준이* 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="005e7-154">선언 문을 프로시저 또는 블록 외부에 배치 하 고 모듈, 클래스 또는 구조체 내에 배치 하 여이 수준에서 요소를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="005e7-155">모듈 수준에서 선언을 만들면 선택 하는 액세스 수준에 따라 범위가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="005e7-156">모듈, 클래스 또는 구조가 포함 된 네임 스페이스도 범위에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="005e7-157">[Private](../../../language-reference/modifiers/private.md) 액세스 수준을 선언 하는 요소는 해당 모듈의 모든 프로시저에서 사용할 수 있지만 다른 모듈의 코드에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-157">Elements for which you declare [Private](../../../language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="005e7-158">`Dim`액세스 수준 키워드를 사용 하지 않는 경우 모듈 수준의 문은 기본적으로로 설정 `Private` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="005e7-159">그러나 문에 키워드를 사용 하 여 범위 및 액세스 수준을 보다 명확 하 게 만들 수 있습니다 `Private` `Dim` .</span><span class="sxs-lookup"><span data-stu-id="005e7-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="005e7-160">다음 예에서는 모듈에 정의 된 모든 프로시저가 문자열 변수를 참조할 수 있습니다 `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="005e7-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="005e7-161">두 번째 프로시저가 호출 되 면 대화 상자에 문자열 변수의 내용이 표시 됩니다 `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="005e7-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a><span data-ttu-id="005e7-162">네임 스페이스 범위</span><span class="sxs-lookup"><span data-stu-id="005e7-162">Namespace Scope</span></span>

<span data-ttu-id="005e7-163">[Friend](../../../language-reference/modifiers/friend.md) 또는 [Public](../../../language-reference/modifiers/public.md) 키워드를 사용 하 여 모듈 수준에서 요소를 선언 하는 경우 요소가 선언 되는 네임 스페이스 전체의 모든 프로시저에서 해당 요소를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-163">If you declare an element at module level using the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="005e7-164">앞의 예제를 다음과 같이 변경 하 여 문자열 변수를 `strMsg` 선언 네임 스페이스의 모든 위치에서 코드로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="005e7-165">네임 스페이스 범위에는 중첩 된 네임 스페이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="005e7-166">네임 스페이스 내에서 사용할 수 있는 요소는 해당 네임 스페이스 내에 중첩 된 모든 네임 스페이스 내 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="005e7-167">프로젝트에 [네임 스페이스 문이](../../../language-reference/statements/namespace-statement.md)포함 되어 있지 않으면 프로젝트의 모든 항목이 동일한 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-167">If your project does not contain any [Namespace Statement](../../../language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="005e7-168">이 경우 네임 스페이스 범위를 프로젝트 범위로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="005e7-169">`Public`모듈, 클래스 또는 구조체의 요소는 해당 프로젝트를 참조 하는 모든 프로젝트 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="005e7-170">범위 선택</span><span class="sxs-lookup"><span data-stu-id="005e7-170">Choice of Scope</span></span>

<span data-ttu-id="005e7-171">변수를 선언 하는 경우 범위를 선택할 때 다음 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="005e7-172">지역 변수의 장점</span><span class="sxs-lookup"><span data-stu-id="005e7-172">Advantages of Local Variables</span></span>

<span data-ttu-id="005e7-173">지역 변수는 다음과 같은 이유로 모든 종류의 임시 계산에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="005e7-174">**이름 충돌 방지.**</span><span class="sxs-lookup"><span data-stu-id="005e7-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="005e7-175">지역 변수 이름은 충돌을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="005e7-176">예를 들어 라는 변수를 포함 하는 여러 다른 프로시저를 만들 수 있습니다 `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="005e7-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="005e7-177">각 `intTemp` 프로시저는 지역 변수로 선언 되므로 각 프로시저는 자체 버전의만 인식 `intTemp` 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="005e7-178">`intTemp`다른 프로시저의 변수에 영향을 주지 않고 한 프로시저에서 로컬의 값을 변경할 수 있습니다 `intTemp` .</span><span class="sxs-lookup"><span data-stu-id="005e7-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="005e7-179">**메모리 소비**</span><span class="sxs-lookup"><span data-stu-id="005e7-179">**Memory Consumption.**</span></span> <span data-ttu-id="005e7-180">지역 변수는 프로시저를 실행 하는 동안에만 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="005e7-181">이 프로시저는 호출 코드로 반환 될 때 해당 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="005e7-182">반면 [공유](../../../language-reference/modifiers/shared.md) 및 [정적](../../../language-reference/modifiers/static.md) 변수는 응용 프로그램 실행이 중지 될 때까지 메모리 리소스를 사용 하므로 필요한 경우에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-182">By contrast, [Shared](../../../language-reference/modifiers/shared.md) and [Static](../../../language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="005e7-183">인스턴스 *변수* 는 인스턴스가 계속 존재 하는 동안 메모리를 사용 하며,이로 인해 지역 변수 보다 효율성이 낮지만 또는 변수 보다 효율성이 높아집니다 `Shared` `Static` .</span><span class="sxs-lookup"><span data-stu-id="005e7-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="005e7-184">범위 최소화</span><span class="sxs-lookup"><span data-stu-id="005e7-184">Minimizing Scope</span></span>

<span data-ttu-id="005e7-185">일반적으로 변수 또는 상수를 선언 하는 경우 범위를 최대한 좁게 만드는 것이 좋습니다 (블록 범위는 가장 좁은).</span><span class="sxs-lookup"><span data-stu-id="005e7-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="005e7-186">이렇게 하면 메모리를 절약 하 고 잘못 된 변수를 잘못 참조 하는 코드의 가능성을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="005e7-187">마찬가지로 프로시저 호출 사이에 값을 유지 해야 하는 경우에만 변수를 [정적](../../../language-reference/modifiers/static.md) 으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="005e7-187">Similarly, you should declare a variable to be [Static](../../../language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="005e7-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="005e7-188">See also</span></span>

- [<span data-ttu-id="005e7-189">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="005e7-189">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="005e7-190">방법: 변수의 범위 제어</span><span class="sxs-lookup"><span data-stu-id="005e7-190">How to: Control the Scope of a Variable</span></span>](how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="005e7-191">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="005e7-191">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="005e7-192">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="005e7-192">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="005e7-193">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="005e7-193">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="005e7-194">변수 선언</span><span class="sxs-lookup"><span data-stu-id="005e7-194">Variable Declaration</span></span>](../variables/variable-declaration.md)
