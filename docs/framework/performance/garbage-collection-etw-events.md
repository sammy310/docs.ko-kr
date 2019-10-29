---
title: 가비지 컬렉션 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040578"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="ab16c-102">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="ab16c-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="ab16c-103">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="ab16c-104">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="ab16c-105">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="ab16c-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="ab16c-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="ab16c-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="ab16c-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="ab16c-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="ab16c-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="ab16c-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="ab16c-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="ab16c-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="ab16c-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="ab16c-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="ab16c-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="ab16c-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="ab16c-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="ab16c-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="ab16c-121">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="ab16c-122">자세한 내용은 [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab16c-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="ab16c-123">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-123">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-124">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-126">Informational (4)</span></span>|

<span data-ttu-id="ab16c-127">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-127">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-128">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-128">Event</span></span>|<span data-ttu-id="ab16c-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-129">Event ID</span></span>|<span data-ttu-id="ab16c-130">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="ab16c-131">1</span><span class="sxs-lookup"><span data-stu-id="ab16c-131">1</span></span>|<span data-ttu-id="ab16c-132">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-132">A garbage collection has started.</span></span>|

<span data-ttu-id="ab16c-133">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-133">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-134">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-134">Field name</span></span>|<span data-ttu-id="ab16c-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-135">Data type</span></span>|<span data-ttu-id="ab16c-136">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-137">개수</span><span class="sxs-lookup"><span data-stu-id="ab16c-137">Count</span></span>|<span data-ttu-id="ab16c-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-138">win:UInt32</span></span>|<span data-ttu-id="ab16c-139">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="ab16c-140">깊이</span><span class="sxs-lookup"><span data-stu-id="ab16c-140">Depth</span></span>|<span data-ttu-id="ab16c-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-141">win:UInt32</span></span>|<span data-ttu-id="ab16c-142">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="ab16c-143">Reason</span><span class="sxs-lookup"><span data-stu-id="ab16c-143">Reason</span></span>|<span data-ttu-id="ab16c-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-144">win:UInt32</span></span>|<span data-ttu-id="ab16c-145">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="ab16c-146">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="ab16c-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="ab16c-147">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="ab16c-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="ab16c-148">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="ab16c-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="ab16c-149">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="ab16c-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="ab16c-150">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="ab16c-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="ab16c-151">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="ab16c-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="ab16c-152">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="ab16c-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="ab16c-153">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="ab16c-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="ab16c-154">Type</span><span class="sxs-lookup"><span data-stu-id="ab16c-154">Type</span></span>|<span data-ttu-id="ab16c-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-155">win:UInt32</span></span>|<span data-ttu-id="ab16c-156">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="ab16c-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="ab16c-157">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="ab16c-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="ab16c-158">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="ab16c-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="ab16c-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-159">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-160">win:UInt16</span></span>|<span data-ttu-id="ab16c-161">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="ab16c-162">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="ab16c-163">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-164">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-164">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-165">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-167">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-167">Informational (4)</span></span>|

<span data-ttu-id="ab16c-168">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-168">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-169">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-169">Event</span></span>|<span data-ttu-id="ab16c-170">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-170">Event ID</span></span>|<span data-ttu-id="ab16c-171">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="ab16c-172">2</span><span class="sxs-lookup"><span data-stu-id="ab16c-172">2</span></span>|<span data-ttu-id="ab16c-173">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="ab16c-174">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-174">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-175">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-175">Field name</span></span>|<span data-ttu-id="ab16c-176">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-176">Data type</span></span>|<span data-ttu-id="ab16c-177">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-178">개수</span><span class="sxs-lookup"><span data-stu-id="ab16c-178">Count</span></span>|<span data-ttu-id="ab16c-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-179">win:UInt32</span></span>|<span data-ttu-id="ab16c-180">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="ab16c-181">깊이</span><span class="sxs-lookup"><span data-stu-id="ab16c-181">Depth</span></span>|<span data-ttu-id="ab16c-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-182">win:UInt32</span></span>|<span data-ttu-id="ab16c-183">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-183">The generation that was collected.</span></span>|
|<span data-ttu-id="ab16c-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-184">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-185">win:UInt16</span></span>|<span data-ttu-id="ab16c-186">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="ab16c-187">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="ab16c-188">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-189">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-189">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-190">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-192">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-192">Informational (4)</span></span>|

