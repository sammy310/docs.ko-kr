---
title: 다른 비동기 패턴 및 형식과의 Interop
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous design patterns, .NET
- TAP, .NET support for
- Task-based Asynchronous Pattern, .NET support for
- .NET, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: 5ad49c70aaa69d8a4f830851b80b6a4839388b0f
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888752"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="9bcf7-102">다른 비동기 패턴 및 형식과의 Interop</span><span class="sxs-lookup"><span data-stu-id="9bcf7-102">Interop with Other Asynchronous Patterns and Types</span></span>

<span data-ttu-id="9bcf7-103">.NET에서 비동기 패턴의 간단한 기록:</span><span class="sxs-lookup"><span data-stu-id="9bcf7-103">A brief history of asynchronous patterns in .NET:</span></span>

- <span data-ttu-id="9bcf7-104">.NET Framework 1.0에서는 [APM(비동기 프로그래밍 모델)](asynchronous-programming-model-apm.md) 또는 `Begin/End` 패턴이라고도 하는 <xref:System.IAsyncResult> 패턴이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-104">.NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>
- <span data-ttu-id="9bcf7-105">.NET Framework 2.0에서는 [EAP(이벤트 기반 비동기 패턴)](event-based-asynchronous-pattern-eap.md)가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-105">.NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>
- <span data-ttu-id="9bcf7-106">.NET Framework 4에서는 APM 및 EAP를 둘 다 대체하고 이전 패턴에서 마이그레이션 루틴을 쉽게 빌드하는 기능을 제공하는 [TAP(작업 기반 비동기 패턴)](task-based-asynchronous-pattern-tap.md)가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-106">.NET Framework 4 introduced the [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md), which supersedes both APM and EAP and provides the ability to easily build migration routines from the earlier patterns.</span></span>
  
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="9bcf7-107">작업 및 APM(비동기 프로그래밍 모델)</span><span class="sxs-lookup"><span data-stu-id="9bcf7-107">Tasks and the Asynchronous Programming Model (APM)</span></span>

### <a name="from-apm-to-tap"></a><span data-ttu-id="9bcf7-108">APM에서 TAP로</span><span class="sxs-lookup"><span data-stu-id="9bcf7-108">From APM to TAP</span></span>  
 <span data-ttu-id="9bcf7-109">[APM(비동기 프로그래밍 모델)](asynchronous-programming-model-apm.md) 패턴은 구조적이므로 APM 구현을 TAP 구현으로 공개하는 래퍼를 쉽게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-109">Because the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) pattern is structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="9bcf7-110">.NET Framework 4 이상 버전에는 이 변환을 제공하는 도우미 루틴이 <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> 메서드 오버로드의 형식으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-110">.NET Framework 4 and later versions include helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="9bcf7-111">동기 <xref:System.IO.Stream> 메서드에 해당하는 APM 항목을 나타내는 <xref:System.IO.Stream.BeginRead%2A> 클래스와 해당 <xref:System.IO.Stream.EndRead%2A> 및 <xref:System.IO.Stream.Read%2A> 메서드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-111">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="9bcf7-112"><xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> 메서드를 사용하여 다음과 같이 이 작업에 대한 TAP 래퍼를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-112">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="9bcf7-113">구현은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-113">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
