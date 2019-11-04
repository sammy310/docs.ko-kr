---
title: IAsyncResult를 사용하는 비동기 메서드 호출
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 2a9ce8bc2d2edd09ef79c060b9bb173d4d054d02
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121308"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="64ef1-102">IAsyncResult를 사용하는 비동기 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="64ef1-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="64ef1-103">.NET Framework 및 타사 클래스 라이브러리의 유형은 주 애플리케이션 스레드가 아닌 다른 스레드에서 비동기 작업을 수행하는 동안 애플리케이션이 계속 실행할 수 있도록 하는 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64ef1-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="64ef1-104">다음 섹션에서는 <xref:System.IAsyncResult> 디자인 패턴을 사용하는 비동기 메서드를 호출할 수 있는 다양한 방법을 보여주는 코드 예제를 설명하고 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64ef1-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="64ef1-105">[비동기 작업을 종료하여 애플리케이션 실행 차단](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="64ef1-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="64ef1-106">[AsyncWaitHandle을 사용하는 애플리케이션 실행 차단](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="64ef1-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="64ef1-107">[비동기 작업의 상태에 대한 폴링](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="64ef1-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="64ef1-108">[AsyncCallback 대리자를 사용하여 비동기 작업 종료](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="64ef1-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ef1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64ef1-109">See also</span></span>

- [<span data-ttu-id="64ef1-110">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="64ef1-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="64ef1-111">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="64ef1-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
