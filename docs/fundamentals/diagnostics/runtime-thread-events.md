---
title: ThreadPool 런타임 이벤트
description: .NET Core의 스레드 풀에 대 한 진단 정보를 수집 하는 .NET 런타임 스레드 풀 이벤트를 참조 하세요. 스레드 풀 이벤트는 작업자 스레드 풀 이벤트 또는 i/o 스레드 풀 이벤트입니다.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594123"
---
# <a name="net-runtime-thread-pool-events"></a><span data-ttu-id="d80ef-104">.NET 런타임 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-104">.NET runtime thread pool events</span></span>

<span data-ttu-id="d80ef-105">이러한 이벤트는 threadpool의 작업자 및 i/o 스레드에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-105">These events collect information about worker and I/O threads in the threadpool.</span></span> <span data-ttu-id="d80ef-106">진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d80ef-106">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="iothreadcreate_v1-event"></a><span data-ttu-id="d80ef-107">IOThreadCreate_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-107">IOThreadCreate_V1 event</span></span>

 <span data-ttu-id="d80ef-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-108">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-109">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-109">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-110">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-110">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-111">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-111">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-112">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-112">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-113">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-113">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-114">Event</span></span>|<span data-ttu-id="d80ef-115">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-115">Event ID</span></span>|<span data-ttu-id="d80ef-116">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d80ef-116">Raised when</span></span>|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|<span data-ttu-id="d80ef-117">44</span><span class="sxs-lookup"><span data-stu-id="d80ef-117">44</span></span>|<span data-ttu-id="d80ef-118">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-118">An I/O thread is created in the thread pool.</span></span>|

 <span data-ttu-id="d80ef-119">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-119">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-120">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-120">Field name</span></span>|<span data-ttu-id="d80ef-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-121">Data type</span></span>|<span data-ttu-id="d80ef-122">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-122">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="d80ef-123">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-123">Number of I/O threads, including the newly created thread.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="d80ef-124">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-124">Number of retired worker threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-125">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-125">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadterminate_v1-event"></a><span data-ttu-id="d80ef-126">IOThreadTerminate_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-126">IOThreadTerminate_V1 event</span></span>

 <span data-ttu-id="d80ef-127">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-127">The following table shows the keyword and level</span></span>

|<span data-ttu-id="d80ef-128">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-128">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-129">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-129">Level</span></span>
|-----------------------------------|-----------
|<span data-ttu-id="d80ef-130">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-130">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-131">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-131">Informational (4)</span></span>

 <span data-ttu-id="d80ef-132">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-132">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-133">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-133">Event</span></span>|<span data-ttu-id="d80ef-134">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-134">Event ID</span></span>|<span data-ttu-id="d80ef-135">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d80ef-135">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|<span data-ttu-id="d80ef-136">45</span><span class="sxs-lookup"><span data-stu-id="d80ef-136">45</span></span>|<span data-ttu-id="d80ef-137">스레드 풀에서 i/o 스레드가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-137">An I/O thread is terminated in the thread pool.</span></span>|

 <span data-ttu-id="d80ef-138">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-138">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-139">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-139">Field name</span></span>|<span data-ttu-id="d80ef-140">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-140">Data type</span></span>|<span data-ttu-id="d80ef-141">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-141">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="d80ef-142">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-142">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="d80ef-143">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-143">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-144">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadretire_v1-event"></a><span data-ttu-id="d80ef-145">IOThreadRetire_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-145">IOThreadRetire_V1 event</span></span>

 <span data-ttu-id="d80ef-146">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-146">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-147">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-147">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-148">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-149">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-149">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-150">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-150">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-151">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-151">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-152">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-152">Event</span></span>|<span data-ttu-id="d80ef-153">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-153">Event ID</span></span>|<span data-ttu-id="d80ef-154">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d80ef-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|<span data-ttu-id="d80ef-155">46</span><span class="sxs-lookup"><span data-stu-id="d80ef-155">46</span></span>|<span data-ttu-id="d80ef-156">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-156">An I/O thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="d80ef-157">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-157">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-158">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-158">Field name</span></span>|<span data-ttu-id="d80ef-159">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-159">Data type</span></span>|<span data-ttu-id="d80ef-160">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-160">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="d80ef-161">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-161">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="d80ef-162">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-162">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-163">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadunretire_v1-event"></a><span data-ttu-id="d80ef-164">IOThreadUnretire_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-164">IOThreadUnretire_V1 event</span></span>

 <span data-ttu-id="d80ef-165">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-165">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-166">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-166">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-167">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-168">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-168">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-169">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-169">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-170">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-170">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-171">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-171">Event</span></span>|<span data-ttu-id="d80ef-172">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-172">Event ID</span></span>|<span data-ttu-id="d80ef-173">발생 시기</span><span class="sxs-lookup"><span data-stu-id="d80ef-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|<span data-ttu-id="d80ef-174">47</span><span class="sxs-lookup"><span data-stu-id="d80ef-174">47</span></span>|<span data-ttu-id="d80ef-175">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-175">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="d80ef-176">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-176">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-177">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-177">Field name</span></span>|<span data-ttu-id="d80ef-178">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-178">Data type</span></span>|<span data-ttu-id="d80ef-179">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-179">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="d80ef-180">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-180">Number of I/O threads in the thread pool, including this one.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="d80ef-181">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-181">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`Win:UInt16`|<span data-ttu-id="d80ef-182">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-182">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstart-event"></a><span data-ttu-id="d80ef-183">ThreadPoolWorkerThreadStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-183">ThreadPoolWorkerThreadStart event</span></span>

