---
title: AsyncCallback 대리자 및 상태 개체 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
ms.openlocfilehash: c7bd0a7606b5f93289cf39d33794457265e7e453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73094601"
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="ecf80-102">AsyncCallback 대리자 및 상태 개체 사용</span><span class="sxs-lookup"><span data-stu-id="ecf80-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="ecf80-103"><xref:System.AsyncCallback> 대리자를 사용하여 별도의 스레드에서 비동기 작업의 결과를 처리할 때 상태 개체를 사용하여 콜백 간에 정보를 전달하고 최종 결과를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="ecf80-104">이 항목에서는 [AsyncCallback 대리자를 사용하여 비동기 작업 종료](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)의 예를 확장하여 연습하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecf80-105">예제</span><span class="sxs-lookup"><span data-stu-id="ecf80-105">Example</span></span>  
 <span data-ttu-id="ecf80-106">다음 코드 예제는 <xref:System.Net.Dns> 클래스에서 비동기 메서드를 사용하여 사용자가 지정한 컴퓨터의 DNS(Domain Name System) 정보를 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="ecf80-107">이 예제는 상태 정보를 저장하는 `HostRequest` 클래스를 정의하고 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="ecf80-108">사용자가 입력한 각 컴퓨터 이름에 대해 `HostRequest` 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="ecf80-109">이 개체는 <xref:System.Net.Dns.BeginGetHostByName%2A> 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="ecf80-110">요청이 완료될 때마다 `ProcessDnsInformation` 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="ecf80-111">`HostRequest` 개체는 <xref:System.IAsyncResult.AsyncState%2A> 속성을 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="ecf80-112">`ProcessDnsInformation` 메서드는 `HostRequest` 개체를 사용하여 요청에서 반환한 <xref:System.Net.IPHostEntry> 또는 요청에서 throw한 <xref:System.Net.Sockets.SocketException>을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="ecf80-113">모든 요청이 완료되면 애플리케이션은 `HostRequest` 개체에 대해 반복되며 DNS 정보 또는 <xref:System.Net.Sockets.SocketException> 오류 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf80-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ecf80-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecf80-114">See also</span></span>

- [<span data-ttu-id="ecf80-115">이벤트 기반 비동기 패턴(EAP)</span><span class="sxs-lookup"><span data-stu-id="ecf80-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="ecf80-116">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="ecf80-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="ecf80-117">AsyncCallback 대리자를 사용하여 비동기 작업 종료</span><span class="sxs-lookup"><span data-stu-id="ecf80-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
