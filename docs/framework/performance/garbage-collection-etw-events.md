---
title: 가비지 컬렉션 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 5ff214314b92796f4a4a89ddd33a976d8b1f21d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716063"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="c510a-102">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c510a-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="c510a-103">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="c510a-104">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="c510a-105">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="c510a-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="c510a-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="c510a-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="c510a-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="c510a-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="c510a-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="c510a-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="c510a-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="c510a-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="c510a-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="c510a-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="c510a-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="c510a-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="c510a-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="c510a-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="c510a-121">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="c510a-122">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c510a-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="c510a-123">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-123">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-124">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-126">Informational (4)</span></span>|

<span data-ttu-id="c510a-127">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-127">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-128">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-128">Event</span></span>|<span data-ttu-id="c510a-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-129">Event ID</span></span>|<span data-ttu-id="c510a-130">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="c510a-131">1</span><span class="sxs-lookup"><span data-stu-id="c510a-131">1</span></span>|<span data-ttu-id="c510a-132">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-132">A garbage collection has started.</span></span>|

<span data-ttu-id="c510a-133">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-133">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-134">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-134">Field name</span></span>|<span data-ttu-id="c510a-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-135">Data type</span></span>|<span data-ttu-id="c510a-136">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-137">개수</span><span class="sxs-lookup"><span data-stu-id="c510a-137">Count</span></span>|<span data-ttu-id="c510a-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-138">win:UInt32</span></span>|<span data-ttu-id="c510a-139">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c510a-140">깊이</span><span class="sxs-lookup"><span data-stu-id="c510a-140">Depth</span></span>|<span data-ttu-id="c510a-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-141">win:UInt32</span></span>|<span data-ttu-id="c510a-142">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="c510a-143">Reason</span><span class="sxs-lookup"><span data-stu-id="c510a-143">Reason</span></span>|<span data-ttu-id="c510a-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-144">win:UInt32</span></span>|<span data-ttu-id="c510a-145">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="c510a-146">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="c510a-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="c510a-147">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="c510a-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="c510a-148">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="c510a-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="c510a-149">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="c510a-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="c510a-150">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="c510a-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="c510a-151">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="c510a-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="c510a-152">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="c510a-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="c510a-153">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="c510a-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="c510a-154">형식</span><span class="sxs-lookup"><span data-stu-id="c510a-154">Type</span></span>|<span data-ttu-id="c510a-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-155">win:UInt32</span></span>|<span data-ttu-id="c510a-156">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="c510a-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="c510a-157">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="c510a-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="c510a-158">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="c510a-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="c510a-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-159">ClrInstanceID</span></span>|<span data-ttu-id="c510a-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-160">win:UInt16</span></span>|<span data-ttu-id="c510a-161">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="c510a-162">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="c510a-163">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-164">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-164">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-165">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-167">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-167">Informational (4)</span></span>|

<span data-ttu-id="c510a-168">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-168">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-169">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-169">Event</span></span>|<span data-ttu-id="c510a-170">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-170">Event ID</span></span>|<span data-ttu-id="c510a-171">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="c510a-172">2</span><span class="sxs-lookup"><span data-stu-id="c510a-172">2</span></span>|<span data-ttu-id="c510a-173">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="c510a-174">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-174">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-175">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-175">Field name</span></span>|<span data-ttu-id="c510a-176">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-176">Data type</span></span>|<span data-ttu-id="c510a-177">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-178">개수</span><span class="sxs-lookup"><span data-stu-id="c510a-178">Count</span></span>|<span data-ttu-id="c510a-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-179">win:UInt32</span></span>|<span data-ttu-id="c510a-180">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="c510a-181">깊이</span><span class="sxs-lookup"><span data-stu-id="c510a-181">Depth</span></span>|<span data-ttu-id="c510a-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-182">win:UInt32</span></span>|<span data-ttu-id="c510a-183">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-183">The generation that was collected.</span></span>|
|<span data-ttu-id="c510a-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-184">ClrInstanceID</span></span>|<span data-ttu-id="c510a-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-185">win:UInt16</span></span>|<span data-ttu-id="c510a-186">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="c510a-187">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="c510a-188">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-189">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-189">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-190">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-192">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-192">Informational (4)</span></span>|

