---
title: 가비지 컬렉션 ETW 이벤트
description: 가비지 수집 ETW 이벤트에 대 한 자세한 정보를 확인 합니다. 여기에 포함 된 이벤트에는 GCStart_V1, GCEnd_V1, GCHeapStats_V1, GCCreateSegment_V1 등이 포함 됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 58ad874ef6a12c18c404640aa66577c391573534
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309744"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="c8238-104">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c8238-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="c8238-105">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="c8238-106">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="c8238-107">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="c8238-108">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="c8238-109">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="c8238-110">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="c8238-111">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-111">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="c8238-112">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-112">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="c8238-113">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-113">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="c8238-114">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-114">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="c8238-115">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-115">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="c8238-116">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-116">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="c8238-117">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-117">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="c8238-118">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-118">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="c8238-119">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-119">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="c8238-120">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-120">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="c8238-121">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-121">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="c8238-122">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-122">GCStart_V1 Event</span></span>  

<span data-ttu-id="c8238-123">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-123">The following table shows the keyword and level.</span></span> <span data-ttu-id="c8238-124">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8238-124">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="c8238-125">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-125">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-126">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-127">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-127">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-128">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-128">Informational (4)</span></span>|

<span data-ttu-id="c8238-129">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-129">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-130">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-130">Event</span></span>|<span data-ttu-id="c8238-131">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-131">Event ID</span></span>|<span data-ttu-id="c8238-132">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="c8238-133">1</span><span class="sxs-lookup"><span data-stu-id="c8238-133">1</span></span>|<span data-ttu-id="c8238-134">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-134">A garbage collection has started.</span></span>|

<span data-ttu-id="c8238-135">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-135">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-136">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-136">Field name</span></span>|<span data-ttu-id="c8238-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-137">Data type</span></span>|<span data-ttu-id="c8238-138">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-138">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-139">개수</span><span class="sxs-lookup"><span data-stu-id="c8238-139">Count</span></span>|<span data-ttu-id="c8238-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-140">win:UInt32</span></span>|<span data-ttu-id="c8238-141">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-141">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c8238-142">깊이</span><span class="sxs-lookup"><span data-stu-id="c8238-142">Depth</span></span>|<span data-ttu-id="c8238-143">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-143">win:UInt32</span></span>|<span data-ttu-id="c8238-144">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-144">The generation that is being collected.</span></span>|
|<span data-ttu-id="c8238-145">이유</span><span class="sxs-lookup"><span data-stu-id="c8238-145">Reason</span></span>|<span data-ttu-id="c8238-146">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-146">win:UInt32</span></span>|<span data-ttu-id="c8238-147">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-147">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="c8238-148">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="c8238-148">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="c8238-149">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="c8238-149">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="c8238-150">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="c8238-150">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="c8238-151">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="c8238-151">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="c8238-152">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="c8238-152">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="c8238-153">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="c8238-153">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="c8238-154">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="c8238-154">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="c8238-155">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="c8238-155">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="c8238-156">Type</span><span class="sxs-lookup"><span data-stu-id="c8238-156">Type</span></span>|<span data-ttu-id="c8238-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-157">win:UInt32</span></span>|<span data-ttu-id="c8238-158">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="c8238-158">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="c8238-159">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="c8238-159">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="c8238-160">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="c8238-160">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="c8238-161">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-161">ClrInstanceID</span></span>|<span data-ttu-id="c8238-162">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-162">win:UInt16</span></span>|<span data-ttu-id="c8238-163">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="c8238-164">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-164">GCEnd_V1 Event</span></span>

<span data-ttu-id="c8238-165">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-165">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-166">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-166">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-167">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-168">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-168">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-169">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-169">Informational (4)</span></span>|

<span data-ttu-id="c8238-170">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-170">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-171">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-171">Event</span></span>|<span data-ttu-id="c8238-172">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-172">Event ID</span></span>|<span data-ttu-id="c8238-173">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="c8238-174">2</span><span class="sxs-lookup"><span data-stu-id="c8238-174">2</span></span>|<span data-ttu-id="c8238-175">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-175">The garbage collection has ended.</span></span>|

