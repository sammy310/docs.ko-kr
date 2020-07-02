---
title: 이벤트 기반 비동기 패턴(EAP)
description: 구현, 모범 사례, EAP 클라이언트 구현 등과 같은 .NET의 EAP(이벤트 기반 비동기 패턴)에 대한 문서의 링크를 참조하세요.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768874"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="f696d-103">이벤트 기반 비동기 패턴(EAP)</span><span class="sxs-lookup"><span data-stu-id="f696d-103">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="f696d-104">비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-104">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="f696d-105">이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 한 가지 방법을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-105">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f696d-106">.NET Framework 4부터는 작업 병렬 라이브러리에서 비동기 및 병렬 프로그래밍을 위한 새로운 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-106">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="f696d-107">자세한 내용은 [TPL(작업 병렬 라이브러리)](../parallel-programming/task-parallel-library-tpl.md) 및 [TAP(작업 기반 비동기 패턴)](task-based-asynchronous-pattern-tap.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f696d-107">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f696d-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f696d-108">In This Section</span></span>

 [<span data-ttu-id="f696d-109">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="f696d-109">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="f696d-110">이벤트 기반 비동기 패턴이 다중 스레드 디자인에 본질적으로 존재하는 복잡한 여러 가지 문제를 숨기면서 다중 스레드 애플리케이션의 장점을 이용할 수 있게 해주는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-110">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="f696d-111">이벤트 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="f696d-111">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-112">비동기 기능을 포함하는 클래스를 패키징하는 표준화된 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-112">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="f696d-113">최선의 이벤트 기반 비동기 패턴 구현 방법</span><span class="sxs-lookup"><span data-stu-id="f696d-113">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-114">이벤트 기반 비동기 패턴에 따라 비동기 기능을 노출하기 위한 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-114">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="f696d-115">이벤트 기반 비동기 패턴 구현 시기 결정</span><span class="sxs-lookup"><span data-stu-id="f696d-115">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-116">[APM(비동기 프로그래밍 모델)](asynchronous-programming-model-apm.md)에서 나타내는 <xref:System.IAsyncResult> 패턴 대신 이벤트 기반 비동기 패턴을 구현하도록 선택해야 하는 경우를 결정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-116">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="f696d-117">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="f696d-117">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-118">이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-118">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="f696d-119">구성 요소가 모든 애플리케이션 모델에서 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-119">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="f696d-120">방법: 이벤트 기반 비동기 패턴의 클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="f696d-120">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-121">이벤트 기반 비동기 패턴을 구현하는 구성 요소를 사용하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-121">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="f696d-122">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="f696d-122">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="f696d-123">이벤트 기반 비동기 패턴을 지원하는 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-123">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f696d-124">참고</span><span class="sxs-lookup"><span data-stu-id="f696d-124">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="f696d-125"><xref:System.ComponentModel.AsyncOperation> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-125">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="f696d-126"><xref:System.ComponentModel.AsyncOperationManager> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-126">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f696d-127"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-127">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f696d-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f696d-128">Related Sections</span></span>

 [<span data-ttu-id="f696d-129">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="f696d-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="f696d-130">비동기 및 병렬 작업용 프로그래밍 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-130">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="f696d-131">스레딩</span><span class="sxs-lookup"><span data-stu-id="f696d-131">Threading</span></span>](../threading/index.md)  
 <span data-ttu-id="f696d-132">.NET의 다중 스레딩 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f696d-132">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f696d-133">참조</span><span class="sxs-lookup"><span data-stu-id="f696d-133">See also</span></span>

- [<span data-ttu-id="f696d-134">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="f696d-134">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="f696d-135">이벤트</span><span class="sxs-lookup"><span data-stu-id="f696d-135">Events</span></span>](../events/index.md)
- [<span data-ttu-id="f696d-136">비동기 프로그래밍 패턴</span><span class="sxs-lookup"><span data-stu-id="f696d-136">Asynchronous Programming Design Patterns</span></span>](index.md)