|<span data-ttu-id="d80ef-184">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-184">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-185">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-185">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="d80ef-186">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-186">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-187">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-187">Informational (4)</span></span>|

|<span data-ttu-id="d80ef-188">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-188">Event</span></span>|<span data-ttu-id="d80ef-189">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-189">Event ID</span></span>|<span data-ttu-id="d80ef-190">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-190">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="d80ef-191">50</span><span class="sxs-lookup"><span data-stu-id="d80ef-191">50</span></span>|<span data-ttu-id="d80ef-192">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-192">A worker thread is created.</span></span>|

|<span data-ttu-id="d80ef-193">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-193">Field name</span></span>|<span data-ttu-id="d80ef-194">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-194">Data type</span></span>|<span data-ttu-id="d80ef-195">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-195">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-196">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-196">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-197">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-197">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-198">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-198">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstop-event"></a><span data-ttu-id="d80ef-199">ThreadPoolWorkerThreadStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-199">ThreadPoolWorkerThreadStop event</span></span>

|<span data-ttu-id="d80ef-200">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-200">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-201">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-201">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="d80ef-202">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-202">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-203">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-203">Informational (4)</span></span>|

|<span data-ttu-id="d80ef-204">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-204">Event</span></span>|<span data-ttu-id="d80ef-205">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-205">Event ID</span></span>|<span data-ttu-id="d80ef-206">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-206">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="d80ef-207">51</span><span class="sxs-lookup"><span data-stu-id="d80ef-207">51</span></span>|<span data-ttu-id="d80ef-208">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-208">A worker thread is stopped.</span></span>|

|<span data-ttu-id="d80ef-209">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-209">Field name</span></span>|<span data-ttu-id="d80ef-210">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-210">Data type</span></span>|<span data-ttu-id="d80ef-211">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-211">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-212">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-212">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-213">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-213">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-214">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-214">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadwait-event"></a><span data-ttu-id="d80ef-215">ThreadPoolWorkerThreadWait 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-215">ThreadPoolWorkerThreadWait event</span></span>

|<span data-ttu-id="d80ef-216">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-216">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-217">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-217">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="d80ef-218">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-218">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-219">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-219">Informational (4)</span></span>|

|<span data-ttu-id="d80ef-220">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-220">Event</span></span>|<span data-ttu-id="d80ef-221">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-221">Event ID</span></span>|<span data-ttu-id="d80ef-222">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-222">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|<span data-ttu-id="d80ef-223">57</span><span class="sxs-lookup"><span data-stu-id="d80ef-223">57</span></span>|<span data-ttu-id="d80ef-224">작업자 스레드가 작업 대기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-224">A worker thread starts waiting for work.</span></span>|

|<span data-ttu-id="d80ef-225">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-225">Field name</span></span>|<span data-ttu-id="d80ef-226">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-226">Data type</span></span>|<span data-ttu-id="d80ef-227">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-227">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-228">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-228">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-229">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-229">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-230">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-230">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstart-event"></a><span data-ttu-id="d80ef-231">ThreadPoolWorkerThreadRetirementStart 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-231">ThreadPoolWorkerThreadRetirementStart event</span></span>