<span data-ttu-id="c8238-176">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-176">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-177">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-177">Field name</span></span>|<span data-ttu-id="c8238-178">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-178">Data type</span></span>|<span data-ttu-id="c8238-179">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-179">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-180">개수</span><span class="sxs-lookup"><span data-stu-id="c8238-180">Count</span></span>|<span data-ttu-id="c8238-181">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-181">win:UInt32</span></span>|<span data-ttu-id="c8238-182">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-182">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c8238-183">깊이</span><span class="sxs-lookup"><span data-stu-id="c8238-183">Depth</span></span>|<span data-ttu-id="c8238-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-184">win:UInt32</span></span>|<span data-ttu-id="c8238-185">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-185">The generation that was collected.</span></span>|
|<span data-ttu-id="c8238-186">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-186">ClrInstanceID</span></span>|<span data-ttu-id="c8238-187">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-187">win:UInt16</span></span>|<span data-ttu-id="c8238-188">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-188">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="c8238-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-189">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="c8238-190">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-190">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-191">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-191">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-192">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-192">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-194">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-194">Informational (4)</span></span>|

<span data-ttu-id="c8238-195">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-195">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-196">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-196">Event</span></span>|<span data-ttu-id="c8238-197">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-197">Event ID</span></span>|<span data-ttu-id="c8238-198">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-198">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="c8238-199">4</span><span class="sxs-lookup"><span data-stu-id="c8238-199">4</span></span>|<span data-ttu-id="c8238-200">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-200">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="c8238-201">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-201">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-202">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-202">Field name</span></span>|<span data-ttu-id="c8238-203">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-203">Data type</span></span>|<span data-ttu-id="c8238-204">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-204">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="c8238-205">GenerationSize0</span></span>|<span data-ttu-id="c8238-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-206">win:UInt64</span></span>|<span data-ttu-id="c8238-207">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-207">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="c8238-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="c8238-208">TotalPromotedSize0</span></span>|<span data-ttu-id="c8238-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-209">win:UInt64</span></span>|<span data-ttu-id="c8238-210">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="c8238-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="c8238-211">GenerationSize1</span></span>|<span data-ttu-id="c8238-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-212">win:UInt64</span></span>|<span data-ttu-id="c8238-213">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-213">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="c8238-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="c8238-214">TotalPromotedSize1</span></span>|<span data-ttu-id="c8238-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-215">win:UInt64</span></span>|<span data-ttu-id="c8238-216">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="c8238-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="c8238-217">GenerationSize2</span></span>|<span data-ttu-id="c8238-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-218">win:UInt64</span></span>|<span data-ttu-id="c8238-219">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-219">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="c8238-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="c8238-220">TotalPromotedSize2</span></span>|<span data-ttu-id="c8238-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-221">win:UInt64</span></span>|<span data-ttu-id="c8238-222">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="c8238-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="c8238-223">GenerationSize3</span></span>|<span data-ttu-id="c8238-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-224">win:UInt64</span></span>|<span data-ttu-id="c8238-225">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-225">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="c8238-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="c8238-226">TotalPromotedSize3</span></span>|<span data-ttu-id="c8238-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-227">win:UInt64</span></span>|<span data-ttu-id="c8238-228">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="c8238-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="c8238-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="c8238-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-230">win:UInt64</span></span>|<span data-ttu-id="c8238-231">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c8238-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="c8238-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="c8238-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-233">win:UInt64</span></span>|<span data-ttu-id="c8238-234">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-234">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c8238-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="c8238-235">PinnedObjectCount</span></span>|<span data-ttu-id="c8238-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-236">win:UInt32</span></span>|<span data-ttu-id="c8238-237">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-237">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="c8238-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="c8238-238">SinkBlockCount</span></span>|<span data-ttu-id="c8238-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-239">win:UInt32</span></span>|<span data-ttu-id="c8238-240">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-240">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="c8238-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="c8238-241">GCHandleCount</span></span>|<span data-ttu-id="c8238-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-242">win:UInt32</span></span>|<span data-ttu-id="c8238-243">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-243">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="c8238-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-244">ClrInstanceID</span></span>|<span data-ttu-id="c8238-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-245">win:UInt16</span></span>|<span data-ttu-id="c8238-246">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="c8238-247">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-247">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="c8238-248">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-248">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-249">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-249">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-250">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-250">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-251">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-251">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-252">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-252">Informational (4)</span></span>|