<span data-ttu-id="ab16c-193">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-193">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-194">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-194">Event</span></span>|<span data-ttu-id="ab16c-195">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-195">Event ID</span></span>|<span data-ttu-id="ab16c-196">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="ab16c-197">4</span><span class="sxs-lookup"><span data-stu-id="ab16c-197">4</span></span>|<span data-ttu-id="ab16c-198">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="ab16c-199">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-199">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-200">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-200">Field name</span></span>|<span data-ttu-id="ab16c-201">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-201">Data type</span></span>|<span data-ttu-id="ab16c-202">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="ab16c-203">GenerationSize0</span></span>|<span data-ttu-id="ab16c-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-204">win:UInt64</span></span>|<span data-ttu-id="ab16c-205">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="ab16c-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="ab16c-206">TotalPromotedSize0</span></span>|<span data-ttu-id="ab16c-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-207">win:UInt64</span></span>|<span data-ttu-id="ab16c-208">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="ab16c-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="ab16c-209">GenerationSize1</span></span>|<span data-ttu-id="ab16c-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-210">win:UInt64</span></span>|<span data-ttu-id="ab16c-211">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="ab16c-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="ab16c-212">TotalPromotedSize1</span></span>|<span data-ttu-id="ab16c-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-213">win:UInt64</span></span>|<span data-ttu-id="ab16c-214">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="ab16c-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="ab16c-215">GenerationSize2</span></span>|<span data-ttu-id="ab16c-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-216">win:UInt64</span></span>|<span data-ttu-id="ab16c-217">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="ab16c-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="ab16c-218">TotalPromotedSize2</span></span>|<span data-ttu-id="ab16c-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-219">win:UInt64</span></span>|<span data-ttu-id="ab16c-220">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="ab16c-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="ab16c-221">GenerationSize3</span></span>|<span data-ttu-id="ab16c-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-222">win:UInt64</span></span>|<span data-ttu-id="ab16c-223">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="ab16c-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="ab16c-224">TotalPromotedSize3</span></span>|<span data-ttu-id="ab16c-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-225">win:UInt64</span></span>|<span data-ttu-id="ab16c-226">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="ab16c-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="ab16c-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="ab16c-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-228">win:UInt64</span></span>|<span data-ttu-id="ab16c-229">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="ab16c-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="ab16c-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="ab16c-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-231">win:UInt64</span></span>|<span data-ttu-id="ab16c-232">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="ab16c-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="ab16c-233">PinnedObjectCount</span></span>|<span data-ttu-id="ab16c-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-234">win:UInt32</span></span>|<span data-ttu-id="ab16c-235">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="ab16c-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="ab16c-236">SinkBlockCount</span></span>|<span data-ttu-id="ab16c-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-237">win:UInt32</span></span>|<span data-ttu-id="ab16c-238">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="ab16c-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="ab16c-239">GCHandleCount</span></span>|<span data-ttu-id="ab16c-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-240">win:UInt32</span></span>|<span data-ttu-id="ab16c-241">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="ab16c-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-242">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-243">win:UInt16</span></span>|<span data-ttu-id="ab16c-244">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="ab16c-245">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="ab16c-246">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-247">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-247">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-248">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-250">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-250">Informational (4)</span></span>|

