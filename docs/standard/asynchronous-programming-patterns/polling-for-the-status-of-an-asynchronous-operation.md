---
title: 비동기 작업의 상태에 대한 폴링
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: c73ee50c67034feed07a4869deb0a32342bb45e5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888739"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="6db48-102">비동기 작업의 상태에 대한 폴링</span><span class="sxs-lookup"><span data-stu-id="6db48-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="6db48-103">비동기 작업의 결과를 기다리는 동안 다른 작업을 수행할 수 있는 애플리케이션은 작업이 완료될 때까지 차단되면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="6db48-104">다음 옵션 중 하나를 사용하여 비동기 작업이 완료될 때까지 대기하는 동안 명령을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="6db48-105">비동기 작업의 **Begin**_OperationName_ 메서드에서 반환된 <xref:System.IAsyncResult>의 <xref:System.IAsyncResult.IsCompleted%2A> 속성을 사용하여 작업이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="6db48-106">이 방법을 폴링이라고 하고 이 항목에서 이 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="6db48-107"><xref:System.AsyncCallback> 대리자를 사용하여 비동기 작업 결과를 별도의 스레드에서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="6db48-108">이 방법을 설명하는 예제는 [AsyncCallback 대리자를 사용하여 비동기 작업 종료](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6db48-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db48-109">예제</span><span class="sxs-lookup"><span data-stu-id="6db48-109">Example</span></span>  
 <span data-ttu-id="6db48-110">다음 코드 예제는 <xref:System.Net.Dns> 클래스에서 비동기 메서드를 사용하여 사용자가 지정한 컴퓨터의 Domain Name System 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="6db48-111">이 예제에서는 비동기 작업을 시작한 다음, 작업이 완료될 때까지 콘솔에서 마침표(“.”)를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="6db48-112">이 방법을 사용할 경우 이러한 인수가 필요하지 않기 때문에 <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> 및 <xref:System.Object> 매개 변수에 대해 **null** (Visual Basic의 **Nothing** )이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6db48-112">Note that **null** ( **Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6db48-113">참조</span><span class="sxs-lookup"><span data-stu-id="6db48-113">See also</span></span>

- [<span data-ttu-id="6db48-114">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="6db48-114">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="6db48-115">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="6db48-115">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
