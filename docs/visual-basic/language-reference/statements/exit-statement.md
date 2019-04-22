---
title: Exit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832634"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="43869-102">Exit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43869-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="43869-103">프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음 문으로 제어를 즉시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43869-104">구문</span><span class="sxs-lookup"><span data-stu-id="43869-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="43869-105">문</span><span class="sxs-lookup"><span data-stu-id="43869-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="43869-106">즉시 종료는 `Do` 루프 나타나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="43869-107">다음 문으로 계속 실행 합니다 `Loop` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="43869-108">`Exit Do` 내 에서만 사용할 수는 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="43869-109">사용 하는 경우 내에 중첩 `Do` 루프 `Exit Do` 가장 안쪽의 루프를 끝내 고 다음 더 높은 수준의 중첩 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="43869-110">즉시 종료는 `For` 루프 나타나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="43869-111">다음 문으로 계속 실행 합니다 `Next` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="43869-112">`Exit For` 내 에서만 사용할 수는 `For`... `Next` 또는 `For Each`... `Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="43869-113">사용 하는 경우 내에 중첩 `For` 루프 `Exit For` 가장 안쪽의 루프를 끝내 고 다음 더 높은 수준의 중첩 컨트롤을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="43869-114">즉시 끝내는 `Function` 나타나는 프로시저.</span><span class="sxs-lookup"><span data-stu-id="43869-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="43869-115">문 다음에 호출한 문으로 실행이 계속 되는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="43869-116">`Exit Function` 내 에서만 사용할 수는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="43869-117">반환 값을 지정 하려면 앞에 줄에 함수 이름에 값을 할당할 수는 `Exit Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="43869-118">반환 값을 할당 하 고 하나의 문에서 함수 종료를 대신 사용할 수 있습니다 합니다 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="43869-119">즉시 끝내는 `Property` 나타나는 프로시저.</span><span class="sxs-lookup"><span data-stu-id="43869-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="43869-120">호출한 문으로 실행이 계속 됩니다는 `Property` 프로시저, 즉,을 요청 하거나 설정 속성의 값을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="43869-121">`Exit Property` 속성의 내 에서만 사용할 수 있습니다 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="43869-122">반환 값을 지정 하는 `Get` 프로시저, 함수 이름 앞에 줄에서 값을 할당할 수 있습니다는 `Exit Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="43869-123">반환 값 및 종료를 할당 하는 `Get` 하나의 문에서 프로시저를 대신 사용할 수 있습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="43869-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="43869-124">에 `Set` 프로시저는 `Exit Property` 문과 동일는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="43869-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="43869-125">즉시 끝내는 `Select Case` 나타나는 것을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="43869-126">다음 문으로 계속 실행 합니다 `End Select` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="43869-127">`Exit Select` 내 에서만 사용할 수는 `Select Case` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="43869-128">즉시 끝내는 `Sub` 나타나는 프로시저.</span><span class="sxs-lookup"><span data-stu-id="43869-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="43869-129">문 다음에 호출한 문으로 실행이 계속 되는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="43869-130">`Exit Sub` 내 에서만 사용할 수는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="43869-131">에 `Sub` 프로시저는 `Exit Sub` 문과 동일는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="43869-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="43869-132">즉시 종료 합니다 `Try` 또는 `Catch` 나타나는 것을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="43869-133">실행이 계속 됩니다는 `Finally` 하나, 없는 경우 또는 다음 문으로 차단를 `End Try` 문.</span><span class="sxs-lookup"><span data-stu-id="43869-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="43869-134">`Exit Try` 내 에서만 사용할 수는 `Try` 또는 `Catch` 블록 내부가 아니라는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="43869-135">즉시 종료는 `While` 루프 나타나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="43869-136">다음 문으로 계속 실행 합니다 `End While` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="43869-137">`Exit While` 내 에서만 사용할 수는 `While` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="43869-138">사용 하는 경우 내에 중첩 `While` 루프 `Exit While` 중첩된 수준이 하나 위 루프는 루프에 제어를 전송 위치 `Exit While` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43869-139">설명</span><span class="sxs-lookup"><span data-stu-id="43869-139">Remarks</span></span>  
 <span data-ttu-id="43869-140">혼동 하지 마십시오 `Exit` 문을 사용 하 여 `End` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="43869-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="43869-141">`Exit` 문의 끝을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43869-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43869-142">예제</span><span class="sxs-lookup"><span data-stu-id="43869-142">Example</span></span>  
 <span data-ttu-id="43869-143">루프 조건에서 다음 예제에서는 루프를 중지 때는 `index` 변수가 100을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="43869-144">그러나 `If` 루프에서 문을 사용 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="43869-145">예제</span><span class="sxs-lookup"><span data-stu-id="43869-145">Example</span></span>  
 <span data-ttu-id="43869-146">다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction`를 사용 하 여 `Exit Function` 함수에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="43869-147">예제</span><span class="sxs-lookup"><span data-stu-id="43869-147">Example</span></span>  
 <span data-ttu-id="43869-148">다음 예제에서는 합니다 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md) 반환 값을 할당 하 여 함수를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="43869-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="43869-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="43869-149">See also</span></span>

- [<span data-ttu-id="43869-150">Continue 문</span><span class="sxs-lookup"><span data-stu-id="43869-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="43869-151">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="43869-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="43869-152">End 문</span><span class="sxs-lookup"><span data-stu-id="43869-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="43869-153">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="43869-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="43869-154">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="43869-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="43869-155">Function 문</span><span class="sxs-lookup"><span data-stu-id="43869-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="43869-156">Return 문</span><span class="sxs-lookup"><span data-stu-id="43869-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="43869-157">Stop 문</span><span class="sxs-lookup"><span data-stu-id="43869-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="43869-158">Sub 문</span><span class="sxs-lookup"><span data-stu-id="43869-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="43869-159">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="43869-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
