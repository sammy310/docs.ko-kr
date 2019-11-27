---
title: GoTo 문
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
ms.openlocfilehash: d5cdcd214c9679e245645505fe11cb5d521ce085
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351080"
---
# <a name="goto-statement"></a><span data-ttu-id="e0c5d-102">GoTo 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-102">GoTo Statement</span></span>
<span data-ttu-id="e0c5d-103">프로시저에서 지정 된 줄로 무조건 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="e0c5d-105">파트</span><span class="sxs-lookup"><span data-stu-id="e0c5d-105">Part</span></span>  
 `line`  
 <span data-ttu-id="e0c5d-106">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-106">Required.</span></span> <span data-ttu-id="e0c5d-107">모든 줄 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c5d-108">주의</span><span class="sxs-lookup"><span data-stu-id="e0c5d-108">Remarks</span></span>  
 <span data-ttu-id="e0c5d-109">`GoTo` 문은 표시 되는 프로시저의 줄로만 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="e0c5d-110">줄에는 `GoTo` 참조할 수 있는 줄 레이블이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="e0c5d-111">자세한 내용은 [방법: 레이블 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0c5d-112">`GoTo` 문을 사용 하면 코드를 읽고 유지 관리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="e0c5d-113">가능 하면 컨트롤 구조를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="e0c5d-114">자세한 내용은 [제어 흐름](../../../visual-basic/programming-guide/language-features/control-flow/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="e0c5d-115">`GoTo` 문을 사용 하 여 `For``Next`, `For Each`...`Next`, `SyncLock`,`End SyncLock`... `Try`,`Catch`,`Finally``With`또는`End With`생성을 안에 있는 레이블로 분기할 수 없습니다. (예를 들어,).`Using``End Using`</span><span class="sxs-lookup"><span data-stu-id="e0c5d-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="e0c5d-116">분기 및 시도 생성</span><span class="sxs-lookup"><span data-stu-id="e0c5d-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="e0c5d-117">`Try`...`Catch`...`Finally` 생성 내에서 `GoTo` 문으로 분기 하는 데 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="e0c5d-118">블록 또는 지역</span><span class="sxs-lookup"><span data-stu-id="e0c5d-118">Block or region</span></span>|<span data-ttu-id="e0c5d-119">외부에서 분기</span><span class="sxs-lookup"><span data-stu-id="e0c5d-119">Branching in from outside</span></span>|<span data-ttu-id="e0c5d-120">내부에서 외부 분기</span><span class="sxs-lookup"><span data-stu-id="e0c5d-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="e0c5d-121">`Try` 블록</span><span class="sxs-lookup"><span data-stu-id="e0c5d-121">`Try` block</span></span>|<span data-ttu-id="e0c5d-122">동일한 <sup>생성의</sup> `Catch` 블록 에서만</span><span class="sxs-lookup"><span data-stu-id="e0c5d-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="e0c5d-123">전체 생성 외부에만</span><span class="sxs-lookup"><span data-stu-id="e0c5d-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="e0c5d-124">`Catch` 블록</span><span class="sxs-lookup"><span data-stu-id="e0c5d-124">`Catch` block</span></span>|<span data-ttu-id="e0c5d-125">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="e0c5d-125">Never allowed</span></span>|<span data-ttu-id="e0c5d-126">전체 <sup>생성 외부 또는 동일한 생성의</sup> `Try` 블록에만 해당</span><span class="sxs-lookup"><span data-stu-id="e0c5d-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="e0c5d-127">`Finally` 블록</span><span class="sxs-lookup"><span data-stu-id="e0c5d-127">`Finally` block</span></span>|<span data-ttu-id="e0c5d-128">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="e0c5d-128">Never allowed</span></span>|<span data-ttu-id="e0c5d-129">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="e0c5d-129">Never allowed</span></span>|  
  
 <span data-ttu-id="e0c5d-130"><sup>1</sup> `Try`...`Catch`...`Finally` 생성이 다른에 중첩 되는 경우 `Catch` 블록은 자체 중첩 수준에서 `Try` 블록으로 분기할 수 있지만 다른 `Try` 블록으로는 분기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="e0c5d-131">중첩 된 `Try`...`Catch`...`Finally` 생성은 중첩 된 생성의 `Try` 또는 `Catch` 블록에 완전히 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="e0c5d-132">다음 그림에서는 서로 중첩 된 하나의 `Try` 생성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="e0c5d-133">두 생성의 블록 사이에 있는 다양 한 분기가 유효 하거나 유효 하지 않은 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="e0c5d-135">예제</span><span class="sxs-lookup"><span data-stu-id="e0c5d-135">Example</span></span>  
 <span data-ttu-id="e0c5d-136">다음 예에서는 `GoTo` 문을 사용 하 여 프로시저의 줄 레이블로 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5d-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="e0c5d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0c5d-137">See also</span></span>

- [<span data-ttu-id="e0c5d-138">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="e0c5d-139">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="e0c5d-140">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="e0c5d-141">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="e0c5d-142">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="e0c5d-143">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="e0c5d-144">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="e0c5d-145">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="e0c5d-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
