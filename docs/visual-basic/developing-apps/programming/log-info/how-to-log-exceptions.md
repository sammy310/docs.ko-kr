---
description: '자세한 정보: 방법: Visual Basic에서 예외 기록'
title: '방법: 예외 기록'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: a4155de4e73c632edf071256976161cfdbffba77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775216"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="3f6f1-103">방법: Visual Basic에서 예외 기록</span><span class="sxs-lookup"><span data-stu-id="3f6f1-103">How to: Log Exceptions in Visual Basic</span></span>

<span data-ttu-id="3f6f1-104">`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에서 발생하는 예외에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-104">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="3f6f1-105">이 예제에서는 `My.Application.Log.WriteException` 메서드를 사용하여 명시적으로 catch하는 예외 및 처리되지 않은 예외를 기록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-105">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="3f6f1-106">추적 정보를 기록하려면 `My.Application.Log.WriteEntry` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-106">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="3f6f1-107">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-107">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="3f6f1-108">처리된 예외를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="3f6f1-108">To log a handled exception</span></span>  
  
1. <span data-ttu-id="3f6f1-109">예외 정보를 생성하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-109">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. <span data-ttu-id="3f6f1-110">`Try...Catch` 블록을 사용하여 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. <span data-ttu-id="3f6f1-111">예외를 생성할 수 있는 코드를 `Try` 블록에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-111">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="3f6f1-112">`Dim` 및 `MsgBox` 줄의 주석 처리를 제거하여 <xref:System.NullReferenceException> 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-112">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. <span data-ttu-id="3f6f1-113">`Catch` 블록에서 `My.Application.Log.WriteException` 메서드를 사용하여 예외 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-113">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     <span data-ttu-id="3f6f1-114">다음 예제에서는 처리된 예외를 기록하기 위한 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-114">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="3f6f1-115">처리되지 않은 예외를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="3f6f1-115">To log an unhandled exception</span></span>  
  
1. <span data-ttu-id="3f6f1-116">**솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3f6f1-117">**프로젝트** 메뉴에서 **속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-117">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="3f6f1-118">**애플리케이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="3f6f1-119">**애플리케이션 이벤트 보기** 단추를 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-119">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="3f6f1-120">그러면 ApplicationEvents.vb 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-120">This opens the ApplicationEvents.vb file.</span></span>  
  
4. <span data-ttu-id="3f6f1-121">코드 편집기에서 ApplicationEvents.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-121">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="3f6f1-122">**일반** 메뉴에서 **MyApplication 이벤트** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-122">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5. <span data-ttu-id="3f6f1-123">**선언** 메뉴에서 **UnhandledException** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-123">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="3f6f1-124">주 애플리케이션이 실행되기 전에 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-124">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6. <span data-ttu-id="3f6f1-125">`My.Application.Log.WriteException` 이벤트 처리기에 `UnhandledException` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-125">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     <span data-ttu-id="3f6f1-126">다음 예제에서는 처리되지 않은 예외를 기록하기 위한 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f6f1-126">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="3f6f1-127">참조</span><span class="sxs-lookup"><span data-stu-id="3f6f1-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="3f6f1-128">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="3f6f1-128">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="3f6f1-129">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="3f6f1-129">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="3f6f1-130">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="3f6f1-130">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="3f6f1-131">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="3f6f1-131">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