|<span data-ttu-id="d80ef-232">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-232">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-233">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-233">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="d80ef-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-235">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-235">Informational (4)</span></span>|

|<span data-ttu-id="d80ef-236">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-236">Event</span></span>|<span data-ttu-id="d80ef-237">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-237">Event ID</span></span>|<span data-ttu-id="d80ef-238">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-238">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="d80ef-239">52</span><span class="sxs-lookup"><span data-stu-id="d80ef-239">52</span></span>|<span data-ttu-id="d80ef-240">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-240">A worker thread retires.</span></span>|

|<span data-ttu-id="d80ef-241">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-241">Field name</span></span>|<span data-ttu-id="d80ef-242">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-242">Data type</span></span>|<span data-ttu-id="d80ef-243">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-243">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-244">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-244">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-245">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-245">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-246">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstop-event"></a><span data-ttu-id="d80ef-247">ThreadPoolWorkerThreadRetirementStop 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-247">ThreadPoolWorkerThreadRetirementStop event</span></span>

|<span data-ttu-id="d80ef-248">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-248">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-249">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-249">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="d80ef-250">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-250">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-251">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-251">Informational (4)</span></span>|

|<span data-ttu-id="d80ef-252">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-252">Event</span></span>|<span data-ttu-id="d80ef-253">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-253">Event ID</span></span>|<span data-ttu-id="d80ef-254">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-254">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="d80ef-255">53</span><span class="sxs-lookup"><span data-stu-id="d80ef-255">53</span></span>|<span data-ttu-id="d80ef-256">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-256">A retired worker thread becomes active again.</span></span>|

|<span data-ttu-id="d80ef-257">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-257">Field name</span></span>|<span data-ttu-id="d80ef-258">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-258">Data type</span></span>|<span data-ttu-id="d80ef-259">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-259">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-260">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-260">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-261">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-261">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-262">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-262">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a><span data-ttu-id="d80ef-263">ThreadPoolWorkerThreadAdjustmentSample 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-263">ThreadPoolWorkerThreadAdjustmentSample event</span></span>

 <span data-ttu-id="d80ef-264">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-264">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-265">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-265">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-266">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-266">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-267">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-267">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-268">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-268">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-269">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-269">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-270">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-270">Event</span></span>|<span data-ttu-id="d80ef-271">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-271">Event ID</span></span>|<span data-ttu-id="d80ef-272">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-272">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="d80ef-273">54</span><span class="sxs-lookup"><span data-stu-id="d80ef-273">54</span></span>|<span data-ttu-id="d80ef-274">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-274">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|

 <span data-ttu-id="d80ef-275">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-275">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-276">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-276">Field name</span></span>|<span data-ttu-id="d80ef-277">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-277">Data type</span></span>|<span data-ttu-id="d80ef-278">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-278">Description</span></span>|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|<span data-ttu-id="d80ef-279">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-279">Number of completions per unit of time.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-280">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a><span data-ttu-id="d80ef-281">ThreadPoolWorkerThreadAdjustmentAdjustment 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-281">ThreadPoolWorkerThreadAdjustmentAdjustment event</span></span>

 <span data-ttu-id="d80ef-282">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-282">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-283">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-283">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-284">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-284">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-286">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-286">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-287">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-287">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-288">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-288">Event</span></span>|<span data-ttu-id="d80ef-289">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-289">Event ID</span></span>|<span data-ttu-id="d80ef-290">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-290">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="d80ef-291">55</span><span class="sxs-lookup"><span data-stu-id="d80ef-291">55</span></span>|<span data-ttu-id="d80ef-292">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-292">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|

 <span data-ttu-id="d80ef-293">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-293">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-294">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-294">Field name</span></span>|<span data-ttu-id="d80ef-295">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-295">Data type</span></span>|<span data-ttu-id="d80ef-296">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-296">Description</span></span>|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|<span data-ttu-id="d80ef-297">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-297">Average throughput of a sample of measurements.</span></span>|
