---
title: 가비지 수집 런타임 이벤트
description: .NET 가비지 수집기와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594057"
---
# <a name="net-runtime-garbage-collection-events"></a><span data-ttu-id="58f88-103">.NET 런타임 가비지 수집 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-103">.NET runtime garbage collection events</span></span>

<span data-ttu-id="58f88-104">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-104">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="58f88-105">가비지 수집 수행 횟수, 가비지 수집 중에 해제 된 메모리 양 등을 확인 하는 등 진단 및 디버깅에 도움이 됩니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58f88-105">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc. For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="gcstart_v2-event"></a><span data-ttu-id="58f88-106">GCStart_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-106">GCStart_V2 Event</span></span>

<span data-ttu-id="58f88-107">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-107">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-108">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-108">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-109">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-110">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-110">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-111">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-111">Informational (4)</span></span>|

<span data-ttu-id="58f88-112">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-112">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-113">Event</span></span>|<span data-ttu-id="58f88-114">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-114">Event ID</span></span>|<span data-ttu-id="58f88-115">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="58f88-116">1</span><span class="sxs-lookup"><span data-stu-id="58f88-116">1</span></span>|<span data-ttu-id="58f88-117">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-117">A garbage collection has started.</span></span>|

<span data-ttu-id="58f88-118">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-118">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-119">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-119">Field name</span></span>|<span data-ttu-id="58f88-120">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-120">Data type</span></span>|<span data-ttu-id="58f88-121">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-121">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="58f88-122">*n* 번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-122">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="58f88-123">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-123">The generation that is being collected.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="58f88-124">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-124">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="58f88-125">`0x0` -작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="58f88-125">`0x0` - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="58f88-126">`0x1` 시킨.</span><span class="sxs-lookup"><span data-stu-id="58f88-126">`0x1` - Induced.</span></span><br /><br /> <span data-ttu-id="58f88-127">`0x2` -메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="58f88-127">`0x2` - Low memory.</span></span><br /><br /> <span data-ttu-id="58f88-128">`0x3` 비우려면.</span><span class="sxs-lookup"><span data-stu-id="58f88-128">`0x3` - Empty.</span></span><br /><br /> <span data-ttu-id="58f88-129">`0x4` -대량 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="58f88-129">`0x4` - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="58f88-130">`0x5` -공간 부족 (작은 개체 힙 용)</span><span class="sxs-lookup"><span data-stu-id="58f88-130">`0x5` - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="58f88-131">`0x6` -공간 부족 (large object heap의 경우).</span><span class="sxs-lookup"><span data-stu-id="58f88-131">`0x6` - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="58f88-132">`0x7` -발생 하지만 차단으로 강제 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-132">`0x7` - Induced but not forced as blocking.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="58f88-133">`0x0` -가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-133">`0x0` - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="58f88-134">`0x1` -백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="58f88-134">`0x1` - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="58f88-135">`0x2` -백그라운드 가비지 수집 중에 가비지 수집이 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-135">`0x2` - Blocking garbage collection occurred during background garbage collection.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="58f88-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-136">win:UInt16</span></span>|<span data-ttu-id="58f88-137">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-137">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="58f88-138">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="58f88-138">GCEnd_V1 Event</span></span>

<span data-ttu-id="58f88-139">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-139">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-140">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-140">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-141">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-141">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-142">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-142">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-143">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-143">Informational (4)</span></span>|

<span data-ttu-id="58f88-144">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-144">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-145">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-145">Event</span></span>|<span data-ttu-id="58f88-146">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-146">Event ID</span></span>|<span data-ttu-id="58f88-147">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-147">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="58f88-148">2</span><span class="sxs-lookup"><span data-stu-id="58f88-148">2</span></span>|<span data-ttu-id="58f88-149">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-149">The garbage collection has ended.</span></span>|

<span data-ttu-id="58f88-150">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-150">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-151">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-151">Field name</span></span>|<span data-ttu-id="58f88-152">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-152">Data type</span></span>|<span data-ttu-id="58f88-153">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-153">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="58f88-154">*n* 번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-154">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="58f88-155">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-155">The generation that was collected.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="58f88-156">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-156">win:UInt16</span></span>|<span data-ttu-id="58f88-157">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-157">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcheapstats_v2-event"></a><span data-ttu-id="58f88-158">GCHeapStats_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-158">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="58f88-159">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-159">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-160">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-160">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-161">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-161">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-162">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-162">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-163">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-163">Informational (4)</span></span>|