<span data-ttu-id="ab16c-251">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-251">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-252">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-252">Event</span></span>|<span data-ttu-id="ab16c-253">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-253">Event ID</span></span>|<span data-ttu-id="ab16c-254">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="ab16c-255">5</span><span class="sxs-lookup"><span data-stu-id="ab16c-255">5</span></span>|<span data-ttu-id="ab16c-256">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="ab16c-257">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="ab16c-258">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-258">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-259">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-259">Field name</span></span>|<span data-ttu-id="ab16c-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-260">Data type</span></span>|<span data-ttu-id="ab16c-261">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-262">Address</span><span class="sxs-lookup"><span data-stu-id="ab16c-262">Address</span></span>|<span data-ttu-id="ab16c-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-263">win:UInt64</span></span>|<span data-ttu-id="ab16c-264">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-264">The address of the segment.</span></span>|
|<span data-ttu-id="ab16c-265">Size</span><span class="sxs-lookup"><span data-stu-id="ab16c-265">Size</span></span>|<span data-ttu-id="ab16c-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-266">win:UInt64</span></span>|<span data-ttu-id="ab16c-267">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-267">The size of the segment.</span></span>|
|<span data-ttu-id="ab16c-268">Type</span><span class="sxs-lookup"><span data-stu-id="ab16c-268">Type</span></span>|<span data-ttu-id="ab16c-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-269">win:UInt32</span></span>|<span data-ttu-id="ab16c-270">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="ab16c-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="ab16c-271">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="ab16c-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="ab16c-272">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="ab16c-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="ab16c-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-273">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-274">win:UInt16</span></span>|<span data-ttu-id="ab16c-275">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="ab16c-276">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="ab16c-277">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="ab16c-278">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="ab16c-279">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-280">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-280">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-281">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-283">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-283">Informational (4)</span></span>|

<span data-ttu-id="ab16c-284">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-284">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-285">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-285">Event</span></span>|<span data-ttu-id="ab16c-286">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-286">Event ID</span></span>|<span data-ttu-id="ab16c-287">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="ab16c-288">6</span><span class="sxs-lookup"><span data-stu-id="ab16c-288">6</span></span>|<span data-ttu-id="ab16c-289">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="ab16c-290">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-290">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-291">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-291">Field name</span></span>|<span data-ttu-id="ab16c-292">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-292">Data type</span></span>|<span data-ttu-id="ab16c-293">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-294">Address</span><span class="sxs-lookup"><span data-stu-id="ab16c-294">Address</span></span>|<span data-ttu-id="ab16c-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-295">win:UInt64</span></span>|<span data-ttu-id="ab16c-296">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-296">The address of the segment.</span></span>|
|<span data-ttu-id="ab16c-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-297">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-298">win:UInt16</span></span>|<span data-ttu-id="ab16c-299">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="ab16c-300">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="ab16c-301">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-302">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-302">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-303">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-305">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-305">Informational (4)</span></span>|

<span data-ttu-id="ab16c-306">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-306">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-307">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-307">Event</span></span>|<span data-ttu-id="ab16c-308">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-308">Event ID</span></span>|<span data-ttu-id="ab16c-309">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="ab16c-310">7</span><span class="sxs-lookup"><span data-stu-id="ab16c-310">7</span></span>|<span data-ttu-id="ab16c-311">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="ab16c-312">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="ab16c-313">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="ab16c-314">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-315">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-315">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-316">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-318">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-318">Informational (4)</span></span>|

<span data-ttu-id="ab16c-319">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-319">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-320">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-320">Event</span></span>|<span data-ttu-id="ab16c-321">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-321">Event Id</span></span>|<span data-ttu-id="ab16c-322">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="ab16c-323">3</span><span class="sxs-lookup"><span data-stu-id="ab16c-323">3</span></span>|<span data-ttu-id="ab16c-324">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="ab16c-325">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="ab16c-326">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="ab16c-327">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-328">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-328">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-329">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-331">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-331">Informational (4)</span></span>|

