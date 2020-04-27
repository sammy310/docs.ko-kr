---
title: .NET 가비지 수집
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
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
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102244"
---
# <a name="garbage-collection"></a><span data-ttu-id="3cf8e-102">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3cf8e-102">Garbage collection</span></span>

<span data-ttu-id="3cf8e-103">.NET의 가비지 수집기는 애플리케이션의 메모리 할당 및 해제를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="3cf8e-104">새 개체를 만들 때마다 공용 언어 런타임이 관리되는 힙에서 개체에 대해 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="3cf8e-105">관리되는 힙에서 주소 공간을 사용할 수 있다면 런타임은 계속해서 새 개체에 공간을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="3cf8e-106">그러나 메모리는 무한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-106">However, memory is not infinite.</span></span> <span data-ttu-id="3cf8e-107">결국 가비지 수집기는 메모리를 확보하기 위해 수집을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="3cf8e-108">가비지 수집기의 최적화 엔진은 수행 중인 할당에 따라 수집을 수행하기에 가장 적합한 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="3cf8e-109">가비지 수집기는 수집을 수행할 때 애플리케이션에서 더 이상 사용하고 있지 않은 관리되는 힙에 있는 개체를 확인하고 해당 메모리를 회수하는 데 필요한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3cf8e-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="3cf8e-110">In this section</span></span>
  
|<span data-ttu-id="3cf8e-111">제목</span><span class="sxs-lookup"><span data-stu-id="3cf8e-111">Title</span></span>|<span data-ttu-id="3cf8e-112">설명</span><span class="sxs-lookup"><span data-stu-id="3cf8e-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3cf8e-113">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="3cf8e-113">Fundamentals of garbage collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="3cf8e-114">가비지 수집이 작동하는 방법, 관리되는 힙에 개체를 할당하는 방법 및 기타 핵심 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="3cf8e-115">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3cf8e-115">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="3cf8e-116">클라이언트 앱의 워크스테이션 가비지 수집과 서버 앱의 서버 가비지 수집의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-116">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="3cf8e-117">백그라운드 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3cf8e-117">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="3cf8e-118">2세대 수집이 진행 중일 때 이루어지는 0세대 및 1세대 개체의 수집을 가리키는 백그라운드 가비지 수집에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-118">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="3cf8e-119">LOB(Large Object) 힙</span><span class="sxs-lookup"><span data-stu-id="3cf8e-119">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="3cf8e-120">LOH(Large Object 힙)의 개념과 LOB(Large Object)가 가비지 수집되는 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-120">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="3cf8e-121">가비지 수집 및 성능</span><span class="sxs-lookup"><span data-stu-id="3cf8e-121">Garbage collection and performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="3cf8e-122">가비지 수집 및 성능 문제를 진단하는 데 사용할 수 있는 성능 검사에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-122">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="3cf8e-123">도출된 컬렉션</span><span class="sxs-lookup"><span data-stu-id="3cf8e-123">Induced collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="3cf8e-124">가비지 수집을 발생시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-124">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="3cf8e-125">대기 시간 모드</span><span class="sxs-lookup"><span data-stu-id="3cf8e-125">Latency modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="3cf8e-126">가비지 수집의 실행 시기를 결정하는 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-126">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="3cf8e-127">공유 웹 호스팅을 위한 최적화</span><span class="sxs-lookup"><span data-stu-id="3cf8e-127">Optimization for shared web hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="3cf8e-128">여러 개의 작은 웹 사이트에서 공유하는 서버에서 가비지 수집을 최적화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-128">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="3cf8e-129">가비지 수집 알림</span><span class="sxs-lookup"><span data-stu-id="3cf8e-129">Garbage collection notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="3cf8e-130">전체 가비지 수집이 끝나갈 때와 완료될 때를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-130">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="3cf8e-131">애플리케이션 도메인 리소스 모니터링</span><span class="sxs-lookup"><span data-stu-id="3cf8e-131">Application domain resource monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="3cf8e-132">애플리케이션 도메인별로 CPU 및 메모리 사용량을 모니터링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-132">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="3cf8e-133">약한 참조</span><span class="sxs-lookup"><span data-stu-id="3cf8e-133">Weak references</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="3cf8e-134">애플리케이션에서 개체에 계속 액세스하는 동안 가비지 수집기에서 해당 개체를 수집할 수 있도록 하는 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cf8e-134">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="3cf8e-135">참고</span><span class="sxs-lookup"><span data-stu-id="3cf8e-135">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="3cf8e-136">참조</span><span class="sxs-lookup"><span data-stu-id="3cf8e-136">See also</span></span>

- [<span data-ttu-id="3cf8e-137">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="3cf8e-137">Clean up unmanaged resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
