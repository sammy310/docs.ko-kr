---
title: On Error 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: 0a5a5261e6b71178adce02a5635c1f91a1469f3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834272"
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="8fdd1-102">On Error 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fdd1-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="8fdd1-103">오류 처리 루틴을 사용 하도록 설정 하 고 프로시저;에서 루틴의 위치를 지정 오류 처리 루틴을 사용 하지 않으려면 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span>  
  
 <span data-ttu-id="8fdd1-104">발생 하는 모든 런타임 오류는 심각한 오류를 처리 하지: 오류 메시지가 표시 되 고 실행이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-104">Without error handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>  
  
 <span data-ttu-id="8fdd1-105">가능한 경우 구조화 되지 않은 예외 처리를 사용 하는 것이 아니라 코드에서 처리 하는 구조화 된 예외를 사용 하는 것이 좋습니다 하며 `On Error` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-105">Whenever possible, we suggest you use structured exception handling in your code, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="8fdd1-106">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-106">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fdd1-107">합니다 `Error` 키워드에도 사용 합니다 [Error 문](../../../visual-basic/language-reference/statements/error-statement.md), 이전 버전과 호환성을 위해 지원 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fdd1-108">구문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-108">Syntax</span></span>  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a><span data-ttu-id="8fdd1-109">요소</span><span class="sxs-lookup"><span data-stu-id="8fdd1-109">Parts</span></span>  
  
|<span data-ttu-id="8fdd1-110">용어</span><span class="sxs-lookup"><span data-stu-id="8fdd1-110">Term</span></span>|<span data-ttu-id="8fdd1-111">정의</span><span class="sxs-lookup"><span data-stu-id="8fdd1-111">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="8fdd1-112">`GoTo` `line`</span><span class="sxs-lookup"><span data-stu-id="8fdd1-112">`GoTo` `line`</span></span>|<span data-ttu-id="8fdd1-113">에 필요한 지정 된 줄에서 시작 하는 오류 처리 루틴을 사용 하면 `line` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-113">Enables the error-handling routine that starts at the line specified in the required `line` argument.</span></span> <span data-ttu-id="8fdd1-114">`line` 인수는 모든 줄 레이블 또는 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-114">The `line` argument is any line label or line number.</span></span> <span data-ttu-id="8fdd1-115">런타임 오류가 발생 하는 경우 오류 처리기 활성화 될 때 지정된 된 줄에 분기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="8fdd1-116">지정된 된 줄에서와 동일한 절차에 있어야 합니다 `On Error` 문 또는 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-116">The specified line must be in the same procedure as the `On Error` statement, or a compile-time error will occur.</span></span>|  
|<span data-ttu-id="8fdd1-117">`GoTo` 0</span><span class="sxs-lookup"><span data-stu-id="8fdd1-117">`GoTo` 0</span></span>|<span data-ttu-id="8fdd1-118">현재 프로시저에서 활성화 된 오류 처리기를 사용 하지 않도록 설정 하 고 다시 설정 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-118">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|  
|<span data-ttu-id="8fdd1-119">`GoTo` -1</span><span class="sxs-lookup"><span data-stu-id="8fdd1-119">`GoTo` -1</span></span>|<span data-ttu-id="8fdd1-120">현재 프로시저에서 사용 가능한 예외를 사용 하지 않도록 설정 하 고 다시 설정 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-120">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|  
|`Resume Next`|<span data-ttu-id="8fdd1-121">런타임 오류가 발생 하는 컨트롤 여기서 오류가 발생 하 고 해당 지점에서 실행이 계속 문 바로 다음 문으로 이동 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-121">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="8fdd1-122">이 양식을 사용 하 여 대신 `On Error GoTo` 개체에 액세스할 때.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-122">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fdd1-123">설명</span><span class="sxs-lookup"><span data-stu-id="8fdd1-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fdd1-124">구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-124">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="8fdd1-125">자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-125">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="8fdd1-126">"enabled" 오류 처리기가으로 켜져 있는 `On Error` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-126">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="8fdd1-127">"활성" 오류 처리기가 오류를 처리 하는 처리기를 사용 하도록 설정된 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-127">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>  
  
 <span data-ttu-id="8fdd1-128">오류 처리기가 활성 상태인 동안 오류가 발생 하는 경우 (오류 발생 간에 및 `Resume`, `Exit Sub`를 `Exit Function`, 또는 `Exit Property` 문), 현재 프로시저의 오류 처리기는 오류를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-128">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="8fdd1-129">호출 하는 프로시저로 제어가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-129">Control returns to the calling procedure.</span></span>  
  
 <span data-ttu-id="8fdd1-130">호출 하는 프로시저에 설정 된 오류 처리기, 오류 처리에 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-130">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="8fdd1-131">오류 처리기를 호출 하는 프로시저의 활성 상태인 경우 제어가 사용 하지만 비활성화 된 오류 처리기를 찾을 때까지 이전 호출 프로시저를 통해 다시 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-131">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="8fdd1-132">이러한 오류 처리기가 있으면 오류가 심각한는 실제로 발생 한 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-132">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>  
  
 <span data-ttu-id="8fdd1-133">오류 처리기 제어를 호출 하는 프로시저를 다시 전달 될 때마다 해당 프로시저는 현재 프로시저가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-133">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="8fdd1-134">현재 프로시저에서 지정 된 지점에서 실행이 재개는 오류가 모든 프로시저에 오류 처리기가 처리 되 면는 `Resume` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-134">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fdd1-135">오류 처리 루틴을 아닙니다를 `Sub` 프로시저 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-135">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="8fdd1-136">이 줄 레이블 또는 줄 번호 표시 된 코드의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-136">It is a section of code marked by a line label or a line number.</span></span>  
  