<span data-ttu-id="ab16c-332">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-332">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-333">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-333">Event</span></span>|<span data-ttu-id="ab16c-334">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-334">Event ID</span></span>|<span data-ttu-id="ab16c-335">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="ab16c-336">10</span><span class="sxs-lookup"><span data-stu-id="ab16c-336">9</span></span>|<span data-ttu-id="ab16c-337">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="ab16c-338">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-338">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-339">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-339">Field name</span></span>|<span data-ttu-id="ab16c-340">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-340">Data type</span></span>|<span data-ttu-id="ab16c-341">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-342">Reason</span><span class="sxs-lookup"><span data-stu-id="ab16c-342">Reason</span></span>|<span data-ttu-id="ab16c-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-343">win:UInt16</span></span>|<span data-ttu-id="ab16c-344">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="ab16c-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="ab16c-345">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="ab16c-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="ab16c-346">0x2 - 애플리케이션 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="ab16c-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="ab16c-347">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="ab16c-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="ab16c-348">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="ab16c-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="ab16c-349">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="ab16c-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="ab16c-350">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="ab16c-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="ab16c-351">개수</span><span class="sxs-lookup"><span data-stu-id="ab16c-351">Count</span></span>|<span data-ttu-id="ab16c-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-352">win:UInt32</span></span>|<span data-ttu-id="ab16c-353">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-353">The GC count at the time.</span></span> <span data-ttu-id="ab16c-354">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="ab16c-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-355">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-356">win:UInt16</span></span>|<span data-ttu-id="ab16c-357">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="ab16c-358">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="ab16c-359">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-360">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-360">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-361">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-363">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-363">Informational (4)</span></span>|

<span data-ttu-id="ab16c-364">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-364">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-365">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-365">Event</span></span>|<span data-ttu-id="ab16c-366">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-366">Event ID</span></span>|<span data-ttu-id="ab16c-367">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="ab16c-368">8</span><span class="sxs-lookup"><span data-stu-id="ab16c-368">8</span></span>|<span data-ttu-id="ab16c-369">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="ab16c-370">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="ab16c-371">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="ab16c-372">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-373">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-373">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-374">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-376">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-376">Informational (4)</span></span>|

<span data-ttu-id="ab16c-377">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-377">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-378">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-378">Event</span></span>|<span data-ttu-id="ab16c-379">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-379">Event ID</span></span>|<span data-ttu-id="ab16c-380">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="ab16c-381">10</span><span class="sxs-lookup"><span data-stu-id="ab16c-381">10</span></span>|<span data-ttu-id="ab16c-382">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="ab16c-383">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-383">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-384">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-384">Field name</span></span>|<span data-ttu-id="ab16c-385">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-385">Data type</span></span>|<span data-ttu-id="ab16c-386">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="ab16c-387">AllocationAmount</span></span>|<span data-ttu-id="ab16c-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-388">win:UInt32</span></span>|<span data-ttu-id="ab16c-389">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-389">The allocation size, in bytes.</span></span> <span data-ttu-id="ab16c-390">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="ab16c-391">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="ab16c-392">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ab16c-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="ab16c-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="ab16c-393">AllocationKind</span></span>|<span data-ttu-id="ab16c-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-394">win:UInt32</span></span>|<span data-ttu-id="ab16c-395">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="ab16c-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="ab16c-396">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="ab16c-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="ab16c-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-397">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-398">win:UInt16</span></span>|<span data-ttu-id="ab16c-399">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="ab16c-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="ab16c-400">AllocationAmount64</span></span>|<span data-ttu-id="ab16c-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab16c-401">win:UInt64</span></span>|<span data-ttu-id="ab16c-402">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-402">The allocation size, in bytes.</span></span> <span data-ttu-id="ab16c-403">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="ab16c-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="ab16c-404">TypeId</span></span>|<span data-ttu-id="ab16c-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="ab16c-405">win:Pointer</span></span>|<span data-ttu-id="ab16c-406">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-406">The address of the MethodTable.</span></span> <span data-ttu-id="ab16c-407">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="ab16c-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="ab16c-408">TypeName</span></span>|<span data-ttu-id="ab16c-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ab16c-409">win:UnicodeString</span></span>|<span data-ttu-id="ab16c-410">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-410">The name of the type that was allocated.</span></span> <span data-ttu-id="ab16c-411">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="ab16c-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="ab16c-412">HeapIndex</span></span>|<span data-ttu-id="ab16c-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-413">win:UInt32</span></span>|<span data-ttu-id="ab16c-414">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-414">The heap where the object was allocated.</span></span> <span data-ttu-id="ab16c-415">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="ab16c-416">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="ab16c-417">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-418">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-418">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-419">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-421">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-421">Informational (4)</span></span>|

