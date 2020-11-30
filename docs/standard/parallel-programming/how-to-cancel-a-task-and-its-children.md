---
title: '방법: 작업 및 해당 자식 취소'
description: .NET에서 작업 및 해당 자식 항목을 취소하는 방법의 예제를 참조하세요. 예제에서는 취소 가능한 작업 만들기, 작업이 취소되었다는 알림 등 다양한 단계에 대해 설명합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 82a71faf3a2390f5bb36dd896cf865f773f54bd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713225"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="08e09-104">방법: 작업 및 해당 자식 취소</span><span class="sxs-lookup"><span data-stu-id="08e09-104">How to: Cancel a Task and Its Children</span></span>

<span data-ttu-id="08e09-105">이 예제는 다음 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-105">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="08e09-106">취소 가능한 작업을 만들고 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-106">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="08e09-107">사용자 대리자에 그리고 선택적으로 작업 인스턴스에 취소 토큰을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-107">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="08e09-108">사용자 대리자의 취소 요청을 확인하고 이에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-108">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="08e09-109">선택적으로 작업이 취소된 호출 스레드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-109">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="08e09-110">호출 스레드가 작업을 강제로 종료하지 않으며, 취소가 요청되었다는 신호만 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-110">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="08e09-111">작업이 이미 실행 중인 경우 사용자 대리자가 요청을 알리고 적절하게 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-111">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="08e09-112">작업 실행 전에 취소를 요청하면 사용자 대리자가 실행되지 않고 작업 개체가 Canceled 상태로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-112">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08e09-113">예제</span><span class="sxs-lookup"><span data-stu-id="08e09-113">Example</span></span>  

 <span data-ttu-id="08e09-114">이 예제는 취소 요청에 대한 응답으로 <xref:System.Threading.Tasks.Task> 및 해당 자식을 종료하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-114">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="08e09-115">또한 <xref:System.Threading.Tasks.TaskCanceledException>을 throw하여 사용자 대리자가 종료될 때 호출 스레드에서 필요에 따라 <xref:System.Threading.Tasks.Task.Wait%2A> 메서드나 <xref:System.Threading.Tasks.Task.WaitAll%2A> 메서드를 사용하여 작업이 종료될 때까지 대기할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-115">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="08e09-116">이 경우 `try/catch` 블록을 사용하여 호출 스레드에서 예외를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-116">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="08e09-117"><xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스는 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> 및 <xref:System.Threading.CancellationToken?displayProperty=nameWithType> 유형을 기반으로 하는 취소 모델과 완전히 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08e09-117">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="08e09-118">자세한 내용은 [관리되는 스레드의 취소](../threading/cancellation-in-managed-threads.md) 및 [작업 취소](task-cancellation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08e09-118">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e09-119">참조</span><span class="sxs-lookup"><span data-stu-id="08e09-119">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="08e09-120">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="08e09-120">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="08e09-121">연결된 자식 작업 및 분리된 자식 작업</span><span class="sxs-lookup"><span data-stu-id="08e09-121">Attached and Detached Child Tasks</span></span>](attached-and-detached-child-tasks.md)
- [<span data-ttu-id="08e09-122">PLINQ 및 TPL의 람다 식</span><span class="sxs-lookup"><span data-stu-id="08e09-122">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
