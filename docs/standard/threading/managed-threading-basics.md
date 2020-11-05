---
title: 관리되는 스레딩 기본 사항
description: 예외, 데이터 동기화, 포그라운드 및 백그라운드 스레드, 로컬 스토리지 등의 항목을 다루는 다른 관리형 스레딩 문서에 대한 링크를 참조하세요.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: ca3073cca9887265b4bacb4f8dfeb01203f82621
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189136"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="afb67-103">관리형 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="afb67-103">Managed threading basics</span></span>

<span data-ttu-id="afb67-104">이 섹션의 처음 5개 문서는 관리형 스레딩을 사용할 시기를 결정하는 데 도움을 주고 몇 가지 기본 기능을 설명하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-104">The first five articles of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="afb67-105">추가 기능을 제공하는 클래스에 대한 내용은 [스레딩 개체 및 기능](threading-objects-and-features.md) 및 [동기화 기본 형식 개요](overview-of-synchronization-primitives.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afb67-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="afb67-106">나머지 문서에서는 Windows 운영 체제와 관리형 스레딩의 상호 작용을 비롯한 고급 주제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-106">The remaining articles in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afb67-107">.NET Framework 4부터 작업 병렬 라이브러리 및 PLINQ는 다중 스레드 프로그램에서 작업 및 데이터 병렬 처리를 위한 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-107">Starting with .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="afb67-108">자세한 내용은 [병렬 프로그래밍](../parallel-programming/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="afb67-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afb67-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="afb67-109">In this section</span></span>

 [<span data-ttu-id="afb67-110">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="afb67-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="afb67-111">다중 스레드의 장단점에 대해 설명하고 스레드를 만들거나 스레드 풀 스레드를 사용할 수 있는 시나리오를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="afb67-112">관리되는 스레드의 예외</span><span class="sxs-lookup"><span data-stu-id="afb67-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="afb67-113">.NET의 여러 버전에 대해 스레드의 처리되지 않은 예외의 동작(특히 애플리케이션 종료를 발생시키는 상황에서)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-113">Describes the behavior of unhandled exceptions in threads for different versions of .NET, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="afb67-114">다중 스레딩을 위한 데이터 동기화</span><span class="sxs-lookup"><span data-stu-id="afb67-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="afb67-115">다중 스레드에서 사용할 클래스의 데이터를 동기화하기 위한 전략에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="afb67-116">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="afb67-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="afb67-117">포그라운드 스레드와 백그라운드 스레드 간의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="afb67-118">Windows에서 관리되는 스레딩 및 관리되지 않는 스레딩</span><span class="sxs-lookup"><span data-stu-id="afb67-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="afb67-119">관리되는 스레딩과 관리되지 않는 스레딩, 간의 관계에 대해 설명하고, Windows 스레딩 API에 대해 관리되는 스레딩을 나열하고, COM 아파트 및 관리되는 스레드의 상호 작용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="afb67-120">스레드 로컬 스토리지: 스레드 관련 정적 필드 및 데이터 슬롯</span><span class="sxs-lookup"><span data-stu-id="afb67-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="afb67-121">스레드 관련 스토리지 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="afb67-122">참고</span><span class="sxs-lookup"><span data-stu-id="afb67-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="afb67-123">비관리 코드에서 가져왔는지 또는 관리되는 애플리케이션에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="afb67-124">사용자 인터페이스 개체와 함께 다중 스레딩을 구현할 수 있는 안전한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="afb67-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="afb67-125">Related sections</span></span>

 [<span data-ttu-id="afb67-126">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="afb67-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="afb67-127">다중 스레드의 활동을 동기화하는 데 사용되는 관리되는 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="afb67-128">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="afb67-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="afb67-129">문제를 피할 수 있도록 다중 스레딩 및 전략에 대한 일반적인 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="afb67-130">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="afb67-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="afb67-131">비동기 및 다중 스레드 .NET 애플리케이션을 만드는 작업을 크게 간소화하는 작업 병렬 라이브러리 및 PLINQ에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afb67-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET applications.</span></span>