<span data-ttu-id="c8238-253">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-253">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-254">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-254">Event</span></span>|<span data-ttu-id="c8238-255">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-255">Event ID</span></span>|<span data-ttu-id="c8238-256">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-256">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="c8238-257">5</span><span class="sxs-lookup"><span data-stu-id="c8238-257">5</span></span>|<span data-ttu-id="c8238-258">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-258">A new garbage collection segment has been created.</span></span> <span data-ttu-id="c8238-259">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-259">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="c8238-260">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-260">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-261">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-261">Field name</span></span>|<span data-ttu-id="c8238-262">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-262">Data type</span></span>|<span data-ttu-id="c8238-263">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-263">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-264">주소</span><span class="sxs-lookup"><span data-stu-id="c8238-264">Address</span></span>|<span data-ttu-id="c8238-265">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-265">win:UInt64</span></span>|<span data-ttu-id="c8238-266">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-266">The address of the segment.</span></span>|
|<span data-ttu-id="c8238-267">크기</span><span class="sxs-lookup"><span data-stu-id="c8238-267">Size</span></span>|<span data-ttu-id="c8238-268">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-268">win:UInt64</span></span>|<span data-ttu-id="c8238-269">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-269">The size of the segment.</span></span>|
|<span data-ttu-id="c8238-270">Type</span><span class="sxs-lookup"><span data-stu-id="c8238-270">Type</span></span>|<span data-ttu-id="c8238-271">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-271">win:UInt32</span></span>|<span data-ttu-id="c8238-272">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="c8238-272">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="c8238-273">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="c8238-273">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="c8238-274">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="c8238-274">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="c8238-275">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-275">ClrInstanceID</span></span>|<span data-ttu-id="c8238-276">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-276">win:UInt16</span></span>|<span data-ttu-id="c8238-277">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-277">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="c8238-278">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-278">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="c8238-279">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-279">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="c8238-280">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-280">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="c8238-281">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-281">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-282">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-282">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-283">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-283">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-284">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-284">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-285">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-285">Informational (4)</span></span>|

<span data-ttu-id="c8238-286">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-286">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-287">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-287">Event</span></span>|<span data-ttu-id="c8238-288">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-288">Event ID</span></span>|<span data-ttu-id="c8238-289">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-289">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="c8238-290">6</span><span class="sxs-lookup"><span data-stu-id="c8238-290">6</span></span>|<span data-ttu-id="c8238-291">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-291">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="c8238-292">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-292">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-293">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-293">Field name</span></span>|<span data-ttu-id="c8238-294">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-294">Data type</span></span>|<span data-ttu-id="c8238-295">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-295">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-296">주소</span><span class="sxs-lookup"><span data-stu-id="c8238-296">Address</span></span>|<span data-ttu-id="c8238-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-297">win:UInt64</span></span>|<span data-ttu-id="c8238-298">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-298">The address of the segment.</span></span>|
|<span data-ttu-id="c8238-299">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-299">ClrInstanceID</span></span>|<span data-ttu-id="c8238-300">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-300">win:UInt16</span></span>|<span data-ttu-id="c8238-301">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-301">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="c8238-302">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-302">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="c8238-303">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-303">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-304">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-304">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-305">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-305">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-306">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-306">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-307">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-307">Informational (4)</span></span>|

<span data-ttu-id="c8238-308">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-308">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-309">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-309">Event</span></span>|<span data-ttu-id="c8238-310">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-310">Event ID</span></span>|<span data-ttu-id="c8238-311">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-311">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="c8238-312">7</span><span class="sxs-lookup"><span data-stu-id="c8238-312">7</span></span>|<span data-ttu-id="c8238-313">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-313">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="c8238-314">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-314">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="c8238-315">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-315">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="c8238-316">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-316">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-317">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-317">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-318">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-318">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-319">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-319">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-320">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-320">Informational (4)</span></span>|

<span data-ttu-id="c8238-321">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-321">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-322">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-322">Event</span></span>|<span data-ttu-id="c8238-323">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-323">Event Id</span></span>|<span data-ttu-id="c8238-324">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-324">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="c8238-325">3</span><span class="sxs-lookup"><span data-stu-id="c8238-325">3</span></span>|<span data-ttu-id="c8238-326">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-326">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="c8238-327">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-327">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="c8238-328">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-328">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="c8238-329">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-329">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-330">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-330">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-331">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-331">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-332">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-332">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-333">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-333">Informational (4)</span></span>|