<span data-ttu-id="c510a-193">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-193">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-194">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-194">Event</span></span>|<span data-ttu-id="c510a-195">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-195">Event ID</span></span>|<span data-ttu-id="c510a-196">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="c510a-197">4</span><span class="sxs-lookup"><span data-stu-id="c510a-197">4</span></span>|<span data-ttu-id="c510a-198">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="c510a-199">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-199">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-200">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-200">Field name</span></span>|<span data-ttu-id="c510a-201">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-201">Data type</span></span>|<span data-ttu-id="c510a-202">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="c510a-203">GenerationSize0</span></span>|<span data-ttu-id="c510a-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-204">win:UInt64</span></span>|<span data-ttu-id="c510a-205">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="c510a-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="c510a-206">TotalPromotedSize0</span></span>|<span data-ttu-id="c510a-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-207">win:UInt64</span></span>|<span data-ttu-id="c510a-208">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="c510a-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="c510a-209">GenerationSize1</span></span>|<span data-ttu-id="c510a-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-210">win:UInt64</span></span>|<span data-ttu-id="c510a-211">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="c510a-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="c510a-212">TotalPromotedSize1</span></span>|<span data-ttu-id="c510a-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-213">win:UInt64</span></span>|<span data-ttu-id="c510a-214">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="c510a-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="c510a-215">GenerationSize2</span></span>|<span data-ttu-id="c510a-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-216">win:UInt64</span></span>|<span data-ttu-id="c510a-217">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="c510a-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="c510a-218">TotalPromotedSize2</span></span>|<span data-ttu-id="c510a-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-219">win:UInt64</span></span>|<span data-ttu-id="c510a-220">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="c510a-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="c510a-221">GenerationSize3</span></span>|<span data-ttu-id="c510a-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-222">win:UInt64</span></span>|<span data-ttu-id="c510a-223">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="c510a-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="c510a-224">TotalPromotedSize3</span></span>|<span data-ttu-id="c510a-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-225">win:UInt64</span></span>|<span data-ttu-id="c510a-226">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="c510a-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="c510a-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="c510a-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-228">win:UInt64</span></span>|<span data-ttu-id="c510a-229">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c510a-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="c510a-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="c510a-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-231">win:UInt64</span></span>|<span data-ttu-id="c510a-232">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="c510a-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="c510a-233">PinnedObjectCount</span></span>|<span data-ttu-id="c510a-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-234">win:UInt32</span></span>|<span data-ttu-id="c510a-235">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="c510a-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="c510a-236">SinkBlockCount</span></span>|<span data-ttu-id="c510a-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-237">win:UInt32</span></span>|<span data-ttu-id="c510a-238">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="c510a-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="c510a-239">GCHandleCount</span></span>|<span data-ttu-id="c510a-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-240">win:UInt32</span></span>|<span data-ttu-id="c510a-241">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="c510a-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-242">ClrInstanceID</span></span>|<span data-ttu-id="c510a-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-243">win:UInt16</span></span>|<span data-ttu-id="c510a-244">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="c510a-245">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="c510a-246">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-247">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-247">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-248">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-250">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-250">Informational (4)</span></span>|

