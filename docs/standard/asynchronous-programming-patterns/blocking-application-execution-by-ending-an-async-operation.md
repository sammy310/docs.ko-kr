---
title: 비동기 작업을 종료하여 애플리케이션 실행 차단
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121324"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="cbab7-102">비동기 작업을 종료하여 애플리케이션 실행 차단</span><span class="sxs-lookup"><span data-stu-id="cbab7-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="cbab7-103">비동기 작업의 결과를 기다리는 동안 다른 작업을 계속 수행할 수 없는 애플리케이션은 작업이 완료될 때까지 차단되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="cbab7-104">다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 대기하는 동안 애플리케이션의 기본 스레드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="cbab7-105">비동기 작업 **End**_OperationName_ 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="cbab7-106">이 항목에서 이 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="cbab7-107">비동기 작업의 <xref:System.IAsyncResult.AsyncWaitHandle%2A>Begin<xref:System.IAsyncResult>**OperationName** 메서드에 의해 반환된 _의_  속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="cbab7-108">이 방법을 설명하는 예제는 [AsyncWaitHandle을 사용하는 애플리케이션 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbab7-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="cbab7-109">**End**_OperationName_ 메서드를 사용하여 비동기 작업이 완료될 때까지 차단하는 애플리케이션은 일반적으로 **Begin**_OperationName_ 메서드를 호출하고, 작업 결과 없이 완료할 수 있는 작업을 수행한 다음, **End**_OperationName_을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbab7-110">예제</span><span class="sxs-lookup"><span data-stu-id="cbab7-110">Example</span></span>  
 <span data-ttu-id="cbab7-111">다음 코드 예제는 <xref:System.Net.Dns> 클래스에서 비동기 메서드를 사용하여 사용자가 지정한 컴퓨터의 Domain Name System 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="cbab7-112">이 방법을 사용할 경우 이러한 인수가 필요하지 않기 때문에 `null``Nothing` 및 <xref:System.Net.Dns.BeginGetHostByName%2A> 매개 변수에 대해 `requestCallback`(Visual Basic의 `stateObject`)이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbab7-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cbab7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbab7-113">See also</span></span>

- [<span data-ttu-id="cbab7-114">이벤트 기반 비동기 패턴(EAP)</span><span class="sxs-lookup"><span data-stu-id="cbab7-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="cbab7-115">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="cbab7-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