<span data-ttu-id="c8238-334">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-334">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-335">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-335">Event</span></span>|<span data-ttu-id="c8238-336">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-336">Event ID</span></span>|<span data-ttu-id="c8238-337">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-337">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="c8238-338">9</span><span class="sxs-lookup"><span data-stu-id="c8238-338">9</span></span>|<span data-ttu-id="c8238-339">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-339">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c8238-340">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-340">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-341">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-341">Field name</span></span>|<span data-ttu-id="c8238-342">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-342">Data type</span></span>|<span data-ttu-id="c8238-343">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-343">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-344">이유</span><span class="sxs-lookup"><span data-stu-id="c8238-344">Reason</span></span>|<span data-ttu-id="c8238-345">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-345">win:UInt16</span></span>|<span data-ttu-id="c8238-346">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="c8238-346">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="c8238-347">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="c8238-347">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="c8238-348">0x2 - 애플리케이션 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="c8238-348">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="c8238-349">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="c8238-349">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="c8238-350">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="c8238-350">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="c8238-351">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="c8238-351">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="c8238-352">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="c8238-352">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="c8238-353">개수</span><span class="sxs-lookup"><span data-stu-id="c8238-353">Count</span></span>|<span data-ttu-id="c8238-354">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-354">win:UInt32</span></span>|<span data-ttu-id="c8238-355">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-355">The GC count at the time.</span></span> <span data-ttu-id="c8238-356">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-356">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="c8238-357">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-357">ClrInstanceID</span></span>|<span data-ttu-id="c8238-358">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-358">win:UInt16</span></span>|<span data-ttu-id="c8238-359">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-359">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="c8238-360">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-360">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="c8238-361">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-361">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-362">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-362">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-363">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-363">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-364">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-364">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-365">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-365">Informational (4)</span></span>|

<span data-ttu-id="c8238-366">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-366">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-367">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-367">Event</span></span>|<span data-ttu-id="c8238-368">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-368">Event ID</span></span>|<span data-ttu-id="c8238-369">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-369">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="c8238-370">8</span><span class="sxs-lookup"><span data-stu-id="c8238-370">8</span></span>|<span data-ttu-id="c8238-371">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-371">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c8238-372">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-372">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="c8238-373">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-373">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="c8238-374">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-374">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-375">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-375">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-376">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-376">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-377">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-377">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-378">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-378">Informational (4)</span></span>|

<span data-ttu-id="c8238-379">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-379">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-380">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-380">Event</span></span>|<span data-ttu-id="c8238-381">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-381">Event ID</span></span>|<span data-ttu-id="c8238-382">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-382">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="c8238-383">10</span><span class="sxs-lookup"><span data-stu-id="c8238-383">10</span></span>|<span data-ttu-id="c8238-384">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-384">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="c8238-385">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-385">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-386">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-386">Field name</span></span>|<span data-ttu-id="c8238-387">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-387">Data type</span></span>|<span data-ttu-id="c8238-388">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-388">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-389">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="c8238-389">AllocationAmount</span></span>|<span data-ttu-id="c8238-390">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-390">win:UInt32</span></span>|<span data-ttu-id="c8238-391">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-391">The allocation size, in bytes.</span></span> <span data-ttu-id="c8238-392">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-392">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="c8238-393">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-393">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="c8238-394">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c8238-394">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="c8238-395">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="c8238-395">AllocationKind</span></span>|<span data-ttu-id="c8238-396">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-396">win:UInt32</span></span>|<span data-ttu-id="c8238-397">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="c8238-397">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="c8238-398">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="c8238-398">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="c8238-399">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-399">ClrInstanceID</span></span>|<span data-ttu-id="c8238-400">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-400">win:UInt16</span></span>|<span data-ttu-id="c8238-401">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-401">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="c8238-402">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="c8238-402">AllocationAmount64</span></span>|<span data-ttu-id="c8238-403">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c8238-403">win:UInt64</span></span>|<span data-ttu-id="c8238-404">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-404">The allocation size, in bytes.</span></span> <span data-ttu-id="c8238-405">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-405">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="c8238-406">TypeId</span><span class="sxs-lookup"><span data-stu-id="c8238-406">TypeId</span></span>|<span data-ttu-id="c8238-407">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c8238-407">win:Pointer</span></span>|<span data-ttu-id="c8238-408">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-408">The address of the MethodTable.</span></span> <span data-ttu-id="c8238-409">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-409">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c8238-410">TypeName</span><span class="sxs-lookup"><span data-stu-id="c8238-410">TypeName</span></span>|<span data-ttu-id="c8238-411">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c8238-411">win:UnicodeString</span></span>|<span data-ttu-id="c8238-412">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-412">The name of the type that was allocated.</span></span> <span data-ttu-id="c8238-413">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-413">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c8238-414">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="c8238-414">HeapIndex</span></span>|<span data-ttu-id="c8238-415">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-415">win:UInt32</span></span>|<span data-ttu-id="c8238-416">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-416">The heap where the object was allocated.</span></span> <span data-ttu-id="c8238-417">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-417">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="c8238-418">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-418">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="c8238-419">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-419">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-420">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-420">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-421">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-421">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-422">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-422">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-423">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-423">Informational (4)</span></span>|