<span data-ttu-id="c510a-251">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-251">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-252">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-252">Event</span></span>|<span data-ttu-id="c510a-253">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-253">Event ID</span></span>|<span data-ttu-id="c510a-254">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="c510a-255">5</span><span class="sxs-lookup"><span data-stu-id="c510a-255">5</span></span>|<span data-ttu-id="c510a-256">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="c510a-257">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="c510a-258">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-258">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-259">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-259">Field name</span></span>|<span data-ttu-id="c510a-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-260">Data type</span></span>|<span data-ttu-id="c510a-261">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-262">Address</span><span class="sxs-lookup"><span data-stu-id="c510a-262">Address</span></span>|<span data-ttu-id="c510a-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-263">win:UInt64</span></span>|<span data-ttu-id="c510a-264">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-264">The address of the segment.</span></span>|
|<span data-ttu-id="c510a-265">크기</span><span class="sxs-lookup"><span data-stu-id="c510a-265">Size</span></span>|<span data-ttu-id="c510a-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-266">win:UInt64</span></span>|<span data-ttu-id="c510a-267">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-267">The size of the segment.</span></span>|
|<span data-ttu-id="c510a-268">형식</span><span class="sxs-lookup"><span data-stu-id="c510a-268">Type</span></span>|<span data-ttu-id="c510a-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-269">win:UInt32</span></span>|<span data-ttu-id="c510a-270">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="c510a-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="c510a-271">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="c510a-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="c510a-272">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="c510a-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="c510a-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-273">ClrInstanceID</span></span>|<span data-ttu-id="c510a-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-274">win:UInt16</span></span>|<span data-ttu-id="c510a-275">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="c510a-276">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="c510a-277">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="c510a-278">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="c510a-279">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-280">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-280">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-281">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-283">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-283">Informational (4)</span></span>|

<span data-ttu-id="c510a-284">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-284">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-285">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-285">Event</span></span>|<span data-ttu-id="c510a-286">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-286">Event ID</span></span>|<span data-ttu-id="c510a-287">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="c510a-288">6</span><span class="sxs-lookup"><span data-stu-id="c510a-288">6</span></span>|<span data-ttu-id="c510a-289">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="c510a-290">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-290">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-291">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-291">Field name</span></span>|<span data-ttu-id="c510a-292">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-292">Data type</span></span>|<span data-ttu-id="c510a-293">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-294">Address</span><span class="sxs-lookup"><span data-stu-id="c510a-294">Address</span></span>|<span data-ttu-id="c510a-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-295">win:UInt64</span></span>|<span data-ttu-id="c510a-296">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-296">The address of the segment.</span></span>|
|<span data-ttu-id="c510a-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-297">ClrInstanceID</span></span>|<span data-ttu-id="c510a-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-298">win:UInt16</span></span>|<span data-ttu-id="c510a-299">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="c510a-300">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="c510a-301">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-302">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-302">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-303">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-305">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-305">Informational (4)</span></span>|

<span data-ttu-id="c510a-306">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-306">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-307">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-307">Event</span></span>|<span data-ttu-id="c510a-308">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-308">Event ID</span></span>|<span data-ttu-id="c510a-309">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="c510a-310">7</span><span class="sxs-lookup"><span data-stu-id="c510a-310">7</span></span>|<span data-ttu-id="c510a-311">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="c510a-312">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="c510a-313">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="c510a-314">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-315">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-315">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-316">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-318">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-318">Informational (4)</span></span>|

<span data-ttu-id="c510a-319">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-319">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-320">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-320">Event</span></span>|<span data-ttu-id="c510a-321">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-321">Event Id</span></span>|<span data-ttu-id="c510a-322">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="c510a-323">3</span><span class="sxs-lookup"><span data-stu-id="c510a-323">3</span></span>|<span data-ttu-id="c510a-324">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="c510a-325">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="c510a-326">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="c510a-327">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-328">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-328">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-329">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-331">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-331">Informational (4)</span></span>|