<span data-ttu-id="58f88-164">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-164">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-165">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-165">Event</span></span>|<span data-ttu-id="58f88-166">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-166">Event ID</span></span>|<span data-ttu-id="58f88-167">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-167">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="58f88-168">4</span><span class="sxs-lookup"><span data-stu-id="58f88-168">4</span></span>|<span data-ttu-id="58f88-169">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-169">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="58f88-170">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-170">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-171">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-171">Field name</span></span>|<span data-ttu-id="58f88-172">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-172">Data type</span></span>|<span data-ttu-id="58f88-173">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-173">Description</span></span>|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|<span data-ttu-id="58f88-174">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-174">The size, in bytes, of generation 0 memory.</span></span>|
|`TotalPromotedSize0`|`win:UInt64`|<span data-ttu-id="58f88-175">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-175">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|`GenerationSize1`|`win:UInt64`|<span data-ttu-id="58f88-176">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-176">The size, in bytes, of generation 1 memory.</span></span>|
|`TotalPromotedSize1`|`win:UInt64`|<span data-ttu-id="58f88-177">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-177">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|`GenerationSize2`|`win:UInt64`|<span data-ttu-id="58f88-178">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-178">The size, in bytes, of generation 2 memory.</span></span>|
|`TotalPromotedSize2`|`win:UInt64`|<span data-ttu-id="58f88-179">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-179">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|`GenerationSize3`|`win:UInt64`|<span data-ttu-id="58f88-180">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-180">The size, in bytes, of the large object heap.</span></span>|
|`TotalPromotedSize3`|`win:UInt64`|<span data-ttu-id="58f88-181">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-181">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|`FinalizationPromotedSize`|`win:UInt64`|<span data-ttu-id="58f88-182">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-182">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|`FinalizationPromotedCount`|`win:UInt64`|<span data-ttu-id="58f88-183">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-183">The number of objects that are ready for finalization.</span></span>|
|`PinnedObjectCount`|`win:UInt32`|<span data-ttu-id="58f88-184">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-184">The number of pinned (unmovable) objects.</span></span>|
|`SinkBlockCount`|`win:UInt32`|<span data-ttu-id="58f88-185">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-185">The number of synchronization blocks in use.</span></span>|
|`GCHandleCount`|`win:UInt32`|<span data-ttu-id="58f88-186">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-186">The number of garbage collection handles in use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-187">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-187">Unique ID for the instance of CoreCLR.</span></span>|
|`GenerationSize4`|`win:UInt64`|<span data-ttu-id="58f88-188">고정 된 개체 힙의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-188">The size, in bytes, of the pinned object heap.</span></span>|
|`TotalPromotedSize4`|`win:UInt64`|<span data-ttu-id="58f88-189">마지막 수집 이후 고정 된 개체 힙에서 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-189">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|

## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="58f88-190">GCCreateSegment_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-190">GCCreateSegment_V1 event</span></span>

<span data-ttu-id="58f88-191">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-191">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-192">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-192">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-193">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-193">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-194">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-194">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-195">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-195">Informational (4)</span></span>|

<span data-ttu-id="58f88-196">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-196">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-197">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-197">Event</span></span>|<span data-ttu-id="58f88-198">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-198">Event ID</span></span>|<span data-ttu-id="58f88-199">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-199">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="58f88-200">5</span><span class="sxs-lookup"><span data-stu-id="58f88-200">5</span></span>|<span data-ttu-id="58f88-201">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-201">A new garbage collection segment has been created.</span></span> <span data-ttu-id="58f88-202">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-202">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="58f88-203">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-203">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-204">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-204">Field name</span></span>|<span data-ttu-id="58f88-205">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-205">Data type</span></span>|<span data-ttu-id="58f88-206">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-206">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="58f88-207">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-207">The address of the segment.</span></span>|
|`Size`|`win:UInt64`|<span data-ttu-id="58f88-208">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-208">The size of the segment.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="58f88-209">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="58f88-209">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="58f88-210">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="58f88-210">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="58f88-211">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="58f88-211">0x2 - Read-only heap.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-212">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-212">Unique ID for the instance of CoreCLR.</span></span>|

<span data-ttu-id="58f88-213">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-213">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="58f88-214">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-214">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="58f88-215">GCFreeSegment_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-215">GCFreeSegment_V1 event</span></span>

<span data-ttu-id="58f88-216">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-216">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-217">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-217">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-218">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-218">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-219">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-219">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-220">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-220">Informational (4)</span></span>|

<span data-ttu-id="58f88-221">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-221">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-222">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-222">Event</span></span>|<span data-ttu-id="58f88-223">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-223">Event ID</span></span>|<span data-ttu-id="58f88-224">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-224">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="58f88-225">6</span><span class="sxs-lookup"><span data-stu-id="58f88-225">6</span></span>|<span data-ttu-id="58f88-226">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-226">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="58f88-227">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-227">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-228">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-228">Field name</span></span>|<span data-ttu-id="58f88-229">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-229">Data type</span></span>|<span data-ttu-id="58f88-230">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-230">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="58f88-231">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-231">The address of the segment.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-232">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-232">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="58f88-233">GCRestartEEBegin_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-233">GCRestartEEBegin_V1 event</span></span>