|`NewWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="d80ef-298">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-298">New number of active worker threads.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="d80ef-299">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-299">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="d80ef-300">`0x0` 워밍업.</span><span class="sxs-lookup"><span data-stu-id="d80ef-300">`0x0` - Warmup.</span></span><br /><br /> <span data-ttu-id="d80ef-301">`0x1` 도중.</span><span class="sxs-lookup"><span data-stu-id="d80ef-301">`0x1` - Initializing.</span></span><br /><br /> <span data-ttu-id="d80ef-302">`0x2` -임의 이동.</span><span class="sxs-lookup"><span data-stu-id="d80ef-302">`0x2` - Random move.</span></span><br /><br /> <span data-ttu-id="d80ef-303">`0x3` -이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-303">`0x3` - Climbing move.</span></span><br /><br /> <span data-ttu-id="d80ef-304">`0x4` -Point를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-304">`0x4` - Change point.</span></span><br /><br /> <span data-ttu-id="d80ef-305">`0x5` 안정화.</span><span class="sxs-lookup"><span data-stu-id="d80ef-305">`0x5` - Stabilizing.</span></span><br /><br /> <span data-ttu-id="d80ef-306">`0x6` 고갈.</span><span class="sxs-lookup"><span data-stu-id="d80ef-306">`0x6` - Starvation.</span></span><br /><br /> <span data-ttu-id="d80ef-307">`0x7` -스레드 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-307">`0x7` - Thread timed out.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-308">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-308">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a><span data-ttu-id="d80ef-309">ThreadPoolWorkerThreadAdjustmentStats 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-309">ThreadPoolWorkerThreadAdjustmentStats event</span></span>

 <span data-ttu-id="d80ef-310">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-310">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-311">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-311">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-312">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-312">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-313">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-313">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-314">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-314">Verbose (5)</span></span>

 <span data-ttu-id="d80ef-315">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-315">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-316">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-316">Event</span></span>|<span data-ttu-id="d80ef-317">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-317">Event ID</span></span>|<span data-ttu-id="d80ef-318">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-318">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="d80ef-319">56</span><span class="sxs-lookup"><span data-stu-id="d80ef-319">56</span></span>|<span data-ttu-id="d80ef-320">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-320">Gathers data on the thread pool.</span></span>|

 <span data-ttu-id="d80ef-321">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-321">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-322">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-322">Field name</span></span>|<span data-ttu-id="d80ef-323">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-323">Data type</span></span>|<span data-ttu-id="d80ef-324">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-324">Description</span></span>|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|<span data-ttu-id="d80ef-325">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-325">Amount of time, in seconds, during which these statistics were collected.</span></span>|
|`Throughput`|`win:Double`|<span data-ttu-id="d80ef-326">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-326">Average number of completions per second during this interval.</span></span>|
|`ThreadWave`|`win:Double`|<span data-ttu-id="d80ef-327">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-327">Reserved for internal use.</span></span>|
|`ThroughputWave`|`win:Double`|<span data-ttu-id="d80ef-328">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-328">Reserved for internal use.</span></span>|
|`ThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="d80ef-329">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-329">Reserved for internal use.</span></span>|
|`AverageThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="d80ef-330">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-330">Reserved for internal use.</span></span>|
|`ThroughputRatio`|`win:Double`|<span data-ttu-id="d80ef-331">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-331">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|
|`Confidence`|`win:Double`|<span data-ttu-id="d80ef-332">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-332">A measure of the validity of the ThroughputRatio field.</span></span>|
|`NewcontrolSetting`|`win:Double`|<span data-ttu-id="d80ef-333">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-333">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|
|`NewThreadWaveMagnitude`|`win:UInt16`|<span data-ttu-id="d80ef-334">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-334">The magnitude of future variations in active thread count.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-335">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-335">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolenqueue-event"></a><span data-ttu-id="d80ef-336">ThreadPoolEnqueue 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-336">ThreadPoolEnqueue event</span></span>

 <span data-ttu-id="d80ef-337">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-337">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-338">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-338">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-339">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-339">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-340">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-340">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-341">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-341">Verbose (5)</span></span>

 <span data-ttu-id="d80ef-342">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-342">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-343">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-343">Event</span></span>|<span data-ttu-id="d80ef-344">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-344">Event ID</span></span>|<span data-ttu-id="d80ef-345">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-345">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|<span data-ttu-id="d80ef-346">61</span><span class="sxs-lookup"><span data-stu-id="d80ef-346">61</span></span>|<span data-ttu-id="d80ef-347">스레드 풀 큐에서 작업 항목을 큐에 넣었습니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-347">A work item was enqueued in the thread pool queue.</span></span>|

 <span data-ttu-id="d80ef-348">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-348">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-349">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-349">Field name</span></span>|<span data-ttu-id="d80ef-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-350">Data type</span></span>|<span data-ttu-id="d80ef-351">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-351">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="d80ef-352">작업 요청에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-352">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-353">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-353">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooldequeue-event"></a><span data-ttu-id="d80ef-354">ThreadPoolDequeue 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-354">ThreadPoolDequeue event</span></span>

 <span data-ttu-id="d80ef-355">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-355">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-356">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-356">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-357">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-357">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-358">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-358">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-359">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-359">Verbose (5)</span></span>

 <span data-ttu-id="d80ef-360">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-360">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-361">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-361">Event</span></span>|<span data-ttu-id="d80ef-362">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-362">Event ID</span></span>|<span data-ttu-id="d80ef-363">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-363">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|<span data-ttu-id="d80ef-364">62</span><span class="sxs-lookup"><span data-stu-id="d80ef-364">62</span></span>|<span data-ttu-id="d80ef-365">작업 항목이 스레드 풀 큐에서 큐에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-365">A work item was dequeued from the thread pool queue.</span></span>|

 <span data-ttu-id="d80ef-366">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-366">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-367">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-367">Field name</span></span>|<span data-ttu-id="d80ef-368">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-368">Data type</span></span>|<span data-ttu-id="d80ef-369">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-369">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="d80ef-370">작업 요청에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-370">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-371">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-371">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpoolioenqueue-event"></a><span data-ttu-id="d80ef-372">ThreadPoolIOEnqueue 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-372">ThreadPoolIOEnqueue event</span></span>

 <span data-ttu-id="d80ef-373">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-373">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-374">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-374">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-375">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-376">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-376">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-377">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-377">Verbose (5)</span></span>

 <span data-ttu-id="d80ef-378">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-378">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-379">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-379">Event</span></span>|<span data-ttu-id="d80ef-380">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-380">Event ID</span></span>|<span data-ttu-id="d80ef-381">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-381">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|<span data-ttu-id="d80ef-382">63</span><span class="sxs-lookup"><span data-stu-id="d80ef-382">63</span></span>|<span data-ttu-id="d80ef-383">비동기 IO 완료가 발생 한 후에는 스레드가 IO 완료 알림을 큐 합니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-383">A thread enqueues an IO completion notification after an async IO completion occurs.</span></span>|

 <span data-ttu-id="d80ef-384">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-384">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-385">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-385">Field name</span></span>|<span data-ttu-id="d80ef-386">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-386">Data type</span></span>|<span data-ttu-id="d80ef-387">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-387">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="d80ef-388">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-388">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="d80ef-389">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-389">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="d80ef-390">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-390">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-391">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-391">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliodequeue-event"></a><span data-ttu-id="d80ef-392">ThreadPoolIODequeue 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-392">ThreadPoolIODequeue event</span></span>

 <span data-ttu-id="d80ef-393">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-393">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-394">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-394">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-395">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-395">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-396">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-396">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-397">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-397">Verbose (5)</span></span>

 <span data-ttu-id="d80ef-398">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-398">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-399">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-399">Event</span></span>|<span data-ttu-id="d80ef-400">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-400">Event ID</span></span>|<span data-ttu-id="d80ef-401">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-401">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|<span data-ttu-id="d80ef-402">64</span><span class="sxs-lookup"><span data-stu-id="d80ef-402">64</span></span>|<span data-ttu-id="d80ef-403">스레드가 IO 완료 알림을 큐에 대기 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-403">A thread dequeues the IO completion notification.</span></span>|

 <span data-ttu-id="d80ef-404">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-404">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-405">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-405">Field name</span></span>|<span data-ttu-id="d80ef-406">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-406">Data type</span></span>|<span data-ttu-id="d80ef-407">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-407">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="d80ef-408">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-408">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="d80ef-409">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-409">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="d80ef-410">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-410">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-411">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-411">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliopack-event"></a><span data-ttu-id="d80ef-412">ThreadPoolIOPack 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-412">ThreadPoolIOPack event</span></span>

 <span data-ttu-id="d80ef-413">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-413">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="d80ef-414">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-414">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-415">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-415">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-416">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-416">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-417">자세한 정보 표시(5)</span><span class="sxs-lookup"><span data-stu-id="d80ef-417">Verbose (5)</span></span>|

 <span data-ttu-id="d80ef-418">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-418">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-419">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-419">Event</span></span>|<span data-ttu-id="d80ef-420">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-420">Event ID</span></span>|<span data-ttu-id="d80ef-421">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-421">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|<span data-ttu-id="d80ef-422">65</span><span class="sxs-lookup"><span data-stu-id="d80ef-422">65</span></span>|<span data-ttu-id="d80ef-423">ThreadPool 겹친 IO pack이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-423">ThreadPool overlapped IO pack is called.</span></span>|

 <span data-ttu-id="d80ef-424">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-424">The following table shows the event data</span></span>

|<span data-ttu-id="d80ef-425">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-425">Field name</span></span>|<span data-ttu-id="d80ef-426">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-426">Data type</span></span>|<span data-ttu-id="d80ef-427">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-427">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="d80ef-428">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-428">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="d80ef-429">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-429">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-430">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-430">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadcreating-event"></a><span data-ttu-id="d80ef-431">ThreadCreating 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-431">ThreadCreating event</span></span>

 <span data-ttu-id="d80ef-432">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-432">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="d80ef-433">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-433">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-434">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-435">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-435">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-436">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-436">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-437">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-437">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-438">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-438">Event</span></span>|<span data-ttu-id="d80ef-439">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-439">Event ID</span></span>|<span data-ttu-id="d80ef-440">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-440">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadCreating`|<span data-ttu-id="d80ef-441">70</span><span class="sxs-lookup"><span data-stu-id="d80ef-441">70</span></span>|<span data-ttu-id="d80ef-442">스레드를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-442">Thread has been created.</span></span>|

 <span data-ttu-id="d80ef-443">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-443">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-444">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-444">Field name</span></span>|<span data-ttu-id="d80ef-445">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-445">Data type</span></span>|<span data-ttu-id="d80ef-446">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-446">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="d80ef-447">스레드 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-447">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-448">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-448">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadrunning-event"></a><span data-ttu-id="d80ef-449">ThreadRunning 이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-449">ThreadRunning event</span></span>

 <span data-ttu-id="d80ef-450">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-450">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="d80ef-451">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="d80ef-451">Keyword for raising the event</span></span>|<span data-ttu-id="d80ef-452">수준</span><span class="sxs-lookup"><span data-stu-id="d80ef-452">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="d80ef-453">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="d80ef-453">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="d80ef-454">정보(4)</span><span class="sxs-lookup"><span data-stu-id="d80ef-454">Informational (4)</span></span>|

 <span data-ttu-id="d80ef-455">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-455">The following table shows the event information.</span></span>

|<span data-ttu-id="d80ef-456">이벤트</span><span class="sxs-lookup"><span data-stu-id="d80ef-456">Event</span></span>|<span data-ttu-id="d80ef-457">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-457">Event ID</span></span>|<span data-ttu-id="d80ef-458">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-458">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadRunning`|<span data-ttu-id="d80ef-459">71</span><span class="sxs-lookup"><span data-stu-id="d80ef-459">71</span></span>|<span data-ttu-id="d80ef-460">스레드의 실행이 시작 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-460">Thread has started running.</span></span>|

 <span data-ttu-id="d80ef-461">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-461">The following table shows the event data.</span></span>

|<span data-ttu-id="d80ef-462">필드 이름</span><span class="sxs-lookup"><span data-stu-id="d80ef-462">Field name</span></span>|<span data-ttu-id="d80ef-463">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d80ef-463">Data type</span></span>|<span data-ttu-id="d80ef-464">Description</span><span class="sxs-lookup"><span data-stu-id="d80ef-464">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="d80ef-465">스레드 ID</span><span class="sxs-lookup"><span data-stu-id="d80ef-465">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="d80ef-466">CoreCLR 인스턴스에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d80ef-466">Unique ID for the instance of CoreCLR.</span></span>|