<span data-ttu-id="c510a-332">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-332">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-333">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-333">Event</span></span>|<span data-ttu-id="c510a-334">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-334">Event ID</span></span>|<span data-ttu-id="c510a-335">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="c510a-336">10</span><span class="sxs-lookup"><span data-stu-id="c510a-336">9</span></span>|<span data-ttu-id="c510a-337">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c510a-338">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-338">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-339">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-339">Field name</span></span>|<span data-ttu-id="c510a-340">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-340">Data type</span></span>|<span data-ttu-id="c510a-341">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-342">Reason</span><span class="sxs-lookup"><span data-stu-id="c510a-342">Reason</span></span>|<span data-ttu-id="c510a-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-343">win:UInt16</span></span>|<span data-ttu-id="c510a-344">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="c510a-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="c510a-345">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="c510a-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="c510a-346">0x2 - 애플리케이션 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="c510a-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="c510a-347">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="c510a-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="c510a-348">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="c510a-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="c510a-349">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="c510a-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="c510a-350">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="c510a-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="c510a-351">개수</span><span class="sxs-lookup"><span data-stu-id="c510a-351">Count</span></span>|<span data-ttu-id="c510a-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-352">win:UInt32</span></span>|<span data-ttu-id="c510a-353">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-353">The GC count at the time.</span></span> <span data-ttu-id="c510a-354">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="c510a-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-355">ClrInstanceID</span></span>|<span data-ttu-id="c510a-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-356">win:UInt16</span></span>|<span data-ttu-id="c510a-357">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="c510a-358">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="c510a-359">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-360">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-360">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-361">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-363">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-363">Informational (4)</span></span>|

<span data-ttu-id="c510a-364">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-364">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-365">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-365">Event</span></span>|<span data-ttu-id="c510a-366">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-366">Event ID</span></span>|<span data-ttu-id="c510a-367">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="c510a-368">8</span><span class="sxs-lookup"><span data-stu-id="c510a-368">8</span></span>|<span data-ttu-id="c510a-369">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="c510a-370">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="c510a-371">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="c510a-372">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-373">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-373">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-374">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-376">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-376">Informational (4)</span></span>|

<span data-ttu-id="c510a-377">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-377">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-378">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-378">Event</span></span>|<span data-ttu-id="c510a-379">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-379">Event ID</span></span>|<span data-ttu-id="c510a-380">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="c510a-381">10</span><span class="sxs-lookup"><span data-stu-id="c510a-381">10</span></span>|<span data-ttu-id="c510a-382">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="c510a-383">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-383">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-384">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-384">Field name</span></span>|<span data-ttu-id="c510a-385">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-385">Data type</span></span>|<span data-ttu-id="c510a-386">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="c510a-387">AllocationAmount</span></span>|<span data-ttu-id="c510a-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-388">win:UInt32</span></span>|<span data-ttu-id="c510a-389">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-389">The allocation size, in bytes.</span></span> <span data-ttu-id="c510a-390">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="c510a-391">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="c510a-392">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c510a-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="c510a-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="c510a-393">AllocationKind</span></span>|<span data-ttu-id="c510a-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-394">win:UInt32</span></span>|<span data-ttu-id="c510a-395">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="c510a-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="c510a-396">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="c510a-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="c510a-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-397">ClrInstanceID</span></span>|<span data-ttu-id="c510a-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-398">win:UInt16</span></span>|<span data-ttu-id="c510a-399">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="c510a-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="c510a-400">AllocationAmount64</span></span>|<span data-ttu-id="c510a-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c510a-401">win:UInt64</span></span>|<span data-ttu-id="c510a-402">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-402">The allocation size, in bytes.</span></span> <span data-ttu-id="c510a-403">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="c510a-404">유형 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-404">TypeId</span></span>|<span data-ttu-id="c510a-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c510a-405">win:Pointer</span></span>|<span data-ttu-id="c510a-406">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-406">The address of the MethodTable.</span></span> <span data-ttu-id="c510a-407">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c510a-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="c510a-408">TypeName</span></span>|<span data-ttu-id="c510a-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c510a-409">win:UnicodeString</span></span>|<span data-ttu-id="c510a-410">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-410">The name of the type that was allocated.</span></span> <span data-ttu-id="c510a-411">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="c510a-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="c510a-412">HeapIndex</span></span>|<span data-ttu-id="c510a-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-413">win:UInt32</span></span>|<span data-ttu-id="c510a-414">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-414">The heap where the object was allocated.</span></span> <span data-ttu-id="c510a-415">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="c510a-416">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="c510a-417">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-418">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-418">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-419">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-421">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-421">Informational (4)</span></span>|