<span data-ttu-id="c8238-424">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-424">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-425">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-425">Event</span></span>|<span data-ttu-id="c8238-426">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-426">Event ID</span></span>|<span data-ttu-id="c8238-427">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-427">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="c8238-428">14</span><span class="sxs-lookup"><span data-stu-id="c8238-428">14</span></span>|<span data-ttu-id="c8238-429">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-429">The start of running finalizers.</span></span>|

<span data-ttu-id="c8238-430">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-430">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="c8238-431">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-431">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="c8238-432">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-432">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-433">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-433">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-434">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-435">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-435">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-436">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-436">Informational (4)</span></span>|

<span data-ttu-id="c8238-437">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-437">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-438">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-438">Event</span></span>|<span data-ttu-id="c8238-439">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-439">Event ID</span></span>|<span data-ttu-id="c8238-440">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-440">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="c8238-441">13</span><span class="sxs-lookup"><span data-stu-id="c8238-441">13</span></span>|<span data-ttu-id="c8238-442">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-442">The end of running finalizers.</span></span>|

<span data-ttu-id="c8238-443">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-443">The following table shows the event data:</span></span>

|<span data-ttu-id="c8238-444">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c8238-444">Field name</span></span>|<span data-ttu-id="c8238-445">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8238-445">Data type</span></span>|<span data-ttu-id="c8238-446">Description</span><span class="sxs-lookup"><span data-stu-id="c8238-446">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c8238-447">개수</span><span class="sxs-lookup"><span data-stu-id="c8238-447">Count</span></span>|<span data-ttu-id="c8238-448">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c8238-448">win:UInt32</span></span>|<span data-ttu-id="c8238-449">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-449">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="c8238-450">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c8238-450">ClrInstanceID</span></span>|<span data-ttu-id="c8238-451">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c8238-451">win:UInt16</span></span>|<span data-ttu-id="c8238-452">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-452">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="c8238-453">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-453">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c8238-454">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-454">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-455">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-455">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-456">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-456">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-457">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-457">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-458">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-458">Informational (4)</span></span>|
|<span data-ttu-id="c8238-459">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c8238-459">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c8238-460">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-460">Informational (4)</span></span>|

<span data-ttu-id="c8238-461">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-461">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-462">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-462">Event</span></span>|<span data-ttu-id="c8238-463">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-463">Event ID</span></span>|<span data-ttu-id="c8238-464">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-464">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="c8238-465">11</span><span class="sxs-lookup"><span data-stu-id="c8238-465">11</span></span>|<span data-ttu-id="c8238-466">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-466">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="c8238-467">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-467">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="c8238-468">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c8238-468">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c8238-469">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-469">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c8238-470">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c8238-470">Keyword for raising the event</span></span>|<span data-ttu-id="c8238-471">수준</span><span class="sxs-lookup"><span data-stu-id="c8238-471">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c8238-472">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c8238-472">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c8238-473">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-473">Informational (4)</span></span>|
|<span data-ttu-id="c8238-474">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c8238-474">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c8238-475">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c8238-475">Informational (4)</span></span>|

<span data-ttu-id="c8238-476">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-476">The following table shows the event information:</span></span>

|<span data-ttu-id="c8238-477">Event</span><span class="sxs-lookup"><span data-stu-id="c8238-477">Event</span></span>|<span data-ttu-id="c8238-478">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c8238-478">Event ID</span></span>|<span data-ttu-id="c8238-479">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c8238-479">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="c8238-480">12</span><span class="sxs-lookup"><span data-stu-id="c8238-480">12</span></span>|<span data-ttu-id="c8238-481">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-481">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="c8238-482">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8238-482">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8238-483">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8238-483">See also</span></span>

- [<span data-ttu-id="c8238-484">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c8238-484">CLR ETW Events</span></span>](clr-etw-events.md)
