---
title: GoTo 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: c4dd249620ba1bf445642ce4600498f6beb30461
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827772"
---
# <a name="goto-statement"></a><span data-ttu-id="b5c29-102">GoTo 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-102">GoTo Statement</span></span>
<span data-ttu-id="b5c29-103">프로시저에 지정된 된 줄으로 무조건 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c29-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5c29-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="b5c29-105">파트</span><span class="sxs-lookup"><span data-stu-id="b5c29-105">Part</span></span>  
 `line`  
 <span data-ttu-id="b5c29-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b5c29-106">Required.</span></span> <span data-ttu-id="b5c29-107">모든 줄 레이블을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5c29-108">설명</span><span class="sxs-lookup"><span data-stu-id="b5c29-108">Remarks</span></span>  
 <span data-ttu-id="b5c29-109">`GoTo` 문은 나타나는 프로시저의 줄에만 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="b5c29-110">줄에 있는 줄 레이블이 있어야 `GoTo` 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="b5c29-111">자세한 내용은 [방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5c29-112">`GoTo` 문을 코드를 읽고 관리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="b5c29-113">가능 하면 제어 구조를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="b5c29-114">자세한 내용은 [제어 흐름](../../../visual-basic/programming-guide/language-features/control-flow/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="b5c29-115">사용할 수 없습니다는 `GoTo` 문 외부에서 분기를 `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, 또는 `Using`... `End Using` 안에 레이블 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="b5c29-116">분기 및 생성을 시도</span><span class="sxs-lookup"><span data-stu-id="b5c29-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="b5c29-117">내는 `Try`... `Catch`... `Finally` 생성을 사용 하 여 분기 다음 규칙이 적용 된 `GoTo` 문.</span><span class="sxs-lookup"><span data-stu-id="b5c29-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="b5c29-118">블록 또는 지역</span><span class="sxs-lookup"><span data-stu-id="b5c29-118">Block or region</span></span>|<span data-ttu-id="b5c29-119">외부에서 분기</span><span class="sxs-lookup"><span data-stu-id="b5c29-119">Branching in from outside</span></span>|<span data-ttu-id="b5c29-120">내부에서 외부로 분기</span><span class="sxs-lookup"><span data-stu-id="b5c29-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="b5c29-121">`Try` 블록</span><span class="sxs-lookup"><span data-stu-id="b5c29-121">`Try` block</span></span>|<span data-ttu-id="b5c29-122">만 `Catch` 동일한 생성 블록 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5c29-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="b5c29-123">에 전체 구문의 외부</span><span class="sxs-lookup"><span data-stu-id="b5c29-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="b5c29-124">`Catch` 블록</span><span class="sxs-lookup"><span data-stu-id="b5c29-124">`Catch` block</span></span>|<span data-ttu-id="b5c29-125">허용 되지</span><span class="sxs-lookup"><span data-stu-id="b5c29-125">Never allowed</span></span>|<span data-ttu-id="b5c29-126">에 전체 구문의 외부 또는 합니다 `Try` 동일한 생성 블록 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5c29-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="b5c29-127">`Finally` 블록</span><span class="sxs-lookup"><span data-stu-id="b5c29-127">`Finally` block</span></span>|<span data-ttu-id="b5c29-128">허용 되지</span><span class="sxs-lookup"><span data-stu-id="b5c29-128">Never allowed</span></span>|<span data-ttu-id="b5c29-129">허용 되지</span><span class="sxs-lookup"><span data-stu-id="b5c29-129">Never allowed</span></span>|  
  
 <span data-ttu-id="b5c29-130"><sup>1</sup> 없으면 `Try`... `Catch`... `Finally` 생성 다른 내에 중첩 되어를 `Catch` 블록으로 분기할 수는 `Try` 자체 중첩 수준에 포함 되지 않습니다 다른 블록 `Try` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="b5c29-131">중첩 된 `Try`... `Catch`... `Finally` 생성에 완전히 포함 되어야 합니다는 `Try` 또는 `Catch` 중첩 되는 생성 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="b5c29-132">다음 그림에 나와 하나 `Try` 다른 내에 중첩 된 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="b5c29-133">두 구문의 블록 간에 다양 한 분기 잘못 되었거나 잘못 되었습니다.으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="b5c29-135">예제</span><span class="sxs-lookup"><span data-stu-id="b5c29-135">Example</span></span>  
 <span data-ttu-id="b5c29-136">다음 예제에서는 `GoTo` 문을 프로시저의 줄 레이블로 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5c29-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="b5c29-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5c29-137">See also</span></span>

- [<span data-ttu-id="b5c29-138">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="b5c29-139">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="b5c29-140">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="b5c29-141">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="b5c29-142">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="b5c29-143">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="b5c29-144">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="b5c29-145">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="b5c29-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