<span data-ttu-id="58f88-234">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-234">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-235">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-235">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-236">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-236">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-237">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-237">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-238">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-238">Informational (4)</span></span>|

<span data-ttu-id="58f88-239">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-239">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-240">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-240">Event</span></span>|<span data-ttu-id="58f88-241">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-241">Event ID</span></span>|<span data-ttu-id="58f88-242">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-242">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="58f88-243">7</span><span class="sxs-lookup"><span data-stu-id="58f88-243">7</span></span>|<span data-ttu-id="58f88-244">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-244">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="58f88-245">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-245">This event does not have any event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="58f88-246">GCRestartEEEnd_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-246">GCRestartEEEnd_V1 event</span></span>

<span data-ttu-id="58f88-247">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-247">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-248">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-248">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-249">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-249">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-250">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-250">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-251">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-251">Informational (4)</span></span>|

<span data-ttu-id="58f88-252">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-252">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-253">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-253">Event</span></span>|<span data-ttu-id="58f88-254">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-254">Event Id</span></span>|<span data-ttu-id="58f88-255">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-255">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="58f88-256">3</span><span class="sxs-lookup"><span data-stu-id="58f88-256">3</span></span>|<span data-ttu-id="58f88-257">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-257">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="58f88-258">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-258">This event does not have any event data.</span></span>

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="58f88-259">GCSuspendEEEnd_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-259">GCSuspendEEEnd_V1 event</span></span>

<span data-ttu-id="58f88-260">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-260">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-261">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-261">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-262">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-262">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-263">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-263">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-264">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-264">Informational (4)</span></span>|

<span data-ttu-id="58f88-265">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-265">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-266">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-266">Event</span></span>|<span data-ttu-id="58f88-267">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-267">Event ID</span></span>|<span data-ttu-id="58f88-268">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-268">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="58f88-269">8</span><span class="sxs-lookup"><span data-stu-id="58f88-269">8</span></span>|<span data-ttu-id="58f88-270">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-270">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="58f88-271">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-271">This event does not have any event data.</span></span>

## <a name="gcsuspendeebegin_v1-event"></a><span data-ttu-id="58f88-272">GCSuspendEEBegin_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-272">GCSuspendEEBegin_V1 event</span></span>

<span data-ttu-id="58f88-273">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-273">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-274">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-274">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-275">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-275">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-276">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-276">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-277">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-277">Informational (4)</span></span>|

<span data-ttu-id="58f88-278">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-278">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-279">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-279">Event</span></span>|<span data-ttu-id="58f88-280">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-280">Event ID</span></span>|<span data-ttu-id="58f88-281">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-281">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|<span data-ttu-id="58f88-282">8</span><span class="sxs-lookup"><span data-stu-id="58f88-282">8</span></span>|<span data-ttu-id="58f88-283">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-283">Start of suspension of the execution engine for garbage collection.</span></span>|

|<span data-ttu-id="58f88-284">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-284">Field name</span></span>|<span data-ttu-id="58f88-285">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-285">Data type</span></span>|<span data-ttu-id="58f88-286">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-286">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="58f88-287">*n* 번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-287">The *n* th garbage collection.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="58f88-288">EE 일시 중단의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-288">Reason for EE suspension.</span></span><br/><br/><span data-ttu-id="58f88-289">`0x0`: 다른에 대해 일시 중단</span><span class="sxs-lookup"><span data-stu-id="58f88-289">`0x0`: Suspend for Other</span></span><br/><br/><span data-ttu-id="58f88-290">`0x1`: GC에 대해 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-290">`0x1`: Suspend for GC.</span></span><br/><br/><span data-ttu-id="58f88-291">`0x2`: AppDomain 종료를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-291">`0x2`: Suspend for AppDomain shutdown.</span></span><br/><br/><span data-ttu-id="58f88-292">`0x3`: 코드 피칭 일시 중단입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-292">`0x3`: Suspend for code pitching.</span></span><br/><br/><span data-ttu-id="58f88-293">`0x4`: 종료를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-293">`0x4`: Suspend for shutdown.</span></span><br/><br/><span data-ttu-id="58f88-294">`0x5`: 디버거를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-294">`0x5`: Suspend for debugger.</span></span><br/><br/><span data-ttu-id="58f88-295">`0x6`: GC 준비를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-295">`0x6`: Suspend for GC Prep.</span></span><br/><br/><span data-ttu-id="58f88-296">`0x7`: 디버거 스윕 일시 중단</span><span class="sxs-lookup"><span data-stu-id="58f88-296">`0x7`: Suspend for debugger sweep</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="58f88-297">GCAllocationTick_V3 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-297">GCAllocationTick_V3 event</span></span>

<span data-ttu-id="58f88-298">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-298">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-299">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-299">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-300">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-300">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-301">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-301">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-302">자세한 정보 표시 (4)</span><span class="sxs-lookup"><span data-stu-id="58f88-302">Verbose (4)</span></span>|

