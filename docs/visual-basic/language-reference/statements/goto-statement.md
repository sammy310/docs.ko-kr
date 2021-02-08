---
description: '다음에 대 한 자세한 정보: GoTo 문'
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
ms.openlocfilehash: 804baec130111562225b09cbdc7b5fb2d73adba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769054"
---
# <a name="goto-statement"></a><span data-ttu-id="9d1aa-103">GoTo 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-103">GoTo Statement</span></span>

<span data-ttu-id="9d1aa-104">프로시저에서 지정 된 줄로 무조건 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-104">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d1aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d1aa-105">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="9d1aa-106">파트</span><span class="sxs-lookup"><span data-stu-id="9d1aa-106">Part</span></span>  

 `line`  
 <span data-ttu-id="9d1aa-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-107">Required.</span></span> <span data-ttu-id="9d1aa-108">모든 줄 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-108">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d1aa-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d1aa-109">Remarks</span></span>  

 <span data-ttu-id="9d1aa-110">`GoTo`문은 표시 되는 프로시저의 줄로만 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-110">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="9d1aa-111">줄에는를 참조할 수 있는 줄 레이블이 있어야 합니다 `GoTo` .</span><span class="sxs-lookup"><span data-stu-id="9d1aa-111">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="9d1aa-112">자세한 내용은 [방법: 레이블 문](../../programming-guide/program-structure/how-to-label-statements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-112">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d1aa-113">`GoTo` 문을 사용 하면 코드를 읽고 유지 관리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-113">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="9d1aa-114">가능 하면 컨트롤 구조를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-114">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="9d1aa-115">자세한 내용은 [Control Flow](../../programming-guide/language-features/control-flow/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-115">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="9d1aa-116">문을 사용 하 여 (..., ..., ..., ... `GoTo` `For` `Next` `For Each` `Next` `SyncLock` `End SyncLock` , `Try` `Catch` ...) 외부에서 분기할 수 없습니다. ... `Finally` , `With` ... `End With` 또는 `Using` ... `End Using` 생성이 내부 레이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-116">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="9d1aa-117">분기 및 시도 생성</span><span class="sxs-lookup"><span data-stu-id="9d1aa-117">Branching and Try Constructions</span></span>  

 <span data-ttu-id="9d1aa-118">내 ... `Try` `Catch` ...`Finally` 다음 규칙은 문을 사용 하 여 분기에 적용 `GoTo` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-118">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="9d1aa-119">블록 또는 지역</span><span class="sxs-lookup"><span data-stu-id="9d1aa-119">Block or region</span></span>|<span data-ttu-id="9d1aa-120">외부에서 분기</span><span class="sxs-lookup"><span data-stu-id="9d1aa-120">Branching in from outside</span></span>|<span data-ttu-id="9d1aa-121">내부에서 외부 분기</span><span class="sxs-lookup"><span data-stu-id="9d1aa-121">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="9d1aa-122">`Try` 거부</span><span class="sxs-lookup"><span data-stu-id="9d1aa-122">`Try` block</span></span>|<span data-ttu-id="9d1aa-123">`Catch`같은 생성의 블록 에서만 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9d1aa-123">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="9d1aa-124">전체 생성 외부에만</span><span class="sxs-lookup"><span data-stu-id="9d1aa-124">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="9d1aa-125">`Catch` 거부</span><span class="sxs-lookup"><span data-stu-id="9d1aa-125">`Catch` block</span></span>|<span data-ttu-id="9d1aa-126">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9d1aa-126">Never allowed</span></span>|<span data-ttu-id="9d1aa-127">전체 생성 외부 또는 `Try` 동일한 생성의 블록 <sup></sup> 에만 해당</span><span class="sxs-lookup"><span data-stu-id="9d1aa-127">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="9d1aa-128">`Finally` 거부</span><span class="sxs-lookup"><span data-stu-id="9d1aa-128">`Finally` block</span></span>|<span data-ttu-id="9d1aa-129">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9d1aa-129">Never allowed</span></span>|<span data-ttu-id="9d1aa-130">허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="9d1aa-130">Never allowed</span></span>|  
  
 <span data-ttu-id="9d1aa-131"><sup>1</sup> 일 경우 `Try` `Catch` ...`Finally` 생성은 다른 중첩 수준에서 중첩 되 고 `Catch` `Try` 다른 블록에는 포함 되지 않을 수 있습니다 `Try` .</span><span class="sxs-lookup"><span data-stu-id="9d1aa-131"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="9d1aa-132">중첩 된 ... `Try` `Catch` ...`Finally` 생성 `Try` 은 중첩 된 생성의 또는 블록에 완전히 포함 되어야 합니다 `Catch` .</span><span class="sxs-lookup"><span data-stu-id="9d1aa-132">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="9d1aa-133">다음 그림에서는 `Try` 다른 중첩 내에 중첩 된 하나의 생성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-133">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="9d1aa-134">두 생성의 블록 사이에 있는 다양 한 분기가 유효 하거나 유효 하지 않은 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-134">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 생성에서 분기의 그래픽 다이어그램](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="9d1aa-136">예제</span><span class="sxs-lookup"><span data-stu-id="9d1aa-136">Example</span></span>  

 <span data-ttu-id="9d1aa-137">다음 예에서는 문을 사용 하 여 `GoTo` 프로시저의 줄 레이블로 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1aa-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="9d1aa-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d1aa-138">See also</span></span>

- [<span data-ttu-id="9d1aa-139">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-139">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="9d1aa-140">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-140">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="9d1aa-141">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-141">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="9d1aa-142">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-142">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="9d1aa-143">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-143">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="9d1aa-144">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-144">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="9d1aa-145">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-145">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="9d1aa-146">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="9d1aa-146">With...End With Statement</span></span>](with-end-with-statement.md)