<span data-ttu-id="ab16c-422">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-422">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-423">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-423">Event</span></span>|<span data-ttu-id="ab16c-424">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-424">Event ID</span></span>|<span data-ttu-id="ab16c-425">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="ab16c-426">14</span><span class="sxs-lookup"><span data-stu-id="ab16c-426">14</span></span>|<span data-ttu-id="ab16c-427">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-427">The start of running finalizers.</span></span>|

<span data-ttu-id="ab16c-428">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="ab16c-429">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="ab16c-430">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-431">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-431">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-432">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-434">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-434">Informational (4)</span></span>|

<span data-ttu-id="ab16c-435">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-435">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-436">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-436">Event</span></span>|<span data-ttu-id="ab16c-437">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-437">Event ID</span></span>|<span data-ttu-id="ab16c-438">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="ab16c-439">13</span><span class="sxs-lookup"><span data-stu-id="ab16c-439">13</span></span>|<span data-ttu-id="ab16c-440">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-440">The end of running finalizers.</span></span>|

<span data-ttu-id="ab16c-441">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-441">The following table shows the event data:</span></span>

|<span data-ttu-id="ab16c-442">필드 이름</span><span class="sxs-lookup"><span data-stu-id="ab16c-442">Field name</span></span>|<span data-ttu-id="ab16c-443">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab16c-443">Data type</span></span>|<span data-ttu-id="ab16c-444">설명</span><span class="sxs-lookup"><span data-stu-id="ab16c-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ab16c-445">개수</span><span class="sxs-lookup"><span data-stu-id="ab16c-445">Count</span></span>|<span data-ttu-id="ab16c-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab16c-446">win:UInt32</span></span>|<span data-ttu-id="ab16c-447">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="ab16c-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab16c-448">ClrInstanceID</span></span>|<span data-ttu-id="ab16c-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab16c-449">win:UInt16</span></span>|<span data-ttu-id="ab16c-450">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="ab16c-451">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="ab16c-452">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-453">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-453">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-454">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-456">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-456">Informational (4)</span></span>|
|<span data-ttu-id="ab16c-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ab16c-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ab16c-458">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-458">Informational (4)</span></span>|

<span data-ttu-id="ab16c-459">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-459">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-460">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-460">Event</span></span>|<span data-ttu-id="ab16c-461">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-461">Event ID</span></span>|<span data-ttu-id="ab16c-462">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="ab16c-463">11</span><span class="sxs-lookup"><span data-stu-id="ab16c-463">11</span></span>|<span data-ttu-id="ab16c-464">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="ab16c-465">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="ab16c-466">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="ab16c-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="ab16c-467">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ab16c-468">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="ab16c-468">Keyword for raising the event</span></span>|<span data-ttu-id="ab16c-469">Level</span><span class="sxs-lookup"><span data-stu-id="ab16c-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ab16c-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab16c-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab16c-471">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-471">Informational (4)</span></span>|
|<span data-ttu-id="ab16c-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ab16c-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ab16c-473">정보(4)</span><span class="sxs-lookup"><span data-stu-id="ab16c-473">Informational (4)</span></span>|

<span data-ttu-id="ab16c-474">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-474">The following table shows the event information:</span></span>

|<span data-ttu-id="ab16c-475">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="ab16c-475">Event</span></span>|<span data-ttu-id="ab16c-476">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="ab16c-476">Event ID</span></span>|<span data-ttu-id="ab16c-477">발생 시기</span><span class="sxs-lookup"><span data-stu-id="ab16c-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="ab16c-478">12</span><span class="sxs-lookup"><span data-stu-id="ab16c-478">12</span></span>|<span data-ttu-id="ab16c-479">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="ab16c-480">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab16c-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab16c-481">참조</span><span class="sxs-lookup"><span data-stu-id="ab16c-481">See also</span></span>

- [<span data-ttu-id="ab16c-482">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="ab16c-482">CLR ETW Events</span></span>](clr-etw-events.md)