## <a name="number-property"></a><span data-ttu-id="8fdd1-137">Number 속성</span><span class="sxs-lookup"><span data-stu-id="8fdd1-137">Number Property</span></span>  
 <span data-ttu-id="8fdd1-138">오류 처리 루틴에서 값을 사용 합니다 `Number` 의 속성을 `Err` 오류의 원인을 확인 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-138">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="8fdd1-139">루틴을 테스트 하거나 관련 속성 값을 저장 해야 합니다 `Err` 다른 오류가 발생할 수 있습니다 하거나 오류가 발생할 수 있는 절차 앞 이라고 전에 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-139">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="8fdd1-140">속성 값을 `Err` 개체는 가장 최근의 오류만을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-140">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="8fdd1-141">관련 된 오류 메시지 `Err.Number` 에 포함 된 `Err.Description`합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-141">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="8fdd1-142">Throw 문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-142">Throw Statement</span></span>  
 <span data-ttu-id="8fdd1-143">사용 하 여 발생 하는 오류를 `Err.Raise` 메서드 집합을 `Exception` 의 새로 만든된 인스턴스에 대 한 속성을 <xref:System.Exception> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-143">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="8fdd1-144">파생 된 예외 형식의 예외 발생을 지원 하기 위해는 `Throw` 언어 문이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-144">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="8fdd1-145">이 예외 인스턴스가 throw 되는 단일 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-145">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="8fdd1-146">다음 예제에서는 기존 예외 처리 지원을 사용 하 여 이러한 기능을 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-146">The following example shows how these features can be used with the existing exception handling support:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 <span data-ttu-id="8fdd1-147">`On Error GoTo` 문을 예외 클래스에 관계 없이 모든 오류를 포착 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-147">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>  
  
## <a name="on-error-resume-next"></a><span data-ttu-id="8fdd1-148">On Error Resume 다음</span><span class="sxs-lookup"><span data-stu-id="8fdd1-148">On Error Resume Next</span></span>  
 <span data-ttu-id="8fdd1-149">`On Error Resume Next` 런타임 오류를 발생 시킨 문 바로 다음 문으로 계속 하거나 포함 하는 프로시저에서 호출 바로 다음에 최신 문을 사용 하 여 실행이 넘어갑니다는 `On Error Resume Next` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-149">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="8fdd1-150">이 문은 런타임 오류가 있더라도 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-150">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="8fdd1-151">프로시저 내의 다른 위치로 제어를 전송 하는 것이 아니라 오류 발생 오류 처리 루틴을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-151">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="8fdd1-152">`On Error Resume Next` 문이 비활성화 됩니다 다른 프로시저를 호출 하는 경우 실행 해야 하므로 `On Error Resume Next` 각 문이 인라인 오류 해당 루틴 내에서 처리 하려는 경우 루틴을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-152">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fdd1-153">합니다 `On Error Resume Next` 구문에 더 적합할 수 있습니다 `On Error GoTo` 다른 개체에 액세스 하는 동안 발생 한 오류를 처리 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-153">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="8fdd1-154">검사 `Err` 각 상호 작용 후 개체를 사용 하 여 코드에서 액세스 된 개체에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-154">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="8fdd1-155">확인할 수 있는 개체의 오류 코드에 배치 `Err.Number`, 개체가 원래 오류를 생성 하는 데 뿐만 아니라 (에서 지정 된 개체 `Err.Source`).</span><span class="sxs-lookup"><span data-stu-id="8fdd1-155">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>  
  
## <a name="on-error-goto-0"></a><span data-ttu-id="8fdd1-156">Error GoTo 0 대</span><span class="sxs-lookup"><span data-stu-id="8fdd1-156">On Error GoTo 0</span></span>  
 <span data-ttu-id="8fdd1-157">`On Error GoTo 0` 현재 프로시저의 오류 처리를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-157">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="8fdd1-158">라인 0 프로시저 0 번 줄이 있는 경우에 오류 처리 코드의 시작으로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-158">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="8fdd1-159">없이 `On Error GoTo 0` 문에서 오류 처리기 프로시저 종료 될 때 자동으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-159">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>  
  
