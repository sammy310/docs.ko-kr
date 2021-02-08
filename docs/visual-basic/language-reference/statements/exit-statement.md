---
description: '자세한 정보: Exit 문 (Visual Basic)'
title: Exit 문
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
ms.openlocfilehash: 54af7fbf908dbad829cf6f08bf442dfe85e35610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769129"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="96723-103">Exit 문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96723-103">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="96723-104">프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음에 오는 문으로 제어를 즉시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-104">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="96723-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="96723-105">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="96723-106">문</span><span class="sxs-lookup"><span data-stu-id="96723-106">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="96723-107">표시 되는 루프를 즉시 종료 `Do` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-107">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="96723-108">문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Loop` .</span><span class="sxs-lookup"><span data-stu-id="96723-108">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="96723-109">`Exit Do` 루프 내 에서만 사용할 수 있습니다 `Do` .</span><span class="sxs-lookup"><span data-stu-id="96723-109">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="96723-110">중첩 된 루프 내에서 사용 되는 경우 `Do` `Exit Do` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-110">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="96723-111">표시 되는 루프를 즉시 종료 `For` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-111">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="96723-112">문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Next` .</span><span class="sxs-lookup"><span data-stu-id="96723-112">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="96723-113">`Exit For` ... `For` `Next` 또는 `For Each` ... `Next` 루프 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96723-113">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="96723-114">중첩 된 루프 내에서 사용 되는 경우 `For` `Exit For` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-114">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="96723-115">표시 되는 프로시저를 즉시 종료 `Function` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-115">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="96723-116">프로시저를 호출한 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="96723-116">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="96723-117">`Exit Function` 프로시저 내 에서만 사용할 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="96723-117">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="96723-118">반환 값을 지정 하기 위해 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다 `Exit Function` .</span><span class="sxs-lookup"><span data-stu-id="96723-118">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="96723-119">반환 값을 할당 하 고 한 문에서 함수를 종료 하려면 [Return 문을](return-statement.md)대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96723-119">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="96723-120">표시 되는 프로시저를 즉시 종료 `Property` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-120">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="96723-121">프로시저를 호출한 문 즉 `Property` , 속성의 값을 요청 하거나 설정 하는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96723-121">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="96723-122">`Exit Property` 속성의 또는 프로시저 내 에서만 사용할 수 `Get` 있습니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="96723-122">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="96723-123">프로시저에서 반환 값을 지정 하려면 `Get` 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다 `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="96723-123">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="96723-124">반환 값을 할당 하 고 `Get` 한 문에서 프로시저를 종료 하려면 문을 대신 사용할 수 있습니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="96723-124">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="96723-125">프로시저에서 `Set` `Exit Property` 문은 문과 동일 합니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="96723-125">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="96723-126">표시 되는 블록을 즉시 종료 `Select Case` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-126">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="96723-127">문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `End Select` .</span><span class="sxs-lookup"><span data-stu-id="96723-127">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="96723-128">`Exit Select` 문 내 에서만 사용할 수 있습니다 `Select Case` .</span><span class="sxs-lookup"><span data-stu-id="96723-128">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="96723-129">표시 되는 프로시저를 즉시 종료 `Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-129">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="96723-130">프로시저를 호출한 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="96723-130">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="96723-131">`Exit Sub` 프로시저 내 에서만 사용할 수 있습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="96723-131">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="96723-132">프로시저에서 `Sub` `Exit Sub` 문은 문과 동일 합니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="96723-132">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="96723-133">`Try`가 표시 되는 또는 블록을 즉시 종료 `Catch` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-133">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="96723-134">블록 (있는 `Finally` 경우) 또는 문 뒤의 문이 있는 경우 실행이 계속 됩니다 `End Try` .</span><span class="sxs-lookup"><span data-stu-id="96723-134">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="96723-135">`Exit Try` 는 `Try` `Catch` 블록 내부가 아니라 또는 블록 내부 에서만 사용할 수 있습니다 `Finally` .</span><span class="sxs-lookup"><span data-stu-id="96723-135">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="96723-136">표시 되는 루프를 즉시 종료 `While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-136">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="96723-137">문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `End While` .</span><span class="sxs-lookup"><span data-stu-id="96723-137">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="96723-138">`Exit While` 루프 내 에서만 사용할 수 있습니다 `While` .</span><span class="sxs-lookup"><span data-stu-id="96723-138">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="96723-139">중첩 된 루프 내에서 사용 되는 경우이 발생 하는 `While` `Exit While` 루프 위에 중첩 된 한 수준으로 제어를 전달 `Exit While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-139">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="96723-140">설명</span><span class="sxs-lookup"><span data-stu-id="96723-140">Remarks</span></span>

<span data-ttu-id="96723-141">문을 문과 혼동 하지 마십시오 `Exit` `End` .</span><span class="sxs-lookup"><span data-stu-id="96723-141">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="96723-142">`Exit` 는 문의 끝을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96723-142">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="96723-143">예제</span><span class="sxs-lookup"><span data-stu-id="96723-143">Example</span></span>

<span data-ttu-id="96723-144">다음 예제에서 루프 조건은 `index` 변수가 100 보다 큰 경우 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-144">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="96723-145">`If`그러나 루프의 문은 `Exit Do` 인덱스 변수가 10 보다 클 경우 문이 루프를 중지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-145">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="96723-146">예제</span><span class="sxs-lookup"><span data-stu-id="96723-146">Example</span></span>

<span data-ttu-id="96723-147">다음 예에서는 함수 이름에 반환 값을 할당 한 `myFunction` 다음를 사용 하 여 `Exit Function` 함수에서를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-147">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="96723-148">예제</span><span class="sxs-lookup"><span data-stu-id="96723-148">Example</span></span>

<span data-ttu-id="96723-149">다음 예에서는 [Return 문을](return-statement.md) 사용 하 여 반환 값을 할당 하 고 함수를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="96723-149">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="96723-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96723-150">See also</span></span>

- [<span data-ttu-id="96723-151">Continue 문</span><span class="sxs-lookup"><span data-stu-id="96723-151">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="96723-152">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="96723-152">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="96723-153">End 문</span><span class="sxs-lookup"><span data-stu-id="96723-153">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="96723-154">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="96723-154">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="96723-155">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="96723-155">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="96723-156">Function 문</span><span class="sxs-lookup"><span data-stu-id="96723-156">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="96723-157">Return 문</span><span class="sxs-lookup"><span data-stu-id="96723-157">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="96723-158">Stop 문</span><span class="sxs-lookup"><span data-stu-id="96723-158">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="96723-159">Sub 문</span><span class="sxs-lookup"><span data-stu-id="96723-159">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="96723-160">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="96723-160">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