<span data-ttu-id="c510a-422">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-422">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-423">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-423">Event</span></span>|<span data-ttu-id="c510a-424">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-424">Event ID</span></span>|<span data-ttu-id="c510a-425">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="c510a-426">14</span><span class="sxs-lookup"><span data-stu-id="c510a-426">14</span></span>|<span data-ttu-id="c510a-427">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-427">The start of running finalizers.</span></span>|

<span data-ttu-id="c510a-428">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="c510a-429">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="c510a-430">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-431">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-431">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-432">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-434">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-434">Informational (4)</span></span>|

<span data-ttu-id="c510a-435">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-435">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-436">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-436">Event</span></span>|<span data-ttu-id="c510a-437">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-437">Event ID</span></span>|<span data-ttu-id="c510a-438">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="c510a-439">13</span><span class="sxs-lookup"><span data-stu-id="c510a-439">13</span></span>|<span data-ttu-id="c510a-440">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-440">The end of running finalizers.</span></span>|

<span data-ttu-id="c510a-441">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-441">The following table shows the event data:</span></span>

|<span data-ttu-id="c510a-442">필드 이름</span><span class="sxs-lookup"><span data-stu-id="c510a-442">Field name</span></span>|<span data-ttu-id="c510a-443">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c510a-443">Data type</span></span>|<span data-ttu-id="c510a-444">설명</span><span class="sxs-lookup"><span data-stu-id="c510a-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="c510a-445">개수</span><span class="sxs-lookup"><span data-stu-id="c510a-445">Count</span></span>|<span data-ttu-id="c510a-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c510a-446">win:UInt32</span></span>|<span data-ttu-id="c510a-447">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="c510a-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c510a-448">ClrInstanceID</span></span>|<span data-ttu-id="c510a-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c510a-449">win:UInt16</span></span>|<span data-ttu-id="c510a-450">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="c510a-451">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c510a-452">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-453">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-453">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-454">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-456">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-456">Informational (4)</span></span>|
|<span data-ttu-id="c510a-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c510a-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c510a-458">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-458">Informational (4)</span></span>|

<span data-ttu-id="c510a-459">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-459">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-460">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-460">Event</span></span>|<span data-ttu-id="c510a-461">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-461">Event ID</span></span>|<span data-ttu-id="c510a-462">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="c510a-463">11</span><span class="sxs-lookup"><span data-stu-id="c510a-463">11</span></span>|<span data-ttu-id="c510a-464">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="c510a-465">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="c510a-466">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c510a-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="c510a-467">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="c510a-468">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="c510a-468">Keyword for raising the event</span></span>|<span data-ttu-id="c510a-469">수준</span><span class="sxs-lookup"><span data-stu-id="c510a-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="c510a-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c510a-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c510a-471">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-471">Informational (4)</span></span>|
|<span data-ttu-id="c510a-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c510a-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c510a-473">정보(4)</span><span class="sxs-lookup"><span data-stu-id="c510a-473">Informational (4)</span></span>|

<span data-ttu-id="c510a-474">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-474">The following table shows the event information:</span></span>

|<span data-ttu-id="c510a-475">Event</span><span class="sxs-lookup"><span data-stu-id="c510a-475">Event</span></span>|<span data-ttu-id="c510a-476">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="c510a-476">Event ID</span></span>|<span data-ttu-id="c510a-477">발생 시기</span><span class="sxs-lookup"><span data-stu-id="c510a-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="c510a-478">12</span><span class="sxs-lookup"><span data-stu-id="c510a-478">12</span></span>|<span data-ttu-id="c510a-479">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="c510a-480">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c510a-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="c510a-481">참조</span><span class="sxs-lookup"><span data-stu-id="c510a-481">See also</span></span>

- [<span data-ttu-id="c510a-482">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="c510a-482">CLR ETW Events</span></span>](clr-etw-events.md)
