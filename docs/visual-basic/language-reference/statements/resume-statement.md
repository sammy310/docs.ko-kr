---
title: Resume 문
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: db9d47798d087d60f4318b06fe3291fb895e6618
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871867"
---
# <a name="resume-statement"></a><span data-ttu-id="aaef7-102">Resume 문</span><span class="sxs-lookup"><span data-stu-id="aaef7-102">Resume Statement</span></span>

<span data-ttu-id="aaef7-103">오류 처리 루틴이 완료 된 후 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="aaef7-104">구조화 되지 않은 예외 처리 및 및 문을 사용 하는 대신 가능한 경우 코드에서 구조적 예외 처리를 사용 하는 것이 좋습니다 `On Error` `Resume` .</span><span class="sxs-lookup"><span data-stu-id="aaef7-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="aaef7-105">자세한 내용은 [Try...Catch...Finally 문](try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaef7-105">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaef7-106">구문</span><span class="sxs-lookup"><span data-stu-id="aaef7-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="aaef7-107">부분</span><span class="sxs-lookup"><span data-stu-id="aaef7-107">Parts</span></span>  

 `Resume`  
 <span data-ttu-id="aaef7-108">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-108">Required.</span></span> <span data-ttu-id="aaef7-109">오류 처리기와 동일한 프로시저에서 오류가 발생 한 경우 오류를 발생 시킨 문으로 실행이 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="aaef7-110">호출 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출한 문에서 실행이 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="aaef7-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-111">Optional.</span></span> <span data-ttu-id="aaef7-112">오류 처리기와 동일한 프로시저에서 오류가 발생 한 경우 오류가 발생 한 문 바로 다음에 오는 문으로 실행이 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="aaef7-113">호출 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴 (문)을 포함 하는 프로시저에서 마지막으로 호출한 문 바로 다음 문으로 실행이 다시 시작 `On Error Resume Next` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="aaef7-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-114">Optional.</span></span> <span data-ttu-id="aaef7-115">필수 인수에 지정 된 줄에서 실행이 다시 시작 `line` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="aaef7-116">`line`인수는 줄 레이블 또는 줄 번호 이며 오류 처리기와 같은 프로시저에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaef7-117">설명</span><span class="sxs-lookup"><span data-stu-id="aaef7-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aaef7-118">구조화 되지 않은 예외 처리 및 및 문을 사용 하는 대신 가능한 경우 코드에서 구조적 예외 처리를 사용 하는 것이 좋습니다 `On Error` `Resume` .</span><span class="sxs-lookup"><span data-stu-id="aaef7-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="aaef7-119">자세한 내용은 [Try...Catch...Finally 문](try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaef7-119">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="aaef7-120">`Resume`오류 처리 루틴이 아닌 다른 위치에서 문을 사용 하는 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="aaef7-121">문은 `Resume` 문을 포함 하는 프로시저에서 사용할 수 없습니다 `Try...Catch...Finally` .</span><span class="sxs-lookup"><span data-stu-id="aaef7-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaef7-122">예제</span><span class="sxs-lookup"><span data-stu-id="aaef7-122">Example</span></span>  

 <span data-ttu-id="aaef7-123">이 예에서는 문을 사용 하 여 `Resume` 프로시저에서 오류 처리를 종료 한 다음 오류를 발생 시킨 문으로 실행을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaef7-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="aaef7-124">문 사용을 보여 주기 위해 55 오류 번호가 생성 됩니다 `Resume` .</span><span class="sxs-lookup"><span data-stu-id="aaef7-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="aaef7-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aaef7-125">Requirements</span></span>  

 <span data-ttu-id="aaef7-126">**네임 스페이스:** [microsoft.visualbasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="aaef7-126">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="aaef7-127">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="aaef7-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaef7-128">참조</span><span class="sxs-lookup"><span data-stu-id="aaef7-128">See also</span></span>

- [<span data-ttu-id="aaef7-129">Try...Catch...Finally 명령문</span><span class="sxs-lookup"><span data-stu-id="aaef7-129">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="aaef7-130">Error 문</span><span class="sxs-lookup"><span data-stu-id="aaef7-130">Error Statement</span></span>](error-statement.md)
- [<span data-ttu-id="aaef7-131">On Error 문</span><span class="sxs-lookup"><span data-stu-id="aaef7-131">On Error Statement</span></span>](on-error-statement.md)