### <a name="from-tap-to-apm"></a><span data-ttu-id="9bcf7-114">TAP에서 APM으로</span><span class="sxs-lookup"><span data-stu-id="9bcf7-114">From TAP to APM</span></span>  
 <span data-ttu-id="9bcf7-115">기존 인프라에 APM 패턴이 필요한 경우 TAP 구현을 가져와 APM 구현이 필요한 곳에서 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-115">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="9bcf7-116">작업이 구성되고 <xref:System.Threading.Tasks.Task> 클래스가 <xref:System.IAsyncResult>를 구현하기 때문에 간단한 도우미 함수를 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-116">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="9bcf7-117">다음 코드에서는 <xref:System.Threading.Tasks.Task%601> 클래스 확장을 사용하지만 제네릭이 아닌 작업에 대해 거의 동일한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-117">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="9bcf7-118">이제 다음 TAP 구현이 있는 경우를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-118">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="9bcf7-119">다음 APM 구현을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-119">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="9bcf7-120">다음 예제에서는 APM으로 마이그레이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-120">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="9bcf7-121">작업 및 EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="9bcf7-121">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="9bcf7-122">EAP 패턴에는 APM 패턴보다 더 많은 변형과 더 적은 구조가 있기 때문에 [이벤트 기반 비동기 패턴(EAP)](event-based-asynchronous-pattern-eap.md) 구현 래핑이 APM 패턴 래핑보다 훨씬 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-122">Wrapping an [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="9bcf7-123">이를 보여 주기 위해 다음 코드에서는 `DownloadStringAsync` 메서드를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-123">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="9bcf7-124">`DownloadStringAsync` 는 URI를 수락하고 진행 중인 여러 통계를 보고하기 위해 다운로드하는 동안 `DownloadProgressChanged` 이벤트를 발생시키며 완료되면 `DownloadStringCompleted` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-124">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="9bcf7-125">최종 결과는 지정된 URI에 있는 페이지의 내용이 포함된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-125">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="9bcf7-126">작업 및 대기 핸들</span><span class="sxs-lookup"><span data-stu-id="9bcf7-126">Tasks and Wait Handles</span></span>  
  
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="9bcf7-127">대기 핸들에서 TAP로</span><span class="sxs-lookup"><span data-stu-id="9bcf7-127">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="9bcf7-128">대기 핸들은 비동기 패턴을 구현하지 않지만 대기 핸들이 설정된 경우 고급 개발자는 <xref:System.Threading.WaitHandle> 클래스 및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 비동기 알림에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-128">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="9bcf7-129"><xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 메서드를 래핑하여 대기 핸들의 동기 대기에 대해 작업 기반 대체 항목을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-129">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="9bcf7-130">이 메서드를 통해 비동기 메서드에서 기존 <xref:System.Threading.WaitHandle> 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-130">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="9bcf7-131">예를 들어 특정 시간에 실행되는 비동기 작업 수를 제한하려는 경우 세마포( <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> 개체)를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-131">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="9bcf7-132">세마포 개수를 *N* 으로 초기화하고, 작업을 수행하려는 시간 동안 세마포에서 대기한 다음, 작업이 완료되면 세마포를 해제하여 동시에 실행되는 작업 수를 *N* 개로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-132">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore's count to *N* , waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you're done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="9bcf7-133">대기 핸들에 의존하지 않고 완전히 작업으로 작동하는 비동기 세마포를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-133">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="9bcf7-134">이렇게 하려면 [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) 에 설명된 <xref:System.Threading.Tasks.Task>이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-134">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="9bcf7-135">TAP에서 대기 핸들로</span><span class="sxs-lookup"><span data-stu-id="9bcf7-135">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="9bcf7-136">앞에서 설명한 대로 <xref:System.Threading.Tasks.Task> 클래스는 <xref:System.IAsyncResult>를 구현하고, 해당 구현에서 <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> 가 완료될 때 설정되는 대기 핸들을 반환하는 <xref:System.Threading.Tasks.Task> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-136">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="9bcf7-137">다음과 같이 <xref:System.Threading.WaitHandle> 에 대한 <xref:System.Threading.Tasks.Task> 을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcf7-137">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="9bcf7-138">참조</span><span class="sxs-lookup"><span data-stu-id="9bcf7-138">See also</span></span>

- [<span data-ttu-id="9bcf7-139">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="9bcf7-139">Task-based Asynchronous Pattern (TAP)</span></span>](task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="9bcf7-140">작업 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="9bcf7-140">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="9bcf7-141">작업 기반 비동기 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="9bcf7-141">Consuming the Task-based Asynchronous Pattern</span></span>](consuming-the-task-based-asynchronous-pattern.md)
