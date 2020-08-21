---
title: 가비지 컬렉션 ETW 이벤트
description: 가비지 수집 ETW 이벤트에 대 한 자세한 정보를 확인 합니다. 여기에 포함 된 이벤트에는 GCStart_V1, GCEnd_V1, GCHeapStats_V1, GCCreateSegment_V1 등이 포함 됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 2e1e0fda5c1a80627c8dde7f49954a867b9a2b66
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720139"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="d8a33-104">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="d8a33-105">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="d8a33-106">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="d8a33-107">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="d8a33-108">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="d8a33-109">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="d8a33-110">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="d8a33-111">GCHeapStats_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-111">GCHeapStats_V2 Event</span></span>](#gcheapstats_v2-event)
- [<span data-ttu-id="d8a33-112">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-112">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="d8a33-113">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-113">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="d8a33-114">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-114">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="d8a33-115">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-115">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="d8a33-116">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-116">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="d8a33-117">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-117">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="d8a33-118">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-118">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="d8a33-119">GCAllocationTick_V3 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-119">GCAllocationTick_V3 Event</span></span>](#gcallocationtick_v3-event)
- [<span data-ttu-id="d8a33-120">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-120">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="d8a33-121">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-121">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="d8a33-122">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-122">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="d8a33-123">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-123">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="d8a33-124">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-124">GCStart_V1 Event</span></span>  

<span data-ttu-id="d8a33-125">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-125">The following table shows the keyword and level.</span></span> <span data-ttu-id="d8a33-126">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8a33-126">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="d8a33-127">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-127">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-128">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-128">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-129">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-129">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-130">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-130">Informational (4)</span></span>|

<span data-ttu-id="d8a33-131">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-131">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-132">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-132">Event</span></span>|<span data-ttu-id="d8a33-133">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-133">Event ID</span></span>|<span data-ttu-id="d8a33-134">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-134">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="d8a33-135">1</span><span class="sxs-lookup"><span data-stu-id="d8a33-135">1</span></span>|<span data-ttu-id="d8a33-136">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-136">A garbage collection has started.</span></span>|

<span data-ttu-id="d8a33-137">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-137">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-138">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-138">Field name</span></span>|<span data-ttu-id="d8a33-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-139">Data type</span></span>|<span data-ttu-id="d8a33-140">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-140">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-141">개수</span><span class="sxs-lookup"><span data-stu-id="d8a33-141">Count</span></span>|<span data-ttu-id="d8a33-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-142">win:UInt32</span></span>|<span data-ttu-id="d8a33-143">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-143">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="d8a33-144">깊이</span><span class="sxs-lookup"><span data-stu-id="d8a33-144">Depth</span></span>|<span data-ttu-id="d8a33-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-145">win:UInt32</span></span>|<span data-ttu-id="d8a33-146">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-146">The generation that is being collected.</span></span>|
|<span data-ttu-id="d8a33-147">이유</span><span class="sxs-lookup"><span data-stu-id="d8a33-147">Reason</span></span>|<span data-ttu-id="d8a33-148">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-148">win:UInt32</span></span>|<span data-ttu-id="d8a33-149">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-149">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="d8a33-150">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="d8a33-150">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="d8a33-151">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="d8a33-151">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="d8a33-152">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="d8a33-152">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="d8a33-153">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="d8a33-153">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="d8a33-154">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="d8a33-154">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="d8a33-155">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="d8a33-155">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="d8a33-156">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="d8a33-156">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="d8a33-157">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="d8a33-157">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="d8a33-158">유형</span><span class="sxs-lookup"><span data-stu-id="d8a33-158">Type</span></span>|<span data-ttu-id="d8a33-159">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-159">win:UInt32</span></span>|<span data-ttu-id="d8a33-160">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="d8a33-160">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="d8a33-161">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="d8a33-161">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="d8a33-162">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="d8a33-162">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="d8a33-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-163">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-164">win:UInt16</span></span>|<span data-ttu-id="d8a33-165">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="d8a33-166">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-166">GCEnd_V1 Event</span></span>

<span data-ttu-id="d8a33-167">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-167">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-168">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-168">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-169">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-169">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-170">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-170">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-171">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-171">Informational (4)</span></span>|

<span data-ttu-id="d8a33-172">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-172">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-173">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-173">Event</span></span>|<span data-ttu-id="d8a33-174">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-174">Event ID</span></span>|<span data-ttu-id="d8a33-175">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-175">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="d8a33-176">2</span><span class="sxs-lookup"><span data-stu-id="d8a33-176">2</span></span>|<span data-ttu-id="d8a33-177">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-177">The garbage collection has ended.</span></span>|

<span data-ttu-id="d8a33-178">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-178">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-179">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-179">Field name</span></span>|<span data-ttu-id="d8a33-180">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-180">Data type</span></span>|<span data-ttu-id="d8a33-181">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-181">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-182">개수</span><span class="sxs-lookup"><span data-stu-id="d8a33-182">Count</span></span>|<span data-ttu-id="d8a33-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-183">win:UInt32</span></span>|<span data-ttu-id="d8a33-184">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-184">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="d8a33-185">깊이</span><span class="sxs-lookup"><span data-stu-id="d8a33-185">Depth</span></span>|<span data-ttu-id="d8a33-186">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-186">win:UInt32</span></span>|<span data-ttu-id="d8a33-187">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-187">The generation that was collected.</span></span>|
|<span data-ttu-id="d8a33-188">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-188">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-189">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-189">win:UInt16</span></span>|<span data-ttu-id="d8a33-190">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-190">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="d8a33-191">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-191">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="d8a33-192">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-192">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-193">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-193">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-194">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-194">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-195">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-195">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-196">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-196">Informational (4)</span></span>|

<span data-ttu-id="d8a33-197">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-197">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-198">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-198">Event</span></span>|<span data-ttu-id="d8a33-199">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-199">Event ID</span></span>|<span data-ttu-id="d8a33-200">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-200">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="d8a33-201">4</span><span class="sxs-lookup"><span data-stu-id="d8a33-201">4</span></span>|<span data-ttu-id="d8a33-202">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-202">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="d8a33-203">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-203">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-204">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-204">Field name</span></span>|<span data-ttu-id="d8a33-205">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-205">Data type</span></span>|<span data-ttu-id="d8a33-206">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-206">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-207">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="d8a33-207">GenerationSize0</span></span>|<span data-ttu-id="d8a33-208">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-208">win:UInt64</span></span>|<span data-ttu-id="d8a33-209">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-209">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="d8a33-210">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="d8a33-210">TotalPromotedSize0</span></span>|<span data-ttu-id="d8a33-211">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-211">win:UInt64</span></span>|<span data-ttu-id="d8a33-212">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-212">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="d8a33-213">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="d8a33-213">GenerationSize1</span></span>|<span data-ttu-id="d8a33-214">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-214">win:UInt64</span></span>|<span data-ttu-id="d8a33-215">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-215">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="d8a33-216">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="d8a33-216">TotalPromotedSize1</span></span>|<span data-ttu-id="d8a33-217">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-217">win:UInt64</span></span>|<span data-ttu-id="d8a33-218">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-218">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="d8a33-219">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="d8a33-219">GenerationSize2</span></span>|<span data-ttu-id="d8a33-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-220">win:UInt64</span></span>|<span data-ttu-id="d8a33-221">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-221">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="d8a33-222">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="d8a33-222">TotalPromotedSize2</span></span>|<span data-ttu-id="d8a33-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-223">win:UInt64</span></span>|<span data-ttu-id="d8a33-224">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-224">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="d8a33-225">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="d8a33-225">GenerationSize3</span></span>|<span data-ttu-id="d8a33-226">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-226">win:UInt64</span></span>|<span data-ttu-id="d8a33-227">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-227">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="d8a33-228">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="d8a33-228">TotalPromotedSize3</span></span>|<span data-ttu-id="d8a33-229">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-229">win:UInt64</span></span>|<span data-ttu-id="d8a33-230">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-230">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="d8a33-231">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="d8a33-231">FinalizationPromotedSize</span></span>|<span data-ttu-id="d8a33-232">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-232">win:UInt64</span></span>|<span data-ttu-id="d8a33-233">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-233">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="d8a33-234">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-234">FinalizationPromotedCount</span></span>|<span data-ttu-id="d8a33-235">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-235">win:UInt64</span></span>|<span data-ttu-id="d8a33-236">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-236">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="d8a33-237">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-237">PinnedObjectCount</span></span>|<span data-ttu-id="d8a33-238">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-238">win:UInt32</span></span>|<span data-ttu-id="d8a33-239">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-239">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="d8a33-240">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-240">SinkBlockCount</span></span>|<span data-ttu-id="d8a33-241">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-241">win:UInt32</span></span>|<span data-ttu-id="d8a33-242">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-242">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="d8a33-243">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-243">GCHandleCount</span></span>|<span data-ttu-id="d8a33-244">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-244">win:UInt32</span></span>|<span data-ttu-id="d8a33-245">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-245">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="d8a33-246">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-246">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-247">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-247">win:UInt16</span></span>|<span data-ttu-id="d8a33-248">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-248">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gcheapstats_v2-event"></a><span data-ttu-id="d8a33-249">GCHeapStats_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-249">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="d8a33-250">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-250">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-251">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-251">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-252">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-252">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-253">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-253">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-254">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-254">Informational (4)</span></span>|

<span data-ttu-id="d8a33-255">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-255">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-256">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-256">Event</span></span>|<span data-ttu-id="d8a33-257">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-257">Event ID</span></span>|<span data-ttu-id="d8a33-258">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-258">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="d8a33-259">4</span><span class="sxs-lookup"><span data-stu-id="d8a33-259">4</span></span>|<span data-ttu-id="d8a33-260">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-260">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="d8a33-261">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-261">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-262">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-262">Field name</span></span>|<span data-ttu-id="d8a33-263">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-263">Data type</span></span>|<span data-ttu-id="d8a33-264">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-264">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-265">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="d8a33-265">GenerationSize0</span></span>|<span data-ttu-id="d8a33-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-266">win:UInt64</span></span>|<span data-ttu-id="d8a33-267">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-267">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="d8a33-268">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="d8a33-268">TotalPromotedSize0</span></span>|<span data-ttu-id="d8a33-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-269">win:UInt64</span></span>|<span data-ttu-id="d8a33-270">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-270">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="d8a33-271">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="d8a33-271">GenerationSize1</span></span>|<span data-ttu-id="d8a33-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-272">win:UInt64</span></span>|<span data-ttu-id="d8a33-273">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-273">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="d8a33-274">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="d8a33-274">TotalPromotedSize1</span></span>|<span data-ttu-id="d8a33-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-275">win:UInt64</span></span>|<span data-ttu-id="d8a33-276">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-276">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="d8a33-277">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="d8a33-277">GenerationSize2</span></span>|<span data-ttu-id="d8a33-278">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-278">win:UInt64</span></span>|<span data-ttu-id="d8a33-279">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-279">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="d8a33-280">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="d8a33-280">TotalPromotedSize2</span></span>|<span data-ttu-id="d8a33-281">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-281">win:UInt64</span></span>|<span data-ttu-id="d8a33-282">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-282">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="d8a33-283">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="d8a33-283">GenerationSize3</span></span>|<span data-ttu-id="d8a33-284">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-284">win:UInt64</span></span>|<span data-ttu-id="d8a33-285">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-285">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="d8a33-286">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="d8a33-286">TotalPromotedSize3</span></span>|<span data-ttu-id="d8a33-287">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-287">win:UInt64</span></span>|<span data-ttu-id="d8a33-288">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-288">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="d8a33-289">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="d8a33-289">FinalizationPromotedSize</span></span>|<span data-ttu-id="d8a33-290">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-290">win:UInt64</span></span>|<span data-ttu-id="d8a33-291">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-291">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="d8a33-292">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-292">FinalizationPromotedCount</span></span>|<span data-ttu-id="d8a33-293">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-293">win:UInt64</span></span>|<span data-ttu-id="d8a33-294">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-294">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="d8a33-295">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-295">PinnedObjectCount</span></span>|<span data-ttu-id="d8a33-296">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-296">win:UInt32</span></span>|<span data-ttu-id="d8a33-297">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-297">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="d8a33-298">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-298">SinkBlockCount</span></span>|<span data-ttu-id="d8a33-299">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-299">win:UInt32</span></span>|<span data-ttu-id="d8a33-300">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-300">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="d8a33-301">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="d8a33-301">GCHandleCount</span></span>|<span data-ttu-id="d8a33-302">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-302">win:UInt32</span></span>|<span data-ttu-id="d8a33-303">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-303">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="d8a33-304">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-304">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-305">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-305">win:UInt16</span></span>|<span data-ttu-id="d8a33-306">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-306">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="d8a33-307">GenerationSize4</span><span class="sxs-lookup"><span data-stu-id="d8a33-307">GenerationSize4</span></span>|<span data-ttu-id="d8a33-308">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-308">win:UInt64</span></span>|<span data-ttu-id="d8a33-309">고정 된 개체 힙의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-309">The size, in bytes, of the pinned object heap.</span></span>|
|<span data-ttu-id="d8a33-310">TotalPromotedSize4</span><span class="sxs-lookup"><span data-stu-id="d8a33-310">TotalPromotedSize4</span></span>|<span data-ttu-id="d8a33-311">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-311">win:UInt64</span></span>|<span data-ttu-id="d8a33-312">마지막 수집 이후 고정 된 개체 힙에서 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-312">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="d8a33-313">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-313">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="d8a33-314">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-315">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-315">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-316">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-318">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-318">Informational (4)</span></span>|

<span data-ttu-id="d8a33-319">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-319">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-320">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-320">Event</span></span>|<span data-ttu-id="d8a33-321">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-321">Event ID</span></span>|<span data-ttu-id="d8a33-322">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="d8a33-323">5</span><span class="sxs-lookup"><span data-stu-id="d8a33-323">5</span></span>|<span data-ttu-id="d8a33-324">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-324">A new garbage collection segment has been created.</span></span> <span data-ttu-id="d8a33-325">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-325">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="d8a33-326">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-326">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-327">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-327">Field name</span></span>|<span data-ttu-id="d8a33-328">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-328">Data type</span></span>|<span data-ttu-id="d8a33-329">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-329">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-330">주소</span><span class="sxs-lookup"><span data-stu-id="d8a33-330">Address</span></span>|<span data-ttu-id="d8a33-331">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-331">win:UInt64</span></span>|<span data-ttu-id="d8a33-332">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-332">The address of the segment.</span></span>|
|<span data-ttu-id="d8a33-333">크기</span><span class="sxs-lookup"><span data-stu-id="d8a33-333">Size</span></span>|<span data-ttu-id="d8a33-334">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-334">win:UInt64</span></span>|<span data-ttu-id="d8a33-335">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-335">The size of the segment.</span></span>|
|<span data-ttu-id="d8a33-336">유형</span><span class="sxs-lookup"><span data-stu-id="d8a33-336">Type</span></span>|<span data-ttu-id="d8a33-337">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-337">win:UInt32</span></span>|<span data-ttu-id="d8a33-338">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="d8a33-338">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="d8a33-339">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="d8a33-339">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="d8a33-340">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="d8a33-340">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="d8a33-341">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-341">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-342">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-342">win:UInt16</span></span>|<span data-ttu-id="d8a33-343">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-343">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="d8a33-344">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-344">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="d8a33-345">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-345">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="d8a33-346">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-346">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="d8a33-347">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-347">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-348">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-348">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-349">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-349">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-350">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-350">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-351">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-351">Informational (4)</span></span>|

<span data-ttu-id="d8a33-352">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-352">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-353">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-353">Event</span></span>|<span data-ttu-id="d8a33-354">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-354">Event ID</span></span>|<span data-ttu-id="d8a33-355">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="d8a33-356">6</span><span class="sxs-lookup"><span data-stu-id="d8a33-356">6</span></span>|<span data-ttu-id="d8a33-357">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-357">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="d8a33-358">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-358">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-359">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-359">Field name</span></span>|<span data-ttu-id="d8a33-360">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-360">Data type</span></span>|<span data-ttu-id="d8a33-361">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-361">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-362">주소</span><span class="sxs-lookup"><span data-stu-id="d8a33-362">Address</span></span>|<span data-ttu-id="d8a33-363">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-363">win:UInt64</span></span>|<span data-ttu-id="d8a33-364">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-364">The address of the segment.</span></span>|
|<span data-ttu-id="d8a33-365">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-365">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-366">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-366">win:UInt16</span></span>|<span data-ttu-id="d8a33-367">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-367">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="d8a33-368">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-368">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="d8a33-369">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-369">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-370">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-370">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-371">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-371">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-372">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-372">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-373">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-373">Informational (4)</span></span>|

<span data-ttu-id="d8a33-374">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-374">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-375">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-375">Event</span></span>|<span data-ttu-id="d8a33-376">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-376">Event ID</span></span>|<span data-ttu-id="d8a33-377">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-377">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="d8a33-378">7</span><span class="sxs-lookup"><span data-stu-id="d8a33-378">7</span></span>|<span data-ttu-id="d8a33-379">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-379">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="d8a33-380">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-380">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="d8a33-381">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-381">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="d8a33-382">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-382">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-383">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-383">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-384">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-384">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-385">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-385">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-386">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-386">Informational (4)</span></span>|

<span data-ttu-id="d8a33-387">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-387">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-388">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-388">Event</span></span>|<span data-ttu-id="d8a33-389">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-389">Event Id</span></span>|<span data-ttu-id="d8a33-390">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-390">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="d8a33-391">3</span><span class="sxs-lookup"><span data-stu-id="d8a33-391">3</span></span>|<span data-ttu-id="d8a33-392">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-392">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="d8a33-393">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-393">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="d8a33-394">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-394">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="d8a33-395">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-395">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-396">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-396">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-397">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-397">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-398">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-398">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-399">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-399">Informational (4)</span></span>|

<span data-ttu-id="d8a33-400">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-400">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-401">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-401">Event</span></span>|<span data-ttu-id="d8a33-402">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-402">Event ID</span></span>|<span data-ttu-id="d8a33-403">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-403">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="d8a33-404">9</span><span class="sxs-lookup"><span data-stu-id="d8a33-404">9</span></span>|<span data-ttu-id="d8a33-405">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-405">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="d8a33-406">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-406">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-407">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-407">Field name</span></span>|<span data-ttu-id="d8a33-408">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-408">Data type</span></span>|<span data-ttu-id="d8a33-409">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-409">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-410">이유</span><span class="sxs-lookup"><span data-stu-id="d8a33-410">Reason</span></span>|<span data-ttu-id="d8a33-411">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-411">win:UInt16</span></span>|<span data-ttu-id="d8a33-412">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="d8a33-412">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="d8a33-413">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="d8a33-413">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="d8a33-414">0x2 - 애플리케이션 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="d8a33-414">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="d8a33-415">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="d8a33-415">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="d8a33-416">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="d8a33-416">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="d8a33-417">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="d8a33-417">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="d8a33-418">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="d8a33-418">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="d8a33-419">개수</span><span class="sxs-lookup"><span data-stu-id="d8a33-419">Count</span></span>|<span data-ttu-id="d8a33-420">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-420">win:UInt32</span></span>|<span data-ttu-id="d8a33-421">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-421">The GC count at the time.</span></span> <span data-ttu-id="d8a33-422">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-422">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="d8a33-423">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-423">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-424">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-424">win:UInt16</span></span>|<span data-ttu-id="d8a33-425">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-425">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="d8a33-426">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-426">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="d8a33-427">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-427">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-428">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-428">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-429">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-429">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-431">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-431">Informational (4)</span></span>|

<span data-ttu-id="d8a33-432">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-432">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-433">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-433">Event</span></span>|<span data-ttu-id="d8a33-434">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-434">Event ID</span></span>|<span data-ttu-id="d8a33-435">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-435">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="d8a33-436">8</span><span class="sxs-lookup"><span data-stu-id="d8a33-436">8</span></span>|<span data-ttu-id="d8a33-437">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-437">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="d8a33-438">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-438">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="d8a33-439">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-439">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="d8a33-440">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-440">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-441">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-441">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-442">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-442">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-443">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-443">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-444">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-444">Informational (4)</span></span>|

<span data-ttu-id="d8a33-445">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-445">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-446">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-446">Event</span></span>|<span data-ttu-id="d8a33-447">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-447">Event ID</span></span>|<span data-ttu-id="d8a33-448">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-448">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="d8a33-449">10</span><span class="sxs-lookup"><span data-stu-id="d8a33-449">10</span></span>|<span data-ttu-id="d8a33-450">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-450">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="d8a33-451">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-451">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-452">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-452">Field name</span></span>|<span data-ttu-id="d8a33-453">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-453">Data type</span></span>|<span data-ttu-id="d8a33-454">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-454">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-455">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="d8a33-455">AllocationAmount</span></span>|<span data-ttu-id="d8a33-456">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-456">win:UInt32</span></span>|<span data-ttu-id="d8a33-457">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-457">The allocation size, in bytes.</span></span> <span data-ttu-id="d8a33-458">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-458">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="d8a33-459">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-459">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="d8a33-460">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d8a33-460">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="d8a33-461">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="d8a33-461">AllocationKind</span></span>|<span data-ttu-id="d8a33-462">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-462">win:UInt32</span></span>|<span data-ttu-id="d8a33-463">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="d8a33-463">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="d8a33-464">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="d8a33-464">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="d8a33-465">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-465">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-466">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-466">win:UInt16</span></span>|<span data-ttu-id="d8a33-467">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-467">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="d8a33-468">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="d8a33-468">AllocationAmount64</span></span>|<span data-ttu-id="d8a33-469">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-469">win:UInt64</span></span>|<span data-ttu-id="d8a33-470">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-470">The allocation size, in bytes.</span></span> <span data-ttu-id="d8a33-471">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-471">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="d8a33-472">TypeId</span><span class="sxs-lookup"><span data-stu-id="d8a33-472">TypeId</span></span>|<span data-ttu-id="d8a33-473">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="d8a33-473">win:Pointer</span></span>|<span data-ttu-id="d8a33-474">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-474">The address of the MethodTable.</span></span> <span data-ttu-id="d8a33-475">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-475">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="d8a33-476">TypeName</span><span class="sxs-lookup"><span data-stu-id="d8a33-476">TypeName</span></span>|<span data-ttu-id="d8a33-477">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d8a33-477">win:UnicodeString</span></span>|<span data-ttu-id="d8a33-478">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-478">The name of the type that was allocated.</span></span> <span data-ttu-id="d8a33-479">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-479">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="d8a33-480">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="d8a33-480">HeapIndex</span></span>|<span data-ttu-id="d8a33-481">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-481">win:UInt32</span></span>|<span data-ttu-id="d8a33-482">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-482">The heap where the object was allocated.</span></span> <span data-ttu-id="d8a33-483">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-483">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="d8a33-484">GCAllocationTick_V3 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-484">GCAllocationTick_V3 Event</span></span>

<span data-ttu-id="d8a33-485">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-485">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-486">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-486">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-487">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-487">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-488">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-488">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-489">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-489">Informational (4)</span></span>|

<span data-ttu-id="d8a33-490">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-490">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-491">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-491">Event</span></span>|<span data-ttu-id="d8a33-492">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-492">Event ID</span></span>|<span data-ttu-id="d8a33-493">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-493">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="d8a33-494">10</span><span class="sxs-lookup"><span data-stu-id="d8a33-494">10</span></span>|<span data-ttu-id="d8a33-495">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-495">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="d8a33-496">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-496">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-497">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-497">Field name</span></span>|<span data-ttu-id="d8a33-498">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-498">Data type</span></span>|<span data-ttu-id="d8a33-499">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-499">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-500">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="d8a33-500">AllocationAmount</span></span>|<span data-ttu-id="d8a33-501">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-501">win:UInt32</span></span>|<span data-ttu-id="d8a33-502">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-502">The allocation size, in bytes.</span></span> <span data-ttu-id="d8a33-503">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-503">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="d8a33-504">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-504">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="d8a33-505">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d8a33-505">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="d8a33-506">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="d8a33-506">AllocationKind</span></span>|<span data-ttu-id="d8a33-507">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-507">win:UInt32</span></span>|<span data-ttu-id="d8a33-508">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="d8a33-508">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="d8a33-509">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="d8a33-509">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="d8a33-510">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-510">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-511">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-511">win:UInt16</span></span>|<span data-ttu-id="d8a33-512">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-512">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="d8a33-513">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="d8a33-513">AllocationAmount64</span></span>|<span data-ttu-id="d8a33-514">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d8a33-514">win:UInt64</span></span>|<span data-ttu-id="d8a33-515">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-515">The allocation size, in bytes.</span></span> <span data-ttu-id="d8a33-516">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-516">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="d8a33-517">TypeId</span><span class="sxs-lookup"><span data-stu-id="d8a33-517">TypeId</span></span>|<span data-ttu-id="d8a33-518">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="d8a33-518">win:Pointer</span></span>|<span data-ttu-id="d8a33-519">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-519">The address of the MethodTable.</span></span> <span data-ttu-id="d8a33-520">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-520">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="d8a33-521">TypeName</span><span class="sxs-lookup"><span data-stu-id="d8a33-521">TypeName</span></span>|<span data-ttu-id="d8a33-522">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d8a33-522">win:UnicodeString</span></span>|<span data-ttu-id="d8a33-523">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-523">The name of the type that was allocated.</span></span> <span data-ttu-id="d8a33-524">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-524">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="d8a33-525">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="d8a33-525">HeapIndex</span></span>|<span data-ttu-id="d8a33-526">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-526">win:UInt32</span></span>|<span data-ttu-id="d8a33-527">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-527">The heap where the object was allocated.</span></span> <span data-ttu-id="d8a33-528">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-528">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|<span data-ttu-id="d8a33-529">주소</span><span class="sxs-lookup"><span data-stu-id="d8a33-529">Address</span></span>|<span data-ttu-id="d8a33-530">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="d8a33-530">win:Pointer</span></span>|<span data-ttu-id="d8a33-531">마지막으로 할당 된 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-531">The address of the last allocated object.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="d8a33-532">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-532">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="d8a33-533">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-533">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-534">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-534">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-535">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-535">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-536">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-536">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-537">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-537">Informational (4)</span></span>|

<span data-ttu-id="d8a33-538">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-538">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-539">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-539">Event</span></span>|<span data-ttu-id="d8a33-540">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-540">Event ID</span></span>|<span data-ttu-id="d8a33-541">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-541">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="d8a33-542">14</span><span class="sxs-lookup"><span data-stu-id="d8a33-542">14</span></span>|<span data-ttu-id="d8a33-543">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-543">The start of running finalizers.</span></span>|

<span data-ttu-id="d8a33-544">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-544">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="d8a33-545">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-545">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="d8a33-546">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-546">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-547">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-547">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-548">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-548">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-549">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-549">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-550">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-550">Informational (4)</span></span>|

<span data-ttu-id="d8a33-551">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-551">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-552">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-552">Event</span></span>|<span data-ttu-id="d8a33-553">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-553">Event ID</span></span>|<span data-ttu-id="d8a33-554">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-554">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="d8a33-555">13</span><span class="sxs-lookup"><span data-stu-id="d8a33-555">13</span></span>|<span data-ttu-id="d8a33-556">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-556">The end of running finalizers.</span></span>|

<span data-ttu-id="d8a33-557">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-557">The following table shows the event data:</span></span>

|<span data-ttu-id="d8a33-558">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d8a33-558">Field name</span></span>|<span data-ttu-id="d8a33-559">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8a33-559">Data type</span></span>|<span data-ttu-id="d8a33-560">Description</span><span class="sxs-lookup"><span data-stu-id="d8a33-560">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="d8a33-561">개수</span><span class="sxs-lookup"><span data-stu-id="d8a33-561">Count</span></span>|<span data-ttu-id="d8a33-562">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d8a33-562">win:UInt32</span></span>|<span data-ttu-id="d8a33-563">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-563">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="d8a33-564">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d8a33-564">ClrInstanceID</span></span>|<span data-ttu-id="d8a33-565">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d8a33-565">win:UInt16</span></span>|<span data-ttu-id="d8a33-566">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-566">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="d8a33-567">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-567">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="d8a33-568">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-568">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-569">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-569">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-570">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-570">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-571">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-571">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-572">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-572">Informational (4)</span></span>|
|<span data-ttu-id="d8a33-573">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d8a33-573">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d8a33-574">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-574">Informational (4)</span></span>|

<span data-ttu-id="d8a33-575">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-575">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-576">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-576">Event</span></span>|<span data-ttu-id="d8a33-577">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-577">Event ID</span></span>|<span data-ttu-id="d8a33-578">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-578">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="d8a33-579">11</span><span class="sxs-lookup"><span data-stu-id="d8a33-579">11</span></span>|<span data-ttu-id="d8a33-580">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-580">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="d8a33-581">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-581">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="d8a33-582">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="d8a33-582">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="d8a33-583">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-583">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="d8a33-584">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d8a33-584">Keyword for raising the event</span></span>|<span data-ttu-id="d8a33-585">Level</span><span class="sxs-lookup"><span data-stu-id="d8a33-585">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d8a33-586">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="d8a33-586">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="d8a33-587">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-587">Informational (4)</span></span>|
|<span data-ttu-id="d8a33-588">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d8a33-588">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d8a33-589">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d8a33-589">Informational (4)</span></span>|

<span data-ttu-id="d8a33-590">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-590">The following table shows the event information:</span></span>

|<span data-ttu-id="d8a33-591">이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-591">Event</span></span>|<span data-ttu-id="d8a33-592">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d8a33-592">Event ID</span></span>|<span data-ttu-id="d8a33-593">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d8a33-593">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="d8a33-594">12</span><span class="sxs-lookup"><span data-stu-id="d8a33-594">12</span></span>|<span data-ttu-id="d8a33-595">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-595">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="d8a33-596">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8a33-596">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8a33-597">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8a33-597">See also</span></span>

- [<span data-ttu-id="d8a33-598">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8a33-598">CLR ETW Events</span></span>](clr-etw-events.md)
