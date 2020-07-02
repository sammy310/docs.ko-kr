---
title: 백그라운드 가비지 수집
description: .NET에서의 백그라운드 가비지 수집에 대해 살펴보고 워크스테이션 및 서버에서의 가비지 수집과 어떻게 다른지 알아봅니다.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, background
- background garbage collection
ms.openlocfilehash: 780503288d3474cd99a595bdbd52c3a5abba5308
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990235"
---
# <a name="background-garbage-collection"></a><span data-ttu-id="9a314-103">백그라운드 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="9a314-103">Background garbage collection</span></span>

<span data-ttu-id="9a314-104">백그라운드 GC(가비지 수집)에서 임시 세대(0세대 및 1세대)는 2세대 수집이 진행되는 동안 필요에 따라 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-104">In background garbage collection (GC), ephemeral generations (0 and 1) are collected as needed while the collection of generation 2 is in progress.</span></span> <span data-ttu-id="9a314-105">백그라운드 가비지 수집은 백그라운드 또는 서버 GC인지 여부에 따라 하나 이상의 전용 스레드에서 수행되며 2세대 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-105">Background garbage collection is performed on one or more dedicated threads, depending on whether it's background or server GC, and applies only to generation 2 collections.</span></span>

<span data-ttu-id="9a314-106">백그라운드 가비지 수집은 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-106">Background garbage collection is enabled by default.</span></span> <span data-ttu-id="9a314-107">.NET Framework 앱의 [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 구성 설정 또는 .NET Core 앱의 [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) 설정에서 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-107">It can be enabled or disabled with the [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration setting in .NET Framework apps or the [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) setting in .NET Core apps.</span></span>

> [!NOTE]
> <span data-ttu-id="9a314-108">백그라운드 가비지 수집은 .NET Framework 4 이상 버전에서 사용할 수 있으며 [동시 가비지 수집](#concurrent-garbage-collection)을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-108">Background garbage collection replaces [concurrent garbage collection](#concurrent-garbage-collection) and is available in .NET Framework 4 and later versions.</span></span> <span data-ttu-id="9a314-109">.NET Framework 4에서는 *워크스테이션* 가비지 수집의 경우에만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-109">In .NET Framework 4, it's supported only for *workstation* garbage collection.</span></span> <span data-ttu-id="9a314-110">.NET Framework 4.5부터 백그라운드 가비지 수집이 *워크스테이션* 및 *서버* 가비지 수집 모두에서 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-110">Starting with .NET Framework 4.5, background garbage collection is available for both *workstation* and *server* garbage collection.</span></span>

<span data-ttu-id="9a314-111">백그라운드 가비지 수집 중의 임시 세대 수집을 *포그라운드* 가비지 수집이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-111">A collection on ephemeral generations during background garbage collection is known as *foreground* garbage collection.</span></span> <span data-ttu-id="9a314-112">포그라운드 가비지 수집이 발생하면 모든 관리되는 스레드가 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-112">When foreground garbage collections occur, all managed threads are suspended.</span></span>

<span data-ttu-id="9a314-113">백그라운드 가비지 수집이 진행 중이고 0세대에 충분한 개체가 할당된 경우 CLR은 0세대 또는 1세대 포그라운드 가비지 수집을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-113">When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection.</span></span> <span data-ttu-id="9a314-114">전용 백그라운드 가비지 수집 스레드는 안전한 지점을 수시로 검사하여 포그라운드 가비지 수집 요청이 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-114">The dedicated background garbage collection thread checks at frequent safe points to determine whether there is a request for foreground garbage collection.</span></span> <span data-ttu-id="9a314-115">요청이 있는 경우 포그라운드 가비지 수집이 발생할 수 있도록 백그라운드 수집은 스스로를 일시 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-115">If there is, the background collection suspends itself so that foreground garbage collection can occur.</span></span> <span data-ttu-id="9a314-116">포그라운드 가비지 수집이 완료되고 나면 전용 백그라운드 가비지 수집 스레드와 사용자 스레드가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-116">After the foreground garbage collection is completed, the dedicated background garbage collection threads and user threads resume.</span></span>

<span data-ttu-id="9a314-117">백그라운드 가비지 수집 중에 임시 가비지 수집이 발생할 수 있으므로 백그라운드 가비지 수집은 동시 가비지 수집에 의해 적용된 할당 제한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-117">Background garbage collection removes allocation restrictions imposed by concurrent garbage collection, because ephemeral garbage collections can occur during background garbage collection.</span></span> <span data-ttu-id="9a314-118">백그라운드 가비지 수집은 임시 세대에서 비활성 개체를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-118">Background garbage collection can remove dead objects in ephemeral generations.</span></span> <span data-ttu-id="9a314-119">필요한 경우 1세대 가비지 수집 중에 힙을 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-119">It can also expand the heap if needed during a generation 1 garbage collection.</span></span>

## <a name="background-workstation-vs-server-gc"></a><span data-ttu-id="9a314-120">백그라운드 워크스테이션 및 서버 GC 비교</span><span class="sxs-lookup"><span data-stu-id="9a314-120">Background workstation vs. server GC</span></span>

<span data-ttu-id="9a314-121">.NET Framework 4.5부터 서버 가비지 수집에 백그라운드 GC를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-121">Starting with .NET Framework 4.5, background garbage collection is available for server GC.</span></span> <span data-ttu-id="9a314-122">백그라운드 GC는 서버 가비지 수집의 기본 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-122">Background GC is the default mode for server garbage collection.</span></span>

<span data-ttu-id="9a314-123">백그라운드 서버 가비지 수집은 백그라운드 워크스테이션 가비지 수집과 비슷하게 작동하지만, 몇 가지 다른 점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-123">Background server garbage collection functions similarly to background workstation garbage collection, but there are a few differences:</span></span>

- <span data-ttu-id="9a314-124">백그라운드 서버 가비지 수집은 다중 스레드를 사용하는 반면, 백그라운드 워크스테이션 가비지 수집은 단일 전용 백그라운드 가비지 수집 스레드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-124">Background workstation garbage collection uses one dedicated background garbage collection thread, whereas background server garbage collection uses multiple threads.</span></span> <span data-ttu-id="9a314-125">일반적으로 각 논리 프로세서에 사용할 수 있는 전용 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-125">Typically, there's a dedicated thread for each logical processor.</span></span>

- <span data-ttu-id="9a314-126">워크스테이션 백그라운드 가비지 수집 스레드와는 달리 백그라운드 서버 GC 스레드는 시간 초과되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-126">Unlike the workstation background garbage collection thread, the background server GC threads do not time out.</span></span>

<span data-ttu-id="9a314-127">다음 그림에서는 개별 전용 스레드에서 수행되는 백그라운드 *워크스테이션* 가비지 수집을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-127">The following illustration shows background *workstation* garbage collection performed on a separate, dedicated thread:</span></span>

![백그라운드 워크스테이션 가비지 수집](media/fundamentals/background-workstation-garbage-collection.png)

<span data-ttu-id="9a314-129">다음 그림에서는 개별 전용 스레드에서 수행되는 백그라운드 *서버* 가비지 수집을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-129">The following illustration shows background *server* garbage collection performed on separate, dedicated threads:</span></span>

![백그라운드 서버 가비지 수집](media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a><span data-ttu-id="9a314-131">동시 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="9a314-131">Concurrent garbage collection</span></span>

> [!TIP]
> <span data-ttu-id="9a314-132">이 섹션은 다음에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-132">This section applies to:</span></span>
>
> - <span data-ttu-id="9a314-133">워크스테이션 가비지 수집의 경우 .NET Framework 3.5 이전 버전</span><span class="sxs-lookup"><span data-stu-id="9a314-133">.NET Framework 3.5 and earlier for workstation garbage collection</span></span>
> - <span data-ttu-id="9a314-134">서버 가비지 수집의 경우 .NET Framework 4 이전 버전</span><span class="sxs-lookup"><span data-stu-id="9a314-134">.NET Framework 4 and earlier for server garbage collection</span></span>
>
> <span data-ttu-id="9a314-135">동시 가비지는 이후 버전에서 백그라운드 가비지 수집으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-135">Concurrent garbage is replaced by background garbage collection in later versions.</span></span>

<span data-ttu-id="9a314-136">워크스테이션 또는 서버 가비지 수집에서 [동시 가비지 수집을 활성화](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)할 수 있습니다. 동시 가비지 수집을 사용하면 대부분의 수집 기간 동안 가비지 수집을 수행하는 전용 스레드와 다른 스레드가 동시에 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-136">In workstation or server garbage collection, you can [enable concurrent garbage collection](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), which enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection.</span></span> <span data-ttu-id="9a314-137">이 옵션은 2세대 가비지 수집에만 영향을 미칩니다. 0세대 및 1세대는 빠르게 완료되므로 항상 비동시 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-137">This option affects only garbage collections in generation 2; generations 0 and 1 are always non-concurrent because they finish fast.</span></span>

<span data-ttu-id="9a314-138">동시 가비지 수집을 사용하면 수집을 위한 일시 중지가 최소화되어 대화형 애플리케이션의 응답성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-138">Concurrent garbage collection enables interactive applications to be more responsive by minimizing pauses for a collection.</span></span> <span data-ttu-id="9a314-139">동시 가비지 수집 스레드가 실행되는 대부분의 시간 동안 관리되는 스레드가 계속 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-139">Managed threads can continue to run most of the time while the concurrent garbage collection thread is running.</span></span> <span data-ttu-id="9a314-140">이렇게 디자인하면 가비지 수집이 발생하는 동안 일시 중지 시간이 더 짧아지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-140">This design results in shorter pauses while a garbage collection is occurring.</span></span>

<span data-ttu-id="9a314-141">동시 가비지 수집은 전용 스레드에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-141">Concurrent garbage collection is performed on a dedicated thread.</span></span> <span data-ttu-id="9a314-142">기본적으로 CLR은 단일 프로세서 및 다중 프로세서 컴퓨터에서 동시 가비지 수집을 사용하도록 설정하여 워크스테이션 가비지 수집을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-142">By default, the CLR runs workstation garbage collection with concurrent garbage collection enabled on both single-processor and multi-processor computers.</span></span>

<span data-ttu-id="9a314-143">다음 그림에서는 개별 전용 스레드에서 수행되는 동시 가비지 수집을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a314-143">The following illustration shows concurrent garbage collection performed on a separate dedicated thread.</span></span>

![동시 가비지 수집 스레드](media/gc-concurrent.png)

## <a name="see-also"></a><span data-ttu-id="9a314-145">참조</span><span class="sxs-lookup"><span data-stu-id="9a314-145">See also</span></span>

- [<span data-ttu-id="9a314-146">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="9a314-146">Workstation and server garbage collection</span></span>](workstation-server-gc.md)
- [<span data-ttu-id="9a314-147">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="9a314-147">Run-time configuration options for garbage collection</span></span>](../../core/run-time-config/garbage-collector.md)
