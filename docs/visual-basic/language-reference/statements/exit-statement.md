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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956939"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="2c40f-102">Exit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c40f-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="2c40f-103">프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음에 오는 문으로 제어를 즉시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c40f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c40f-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="2c40f-105">문</span><span class="sxs-lookup"><span data-stu-id="2c40f-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="2c40f-106">이 표시 되는 `Do` 루프가 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="2c40f-107">@No__t-0 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="2c40f-108">`Exit Do`은 `Do` 루프 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="2c40f-109">중첩 된 `Do` 루프 내에서 사용 하는 경우 `Exit Do`은 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="2c40f-110">이 표시 되는 `For` 루프가 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="2c40f-111">@No__t-0 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="2c40f-112">`For` @no__t `Next` 또는 `For Each` ... @no__t 루프 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="2c40f-113">중첩 된 `For` 루프 내에서 사용 하는 경우 `Exit For`은 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="2c40f-114">는 표시 되는 `Function` 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="2c40f-115">@No__t-0 프로시저를 호출한 문 뒤에 오는 문에서 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="2c40f-116">`Exit Function`은 `Function` 프로시저 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="2c40f-117">반환 값을 지정 하려면 `Exit Function` 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="2c40f-118">반환 값을 할당 하 고 한 문에서 함수를 종료 하려면 [Return 문을](return-statement.md)대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="2c40f-119">는 표시 되는 `Property` 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="2c40f-120">@No__t-0 프로시저를 호출한 문 즉, 속성의 값을 요청 하거나 설정 하는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="2c40f-121">`Exit Property`은 속성의 `Get` 또는 `Set` 프로시저 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="2c40f-122">@No__t-0 프로시저에서 반환 값을 지정 하려면 `Exit Property` 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="2c40f-123">반환 값을 할당 하 고 한 문에서 `Get` 프로시저를 종료 하려면 `Return` 문을 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="2c40f-124">@No__t-0 프로시저에서 `Exit Property` 문은 `Return` 문과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="2c40f-125">는 표시 되는 `Select Case` 블록을 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="2c40f-126">@No__t-0 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="2c40f-127">`Exit Select`은 `Select Case` 문 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="2c40f-128">는 표시 되는 `Sub` 프로시저를 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="2c40f-129">@No__t-0 프로시저를 호출한 문 뒤에 오는 문에서 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="2c40f-130">`Exit Sub`은 `Sub` 프로시저 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="2c40f-131">@No__t-0 프로시저에서 `Exit Sub` 문은 `Return` 문과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="2c40f-132">@No__t-0 또는 `Catch` 블록이 표시 되는 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="2c40f-133">@No__t-0 블록 (있는 경우)을 사용 하 여 실행을 계속 하거나, `End Try` 문 뒤에 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="2c40f-134">`Exit Try`은 `Finally` 블록 내부가 아닌 `Try` 또는 `Catch` 블록 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="2c40f-135">이 표시 되는 `While` 루프가 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="2c40f-136">@No__t-0 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="2c40f-137">`Exit While`은 `While` 루프 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="2c40f-138">중첩 된 `While` 루프 내에서 사용 되는 경우 `Exit While`은 `Exit While`가 발생 하는 루프 위에 중첩 된 한 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c40f-139">설명</span><span class="sxs-lookup"><span data-stu-id="2c40f-139">Remarks</span></span>

<span data-ttu-id="2c40f-140">@No__t-0 문을 `End` 문과 혼동 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2c40f-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="2c40f-141">`Exit`은 문의 끝을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="2c40f-142">예제</span><span class="sxs-lookup"><span data-stu-id="2c40f-142">Example</span></span>

<span data-ttu-id="2c40f-143">다음 예제에서는 `index` 변수가 100 보다 큰 경우 루프 조건이 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="2c40f-144">그러나 루프의 `If` 문은 인덱스 변수가 10 보다 클 때 `Exit Do` 문이 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="2c40f-145">예제</span><span class="sxs-lookup"><span data-stu-id="2c40f-145">Example</span></span>

<span data-ttu-id="2c40f-146">다음 예에서는-0 @no__t 함수 이름에 반환 값을 할당 한 다음 `Exit Function`을 사용 하 여 함수에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="2c40f-147">예제</span><span class="sxs-lookup"><span data-stu-id="2c40f-147">Example</span></span>

<span data-ttu-id="2c40f-148">다음 예에서는 [Return 문을](return-statement.md) 사용 하 여 반환 값을 할당 하 고 함수를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c40f-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="2c40f-149">참조</span><span class="sxs-lookup"><span data-stu-id="2c40f-149">See also</span></span>

- [<span data-ttu-id="2c40f-150">Continue 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="2c40f-151">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="2c40f-152">End 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="2c40f-153">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="2c40f-154">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="2c40f-155">Function 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="2c40f-156">Return 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="2c40f-157">Stop 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="2c40f-158">Sub 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="2c40f-159">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="2c40f-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