## <a name="on-error-goto--1"></a><span data-ttu-id="8fdd1-160">Error GoTo-1에서</span><span class="sxs-lookup"><span data-stu-id="8fdd1-160">On Error GoTo -1</span></span>  
 <span data-ttu-id="8fdd1-161">`On Error GoTo -1` 현재 프로시저에서 예외를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-161">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="8fdd1-162">절차-1 번 줄을 포함 하는 경우에-1 번 줄 오류 처리 코드의 시작으로 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-162">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="8fdd1-163">없이 `On Error GoTo -1` 예외가 문을 프로시저 종료 될 때 자동으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-163">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>  
  
 <span data-ttu-id="8fdd1-164">오류 처리 코드 오류가 발생 하지 않은 경우 실행을 방지 하려면 배치는 `Exit Sub`하십시오 `Exit Function`, 또는 `Exit Property` 문은 다음 조각 처럼 오류 처리 루틴을 바로 앞:</span><span class="sxs-lookup"><span data-stu-id="8fdd1-164">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 <span data-ttu-id="8fdd1-165">여기에서 오류 처리 코드가 다음과 `Exit Sub` 문 앞에 오는 및는 `End Sub` 문을 프로시저 흐름을 구분 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-165">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="8fdd1-166">프로시저에서 아무 곳 이나 오류 처리 코드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-166">You can place error-handling code anywhere in a procedure.</span></span>  
  
## <a name="untrapped-errors"></a><span data-ttu-id="8fdd1-167">포착된 되지 않은 오류</span><span class="sxs-lookup"><span data-stu-id="8fdd1-167">Untrapped Errors</span></span>  
 <span data-ttu-id="8fdd1-168">개체의 오류를 포착 되지 않은 개체는 실행 파일로 실행 중일 때 제어 응용 프로그램에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-168">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="8fdd1-169">개발 환경 내에서 포착된 되지 않은 오류는 적절 한 옵션을 설정 하는 경우에 제어 응용 프로그램에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-169">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="8fdd1-170">옵션을 디버깅 하는 동안 집합,를 설정 하는 방법 및 호스트 클래스를 만들 수 있는지 여부 수에 대 한 호스트 응용 프로그램의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-170">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>  
  
 <span data-ttu-id="8fdd1-171">다른 개체에 액세스 하는 개체를 만드는 경우에 다시 전달 하는 모든 처리 되지 않은 오류를 처리 하려고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-171">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="8fdd1-172">오류 코드를 매핑할 수 없는 경우 `Err.Number` 고유한 오류 및이 전달 하는 중 하나에 개체의 호출자에 게 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-172">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="8fdd1-173">오류 코드를 추가 하 여 오류를 지정 해야 합니다 `VbObjectError` 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-173">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="8fdd1-174">예를 들어 1052는 오류 코드가 다음과 같이 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-174">For example, if your error code is 1052, assign it as follows:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  <span data-ttu-id="8fdd1-175">Windows 동적 연결 라이브러리 (Dll)를 호출 하는 동안 시스템 오류 예외를 발생 하지 않습니다 및 Visual Basic 오류 트래핑을 사용 하 여 잡아낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-175">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="8fdd1-176">성공 또는 실패 (에 따라 API 사양)에 대 한 각 반환 값을 검사 하는 DLL 함수를 호출할 때 오류가 발생 하면 값을 확인 합니다 `Err` 개체의 `LastDLLError` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-176">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fdd1-177">예제</span><span class="sxs-lookup"><span data-stu-id="8fdd1-177">Example</span></span>  
 <span data-ttu-id="8fdd1-178">이 예제에서는 먼저 사용 하 여는 `On Error GoTo` 문을 프로시저 내에서 오류 처리 루틴을의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-178">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="8fdd1-179">예제에서는 0으로 나누려 할 6 오류 번호를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-179">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="8fdd1-180">오류 처리 루틴에서 오류가 처리 되 고 제어 오류를 발생 시킨 명령문에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-180">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="8fdd1-181">`On Error GoTo 0` 문을 오류 잡기를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-181">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="8fdd1-182">그런 다음 `On Error Resume Next` 문을 다음 문으로 생성 된 오류에 대 한 컨텍스트를 특정 알 수 있도록 오류 트래핑을 지연 시키려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-182">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="8fdd1-183">`Err.Clear` 의 선택을 취소 하는 데 사용 되는 `Err` 오류가 처리 되 면 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fdd1-183">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a><span data-ttu-id="8fdd1-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fdd1-184">Requirements</span></span>  
 <span data-ttu-id="8fdd1-185">**네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="8fdd1-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="8fdd1-186">**어셈블리:** Visual Basic 런타임 라이브러리(Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="8fdd1-186">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fdd1-187">참고자료</span><span class="sxs-lookup"><span data-stu-id="8fdd1-187">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [<span data-ttu-id="8fdd1-188">End 문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-188">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="8fdd1-189">Exit 문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-189">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="8fdd1-190">Resume 문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-190">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="8fdd1-191">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="8fdd1-191">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
- [<span data-ttu-id="8fdd1-192">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="8fdd1-192">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
