---
title: .NET 가비지 수집
description: .NET의 가비지 수집에 대해 알아보세요. .NET 가비지 수집기는 애플리케이션의 메모리 할당 및 해제를 관리합니다.
ms.date: 04/21/2020
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 8b1fad3420778c17656614994684930fcd1b62ca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827778"
---
# <a name="garbage-collection"></a><span data-ttu-id="ea4a4-104">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="ea4a4-104">Garbage collection</span></span>

<span data-ttu-id="ea4a4-105">.NET의 가비지 수집기는 애플리케이션의 메모리 할당 및 해제를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-105">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="ea4a4-106">새 개체를 만들 때마다 공용 언어 런타임이 관리되는 힙에서 개체에 대해 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-106">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="ea4a4-107">관리되는 힙에서 주소 공간을 사용할 수 있다면 런타임은 계속해서 새 개체에 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-107">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="ea4a4-108">그러나 메모리는 무한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-108">However, memory is not infinite.</span></span> <span data-ttu-id="ea4a4-109">결국 가비지 수집기는 메모리를 확보하기 위해 수집을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-109">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="ea4a4-110">가비지 수집기의 최적화 엔진은 수행 중인 할당에 따라 수집을 수행하기에 가장 적합한 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-110">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="ea4a4-111">가비지 수집기는 수집을 수행할 때 애플리케이션에서 더 이상 사용하고 있지 않은 관리되는 힙에 있는 개체를 확인하고 해당 메모리를 회수하는 데 필요한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-111">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea4a4-112">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ea4a4-112">In this section</span></span>
  
|<span data-ttu-id="ea4a4-113">제목</span><span class="sxs-lookup"><span data-stu-id="ea4a4-113">Title</span></span>|<span data-ttu-id="ea4a4-114">설명</span><span class="sxs-lookup"><span data-stu-id="ea4a4-114">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ea4a4-115">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="ea4a4-115">Fundamentals of garbage collection</span></span>](fundamentals.md)|<span data-ttu-id="ea4a4-116">가비지 수집이 작동하는 방법, 관리되는 힙에 개체를 할당하는 방법 및 기타 핵심 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-116">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="ea4a4-117">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="ea4a4-117">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="ea4a4-118">클라이언트 앱의 워크스테이션 가비지 수집과 서버 앱의 서버 가비지 수집의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-118">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="ea4a4-119">백그라운드 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="ea4a4-119">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="ea4a4-120">2세대 수집이 진행 중일 때 이루어지는 0세대 및 1세대 개체의 수집을 가리키는 백그라운드 가비지 수집에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-120">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="ea4a4-121">LOB(Large Object) 힙</span><span class="sxs-lookup"><span data-stu-id="ea4a4-121">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="ea4a4-122">LOH(Large Object 힙)의 개념과 LOB(Large Object)가 가비지 수집되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-122">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="ea4a4-123">가비지 수집 및 성능</span><span class="sxs-lookup"><span data-stu-id="ea4a4-123">Garbage collection and performance</span></span>](performance.md)|<span data-ttu-id="ea4a4-124">가비지 수집 및 성능 문제를 진단하는 데 사용할 수 있는 성능 검사에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-124">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="ea4a4-125">도출된 컬렉션</span><span class="sxs-lookup"><span data-stu-id="ea4a4-125">Induced collections</span></span>](induced.md)|<span data-ttu-id="ea4a4-126">가비지 수집을 발생시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-126">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="ea4a4-127">대기 시간 모드</span><span class="sxs-lookup"><span data-stu-id="ea4a4-127">Latency modes</span></span>](latency.md)|<span data-ttu-id="ea4a4-128">가비지 수집의 실행 시기를 결정하는 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-128">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="ea4a4-129">공유 웹 호스팅을 위한 최적화</span><span class="sxs-lookup"><span data-stu-id="ea4a4-129">Optimization for shared web hosting</span></span>](optimization-for-shared-web-hosting.md)|<span data-ttu-id="ea4a4-130">여러 개의 작은 웹 사이트에서 공유하는 서버에서 가비지 수집을 최적화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-130">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="ea4a4-131">가비지 수집 알림</span><span class="sxs-lookup"><span data-stu-id="ea4a4-131">Garbage collection notifications</span></span>](notifications.md)|<span data-ttu-id="ea4a4-132">전체 가비지 수집이 끝나갈 때와 완료될 때를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-132">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="ea4a4-133">애플리케이션 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="ea4a4-133">Application domain resource monitoring</span></span>](app-domain-resource-monitoring.md)|<span data-ttu-id="ea4a4-134">애플리케이션 도메인별로 CPU 및 메모리 사용량을 모니터링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-134">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="ea4a4-135">약한 참조</span><span class="sxs-lookup"><span data-stu-id="ea4a4-135">Weak references</span></span>](weak-references.md)|<span data-ttu-id="ea4a4-136">애플리케이션에서 개체에 계속 액세스하는 동안 가비지 수집기에서 해당 개체를 수집할 수 있도록 하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea4a4-136">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="ea4a4-137">참고</span><span class="sxs-lookup"><span data-stu-id="ea4a4-137">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="ea4a4-138">참조</span><span class="sxs-lookup"><span data-stu-id="ea4a4-138">See also</span></span>

- [<span data-ttu-id="ea4a4-139">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="ea4a4-139">Clean up unmanaged resources</span></span>](unmanaged.md)