<span data-ttu-id="58f88-303">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-303">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-304">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-304">Event</span></span>|<span data-ttu-id="58f88-305">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-305">Event ID</span></span>|<span data-ttu-id="58f88-306">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-306">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="58f88-307">10</span><span class="sxs-lookup"><span data-stu-id="58f88-307">10</span></span>|<span data-ttu-id="58f88-308">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-308">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="58f88-309">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-309">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-310">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-310">Field name</span></span>|<span data-ttu-id="58f88-311">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-311">Data type</span></span>|<span data-ttu-id="58f88-312">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-312">Description</span></span>|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|<span data-ttu-id="58f88-313">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-313">The allocation size, in bytes.</span></span> <span data-ttu-id="58f88-314">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-314">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="58f88-315">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-315">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="58f88-316">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="58f88-316">Use `AllocationAmount64` for very large allocations.</span></span>|
|`AllocationKind`|`win:UInt32`|<span data-ttu-id="58f88-317">`0x0` -작은 개체 할당 (할당이 작은 개체 힙에 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="58f88-317">`0x0` - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="58f88-318">`0x1` -대량 개체 할당 (할당이 대량 개체 힙에 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="58f88-318">`0x1` - Large object allocation (allocation is in large object heap).</span></span>|
|`AllocationAmount64`|`win:UInt64`|<span data-ttu-id="58f88-319">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-319">The allocation size, in bytes.</span></span> <span data-ttu-id="58f88-320">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-320">This value is accurate for very large allocations.</span></span>|
|`TypeId`|`win:Pointer`|<span data-ttu-id="58f88-321">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-321">The address of the MethodTable.</span></span> <span data-ttu-id="58f88-322">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-322">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="58f88-323">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-323">The name of the type that was allocated.</span></span> <span data-ttu-id="58f88-324">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-324">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`HeapIndex`|`win:UInt32`|<span data-ttu-id="58f88-325">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-325">The heap where the object was allocated.</span></span> <span data-ttu-id="58f88-326">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-326">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|`Address`|`win:Pointer`|<span data-ttu-id="58f88-327">마지막으로 할당 된 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-327">The address of the last allocated object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-328">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-328">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="58f88-329">GCCreateConcurrentThread_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-329">GCCreateConcurrentThread_V1 event</span></span>

<span data-ttu-id="58f88-330">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-330">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-331">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-331">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-332">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-332">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-333">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-333">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-334">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-334">Informational (4)</span></span>|
|<span data-ttu-id="58f88-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="58f88-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="58f88-336">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-336">Informational (4)</span></span>|

<span data-ttu-id="58f88-337">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-337">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-338">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-338">Event</span></span>|<span data-ttu-id="58f88-339">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-339">Event ID</span></span>|<span data-ttu-id="58f88-340">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-340">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="58f88-341">11</span><span class="sxs-lookup"><span data-stu-id="58f88-341">11</span></span>|<span data-ttu-id="58f88-342">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-342">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="58f88-343">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-343">This event does not have any event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="58f88-344">GCTerminateConcurrentThread_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-344">GCTerminateConcurrentThread_V1 event</span></span>

<span data-ttu-id="58f88-345">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-345">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-346">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-346">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-347">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-347">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-348">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-348">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-349">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-349">Informational (4)</span></span>|
|<span data-ttu-id="58f88-350">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="58f88-350">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="58f88-351">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-351">Informational (4)</span></span>|

<span data-ttu-id="58f88-352">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-352">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-353">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-353">Event</span></span>|<span data-ttu-id="58f88-354">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-354">Event ID</span></span>|<span data-ttu-id="58f88-355">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="58f88-356">12</span><span class="sxs-lookup"><span data-stu-id="58f88-356">12</span></span>|<span data-ttu-id="58f88-357">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-357">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="58f88-358">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-358">This event does not have any event data.</span></span>

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="58f88-359">GCFinalizersBegin_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-359">GCFinalizersBegin_V1 event</span></span>

<span data-ttu-id="58f88-360">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-360">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-361">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-361">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-362">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-362">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-363">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-363">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-364">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-364">Informational (4)</span></span>|

<span data-ttu-id="58f88-365">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-365">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-366">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-366">Event</span></span>|<span data-ttu-id="58f88-367">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-367">Event ID</span></span>|<span data-ttu-id="58f88-368">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-368">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="58f88-369">14</span><span class="sxs-lookup"><span data-stu-id="58f88-369">14</span></span>|<span data-ttu-id="58f88-370">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-370">The start of running finalizers.</span></span>|

<span data-ttu-id="58f88-371">이 이벤트에는 이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-371">This event does not have any event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="58f88-372">GCFinalizersEnd_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-372">GCFinalizersEnd_V1 event</span></span>

<span data-ttu-id="58f88-373">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-373">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-374">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-374">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-375">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-376">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-376">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-377">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-377">Informational (4)</span></span>|

<span data-ttu-id="58f88-378">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-378">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-379">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-379">Event</span></span>|<span data-ttu-id="58f88-380">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-380">Event ID</span></span>|<span data-ttu-id="58f88-381">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-381">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="58f88-382">13</span><span class="sxs-lookup"><span data-stu-id="58f88-382">13</span></span>|<span data-ttu-id="58f88-383">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-383">The end of running finalizers.</span></span>|

<span data-ttu-id="58f88-384">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-384">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-385">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-385">Field name</span></span>|<span data-ttu-id="58f88-386">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-386">Data type</span></span>|<span data-ttu-id="58f88-387">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-387">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="58f88-388">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-388">The number of finalizers that were run.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="58f88-389">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-389">win:UInt16</span></span>|<span data-ttu-id="58f88-390">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-390">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="setgchandle-event"></a><span data-ttu-id="58f88-391">SetGCHandle 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-391">SetGCHandle event</span></span>

<span data-ttu-id="58f88-392">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-392">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-393">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-393">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-394">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-394">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-395">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="58f88-395">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="58f88-396">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-396">Informational (4)</span></span>|

<span data-ttu-id="58f88-397">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-397">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-398">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-398">Event</span></span>|<span data-ttu-id="58f88-399">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-399">Event ID</span></span>|<span data-ttu-id="58f88-400">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-400">Raised when</span></span>|
|-----------|--------------|-----------------|
|`SetGCHandle`|<span data-ttu-id="58f88-401">30</span><span class="sxs-lookup"><span data-stu-id="58f88-401">30</span></span>|<span data-ttu-id="58f88-402">GC 핸들이 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-402">A GC Handle has been set.</span></span>|

<span data-ttu-id="58f88-403">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-403">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-404">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-404">Field name</span></span>|<span data-ttu-id="58f88-405">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-405">Data type</span></span>|<span data-ttu-id="58f88-406">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-406">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="58f88-407">할당 된 핸들의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-407">The address of the allocated handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="58f88-408">핸들이 만들어진 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-408">The address of the object whose handle was created.</span></span>|
|`Kind`|`win:UInt32`|<span data-ttu-id="58f88-409">설정 된 GC 핸들의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-409">The type of GC handle that was set.</span></span> <br /><br /><span data-ttu-id="58f88-410">`0x0`: WeakShort</span><span class="sxs-lookup"><span data-stu-id="58f88-410">`0x0`: WeakShort</span></span> <br/><br/><span data-ttu-id="58f88-411">`0x1`: WeakLong</span><span class="sxs-lookup"><span data-stu-id="58f88-411">`0x1`: WeakLong</span></span> <br /><br /><span data-ttu-id="58f88-412">`0x2`: 강력한</span><span class="sxs-lookup"><span data-stu-id="58f88-412">`0x2`: Strong</span></span> <br /><br /><span data-ttu-id="58f88-413">`0x3`: 고정 됨</span><span class="sxs-lookup"><span data-stu-id="58f88-413">`0x3`: Pinned</span></span> <br /><br /><span data-ttu-id="58f88-414">`0x4`: 변수</span><span class="sxs-lookup"><span data-stu-id="58f88-414">`0x4`: Variable</span></span><br /><br /><span data-ttu-id="58f88-415">`0x5`: RefCounted 됨</span><span class="sxs-lookup"><span data-stu-id="58f88-415">`0x5`: RefCounted</span></span> <br /><br /><span data-ttu-id="58f88-416">`0x6`: 종속</span><span class="sxs-lookup"><span data-stu-id="58f88-416">`0x6`: Dependent</span></span><br /><br /><span data-ttu-id="58f88-417">`0x7`: AsyncPinned 됨</span><span class="sxs-lookup"><span data-stu-id="58f88-417">`0x7`: AsyncPinned</span></span><br /><br /><span data-ttu-id="58f88-418">`0x8`: SizedRef</span><span class="sxs-lookup"><span data-stu-id="58f88-418">`0x8`: SizedRef</span></span>|
|`Generation`|`win:UInt32`|<span data-ttu-id="58f88-419">핸들이 만들어진 개체의 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-419">The generation of the object whose handle was created.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="58f88-420">AppDomain ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-420">The AppDomain ID.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-421">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-421">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="destroygchandle-event"></a><span data-ttu-id="58f88-422">DestroyGCHandle 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-422">DestroyGCHandle event</span></span>

<span data-ttu-id="58f88-423">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-423">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-424">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-424">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-425">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-425">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-426">`GCHandleKeyword` 0x2</span><span class="sxs-lookup"><span data-stu-id="58f88-426">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="58f88-427">정보(4)</span><span class="sxs-lookup"><span data-stu-id="58f88-427">Informational (4)</span></span>|

<span data-ttu-id="58f88-428">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-428">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-429">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-429">Event</span></span>|<span data-ttu-id="58f88-430">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-430">Event ID</span></span>|<span data-ttu-id="58f88-431">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-431">Raised when</span></span>|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|<span data-ttu-id="58f88-432">31</span><span class="sxs-lookup"><span data-stu-id="58f88-432">31</span></span>|<span data-ttu-id="58f88-433">GC 핸들이 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-433">A GC Handle is destroyed.</span></span>|

<span data-ttu-id="58f88-434">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-434">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-435">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-435">Field name</span></span>|<span data-ttu-id="58f88-436">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-436">Data type</span></span>|<span data-ttu-id="58f88-437">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-437">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="58f88-438">소멸 된 핸들의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-438">The address of the destroyed handle.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="58f88-439">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-439">win:UInt16</span></span>|<span data-ttu-id="58f88-440">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-440">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="pinobjectatgctime-event"></a><span data-ttu-id="58f88-441">PinObjectAtGCTime 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-441">PinObjectAtGCTime event</span></span>

<span data-ttu-id="58f88-442">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-442">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-443">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-443">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-444">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-444">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-445">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-445">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-446">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="58f88-446">Verbose (5)</span></span>|

<span data-ttu-id="58f88-447">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-447">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-448">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-448">Event</span></span>|<span data-ttu-id="58f88-449">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-449">Event ID</span></span>|<span data-ttu-id="58f88-450">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-450">Raised when</span></span>|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|<span data-ttu-id="58f88-451">33</span><span class="sxs-lookup"><span data-stu-id="58f88-451">33</span></span>|<span data-ttu-id="58f88-452">GC 중에 개체가 고정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-452">An object was pinned during a GC.</span></span>|

<span data-ttu-id="58f88-453">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-453">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-454">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-454">Field name</span></span>|<span data-ttu-id="58f88-455">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-455">Data type</span></span>|<span data-ttu-id="58f88-456">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-456">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="58f88-457">핸들의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-457">The address of the handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="58f88-458">고정 된 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-458">The address of the pinned object.</span></span>|
|`ObjectSize`|`win:UInt64`|<span data-ttu-id="58f88-459">고정 된 개체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-459">The size of the pinned object.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="58f88-460">고정 된 개체의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-460">The name of the type of the pinned object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-461">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-461">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gctriggered-event"></a><span data-ttu-id="58f88-462">GCTriggered 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-462">GCTriggered event</span></span>

<span data-ttu-id="58f88-463">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-463">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-464">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-464">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-465">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-465">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-466">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-466">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-467">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="58f88-467">Verbose (5)</span></span>|

<span data-ttu-id="58f88-468">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-468">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-469">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-469">Event</span></span>|<span data-ttu-id="58f88-470">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-470">Event ID</span></span>|<span data-ttu-id="58f88-471">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-471">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTriggered`|<span data-ttu-id="58f88-472">33</span><span class="sxs-lookup"><span data-stu-id="58f88-472">33</span></span>|<span data-ttu-id="58f88-473">GC가 트리거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-473">A GC has been triggered.</span></span>|

<span data-ttu-id="58f88-474">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-474">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-475">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-475">Field name</span></span>|<span data-ttu-id="58f88-476">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-476">Data type</span></span>|<span data-ttu-id="58f88-477">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-477">Description</span></span>|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|<span data-ttu-id="58f88-478">GC가 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-478">The reason a GC was triggered.</span></span><br/><br/><span data-ttu-id="58f88-479">`0x0`: AllocSmall</span><span class="sxs-lookup"><span data-stu-id="58f88-479">`0x0`: AllocSmall</span></span><br/><br/><span data-ttu-id="58f88-480">`0x1`: 발생</span><span class="sxs-lookup"><span data-stu-id="58f88-480">`0x1`: Induced</span></span> <br/><br/><span data-ttu-id="58f88-481">`0x2`: LowMemory</span><span class="sxs-lookup"><span data-stu-id="58f88-481">`0x2`: LowMemory</span></span> <br/><br/><span data-ttu-id="58f88-482">`0x3`: 비어 있음</span><span class="sxs-lookup"><span data-stu-id="58f88-482">`0x3`: Empty</span></span> <br/><br/><span data-ttu-id="58f88-483">`0x4`: AllocLarge</span><span class="sxs-lookup"><span data-stu-id="58f88-483">`0x4`: AllocLarge</span></span> <br/><br/><span data-ttu-id="58f88-484">`0x5`: OutOfSpaceSmallObjectHeap</span><span class="sxs-lookup"><span data-stu-id="58f88-484">`0x5`: OutOfSpaceSmallObjectHeap</span></span> <br/><br/><span data-ttu-id="58f88-485">`0x6`: OutOfSpaceLargeObjectHeap</span><span class="sxs-lookup"><span data-stu-id="58f88-485">`0x6`: OutOfSpaceLargeObjectHeap</span></span> <br/><br/><span data-ttu-id="58f88-486">`0x7`:InducedNoForce</span><span class="sxs-lookup"><span data-stu-id="58f88-486">`0x7`:InducedNoForce</span></span> <br/><br/><span data-ttu-id="58f88-487">`0x8`: 스트레스</span><span class="sxs-lookup"><span data-stu-id="58f88-487">`0x8`: Stress</span></span> <br/><br/><span data-ttu-id="58f88-488">`0x9`: InducedLowMemory</span><span class="sxs-lookup"><span data-stu-id="58f88-488">`0x9`: InducedLowMemory</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-489">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-489">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="increasememorypressure-event"></a><span data-ttu-id="58f88-490">IncreaseMemoryPressure 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-490">IncreaseMemoryPressure event</span></span>

<span data-ttu-id="58f88-491">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-491">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-492">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-492">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-493">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-493">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-494">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-494">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-495">정보 (4)</span><span class="sxs-lookup"><span data-stu-id="58f88-495">Information (4)</span></span>|

<span data-ttu-id="58f88-496">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-496">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-497">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-497">Event</span></span>|<span data-ttu-id="58f88-498">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-498">Event ID</span></span>|<span data-ttu-id="58f88-499">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-499">Raised when</span></span>|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|<span data-ttu-id="58f88-500">200</span><span class="sxs-lookup"><span data-stu-id="58f88-500">200</span></span>|<span data-ttu-id="58f88-501">메모리 압력이 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-501">Memory pressure was increased.</span></span>|

<span data-ttu-id="58f88-502">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-502">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-503">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-503">Field Name</span></span>|<span data-ttu-id="58f88-504">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-504">Data type</span></span>|<span data-ttu-id="58f88-505">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-505">Description</span></span>|
|----------------|---------------|-----------------|
|`ClrInstanceID`|<span data-ttu-id="58f88-506">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-506">win:UInt16</span></span>|<span data-ttu-id="58f88-507">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-507">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="decreasememorypressure-event"></a><span data-ttu-id="58f88-508">DecreaseMemoryPressure 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-508">DecreaseMemoryPressure event</span></span>

<span data-ttu-id="58f88-509">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-509">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-510">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-510">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-511">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-511">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-512">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-512">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-513">정보 (4)</span><span class="sxs-lookup"><span data-stu-id="58f88-513">Information (4)</span></span>|

<span data-ttu-id="58f88-514">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-514">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-515">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-515">Event</span></span>|<span data-ttu-id="58f88-516">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-516">Event ID</span></span>|<span data-ttu-id="58f88-517">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-517">Raised when</span></span>|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|<span data-ttu-id="58f88-518">201</span><span class="sxs-lookup"><span data-stu-id="58f88-518">201</span></span>|<span data-ttu-id="58f88-519">메모리 압력이 줄었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-519">Memory pressure was decreased.</span></span>|

<span data-ttu-id="58f88-520">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-520">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-521">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-521">Field Name</span></span>|<span data-ttu-id="58f88-522">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-522">Data type</span></span>|<span data-ttu-id="58f88-523">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-523">Description</span></span>|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|<span data-ttu-id="58f88-524">바이트를 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-524">Bytes freed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-525">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-525">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcmarkwithtype-event"></a><span data-ttu-id="58f88-526">GCMarkWithType 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-526">GCMarkWithType event</span></span>

<span data-ttu-id="58f88-527">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-527">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-528">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-528">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-529">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-529">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-530">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-530">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-531">정보 (4)</span><span class="sxs-lookup"><span data-stu-id="58f88-531">Information (4)</span></span>|

<span data-ttu-id="58f88-532">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-532">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-533">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-533">Event</span></span>|<span data-ttu-id="58f88-534">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-534">Event ID</span></span>|<span data-ttu-id="58f88-535">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-535">Raised when</span></span>|
|----------------|---------------|-----------------|
|`GCMarkWithType`|<span data-ttu-id="58f88-536">202</span><span class="sxs-lookup"><span data-stu-id="58f88-536">202</span></span>|<span data-ttu-id="58f88-537">Gc 루트는 GC 표시 단계에서 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-537">A GC root has been marked during GC mark phase.</span></span>|

<span data-ttu-id="58f88-538">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-538">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-539">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-539">Field Name</span></span>|<span data-ttu-id="58f88-540">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-540">Data type</span></span>|<span data-ttu-id="58f88-541">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-541">Description</span></span>|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|<span data-ttu-id="58f88-542">힙 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-542">The heap number.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="58f88-543">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="58f88-543">win:UInt16</span></span>|<span data-ttu-id="58f88-544">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-544">Unique ID for the instance of CoreCLR.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="58f88-545">GC 루트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-545">The GC root type.</span></span><br/><br/><span data-ttu-id="58f88-546">`0x0`: Stack</span><span class="sxs-lookup"><span data-stu-id="58f88-546">`0x0`: Stack</span></span><br/><br/><span data-ttu-id="58f88-547">`0x1`: 종료자</span><span class="sxs-lookup"><span data-stu-id="58f88-547">`0x1`: Finalizer</span></span><br/><br/><span data-ttu-id="58f88-548">`0x2`: Handle</span><span class="sxs-lookup"><span data-stu-id="58f88-548">`0x2`: Handle</span></span><br/><br/><span data-ttu-id="58f88-549">`0x3`: 이전</span><span class="sxs-lookup"><span data-stu-id="58f88-549">`0x3`: Older</span></span><br/><br/><span data-ttu-id="58f88-550">`0x4`: SizedRef</span><span class="sxs-lookup"><span data-stu-id="58f88-550">`0x4`: SizedRef</span></span><br/><br/><span data-ttu-id="58f88-551">`0x5`: 오버플로</span><span class="sxs-lookup"><span data-stu-id="58f88-551">`0x5`: Overflow</span></span><br/><br/>|
|`Bytes`|`win:UInt64`|<span data-ttu-id="58f88-552">표시 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-552">The number of bytes marked.</span></span>|

## <a name="gcjoin_v2-event"></a><span data-ttu-id="58f88-553">GCJoin_V2 이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-553">GCJoin_V2 event</span></span>

<span data-ttu-id="58f88-554">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-554">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="58f88-555">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="58f88-555">Keyword for raising the event</span></span>|<span data-ttu-id="58f88-556">수준</span><span class="sxs-lookup"><span data-stu-id="58f88-556">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="58f88-557">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="58f88-557">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="58f88-558">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="58f88-558">Verbose (5)</span></span>|

<span data-ttu-id="58f88-559">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-559">The following table shows the event information:</span></span>

|<span data-ttu-id="58f88-560">이벤트</span><span class="sxs-lookup"><span data-stu-id="58f88-560">Event</span></span>|<span data-ttu-id="58f88-561">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="58f88-561">Event ID</span></span>|<span data-ttu-id="58f88-562">발생 시기</span><span class="sxs-lookup"><span data-stu-id="58f88-562">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCJoin_V2`|<span data-ttu-id="58f88-563">203</span><span class="sxs-lookup"><span data-stu-id="58f88-563">203</span></span>|<span data-ttu-id="58f88-564">조인 된 GC 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-564">A GC thread joined.</span></span>|

<span data-ttu-id="58f88-565">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-565">The following table shows the event data:</span></span>

|<span data-ttu-id="58f88-566">필드 이름</span><span class="sxs-lookup"><span data-stu-id="58f88-566">Field name</span></span>|<span data-ttu-id="58f88-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="58f88-567">Data type</span></span>|<span data-ttu-id="58f88-568">Description</span><span class="sxs-lookup"><span data-stu-id="58f88-568">Description</span></span>|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|<span data-ttu-id="58f88-569">힙 번호</span><span class="sxs-lookup"><span data-stu-id="58f88-569">The heap number</span></span>|
|`JoinTime`|`win:UInt32`|<span data-ttu-id="58f88-570">이 이벤트가 조인 시작 시 (조인 시작의 경우 조인 `0x0` 끝에 대해) 발생 하는지 여부를 나타냅니다. `0x1`</span><span class="sxs-lookup"><span data-stu-id="58f88-570">Indicates whether this event is fired at the start of a join or end of a join (`0x0` for join start, `0x1` for join end)</span></span>|
|`JoinType`|`win:UInt32`|<span data-ttu-id="58f88-571">조인 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-571">The join type.</span></span> <br/><br/><span data-ttu-id="58f88-572">`0x0`: 마지막 조인</span><span class="sxs-lookup"><span data-stu-id="58f88-572">`0x0`: Last Join</span></span><br/><br/><span data-ttu-id="58f88-573">`0x1`: 조인</span><span class="sxs-lookup"><span data-stu-id="58f88-573">`0x1`: Join</span></span> <br/><br/><span data-ttu-id="58f88-574">`0x2`: 다시 시작</span><span class="sxs-lookup"><span data-stu-id="58f88-574">`0x2`: Restart</span></span> <br/><br/><span data-ttu-id="58f88-575">`0x3`: 첫 번째 역방향 조인</span><span class="sxs-lookup"><span data-stu-id="58f88-575">`0x3`: First Reverse Join</span></span><br/><br/><span data-ttu-id="58f88-576">`0x4`: 역방향 조인</span><span class="sxs-lookup"><span data-stu-id="58f88-576">`0x4`: Reverse Join</span></span><br/><br/>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="58f88-577">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58f88-577">Unique ID for the instance of CoreCLR.</span></span>|
