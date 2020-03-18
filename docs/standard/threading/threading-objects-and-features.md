---
title: 스레딩 개체 및 기능
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: dd9b7b8cb194353d0a1c285af10d54dc7366896e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128966"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="5c91f-102">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="5c91f-102">Threading objects and features</span></span>

<span data-ttu-id="5c91f-103"><xref:System.Threading.Thread?displayProperty=nameWithType> 클래스와 함께 .NET 다중 스레드 애플리케이션을 개발하는 데 도움이 되는 여러 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="5c91f-104">다음 문서에서는 해당 클래스의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="5c91f-105">제목</span><span class="sxs-lookup"><span data-stu-id="5c91f-105">Title</span></span>|<span data-ttu-id="5c91f-106">설명</span><span class="sxs-lookup"><span data-stu-id="5c91f-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5c91f-107">관리되는 스레드 풀</span><span class="sxs-lookup"><span data-stu-id="5c91f-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="5c91f-108">.NET에서 관리하는 작업자 스레드 풀을 제공하는 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="5c91f-109">타이머</span><span class="sxs-lookup"><span data-stu-id="5c91f-109">Timers</span></span>](timers.md)|<span data-ttu-id="5c91f-110">다중 스레드 환경에서 사용할 수 있는 .NET 타이머에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="5c91f-111">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="5c91f-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="5c91f-112">공유 리소스에 대한 액세스를 동기화하거나 스레드 상호 작용을 제어하는 데 사용할 수 있는 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="5c91f-113">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="5c91f-113">EventWaitHandle</span></span>](eventwaithandle.md)|<span data-ttu-id="5c91f-114">스레드 동기화 이벤트를 나타내는 <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-114">Describes the <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class, which represents a thread synchronization event.</span></span>|
|[<span data-ttu-id="5c91f-115">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="5c91f-115">CountdownEvent</span></span>](countdownevent.md)|<span data-ttu-id="5c91f-116">해당 개수가 0일 때 설정되는 스레드 동기화 이벤트를 나타내는 <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-116">Describes the <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class, which represents a thread synchronization event that becomes set when its count is zero.</span></span>|
|[<span data-ttu-id="5c91f-117">뮤텍스</span><span class="sxs-lookup"><span data-stu-id="5c91f-117">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="5c91f-118">공유 리소스에 대한 배타적 액세스 권한을 부여하는 <xref:System.Threading.Mutex?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-118">Describes the <xref:System.Threading.Mutex?displayProperty=nameWithType> class, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="5c91f-119">세마포 및 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="5c91f-119">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="5c91f-120">공유 리소스 또는 리소스 풀에 동시에 액세스할 수 있는 스레드 수를 제한하는 <xref:System.Threading.Semaphore?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-120">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="5c91f-121">장벽</span><span class="sxs-lookup"><span data-stu-id="5c91f-121">Barrier</span></span>](barrier.md)|<span data-ttu-id="5c91f-122">단계별 작업에서 스레드를 조정하기 위해 장벽 패턴을 구현하는 <xref:System.Threading.Barrier?displayProperty=nameWithType> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-122">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class, which implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="5c91f-123">SpinLock</span><span class="sxs-lookup"><span data-stu-id="5c91f-123">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="5c91f-124">특정 하위 수준 잠금 시나리오의 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 클래스에 대한 간단한 대체 항목인 <xref:System.Threading.Monitor?displayProperty=nameWithType> 구조체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-124">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="5c91f-125">SpinWait</span><span class="sxs-lookup"><span data-stu-id="5c91f-125">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="5c91f-126">회전 기반 대기를 지원하는 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 구조체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c91f-126">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5c91f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c91f-127">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="5c91f-128">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="5c91f-128">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="5c91f-129">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="5c91f-129">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="5c91f-130">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5c91f-130">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="5c91f-131">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="5c91f-131">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
