---
title: 스레드 풀 ETW 이벤트
description: .NET의 스레드에 대 한 정보를 수집 하는 스레드 풀 ETW 이벤트를 검토 합니다. 스레드 풀 이벤트는 작업자 스레드 풀 이벤트 또는 i/o 스레드 풀 이벤트입니다.
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: d3059cec5007c24d41a4a779939d4990f19305ca
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475205"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="30dff-104">스레드 풀 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-104">Thread Pool ETW Events</span></span>
<span data-ttu-id="30dff-105">이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-105">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="30dff-106">스레드 풀 이벤트에는 다음과 같은 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-106">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="30dff-107">[작업자 스레드 풀 이벤트](#worker-thread-pool-events). 이러한 스레드 풀 이벤트는 애플리케이션에서 스레드 풀을 사용하는 방식에 대한 정보 및 작업 부하가 동시성 제어에 미치는 영향에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-107">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="30dff-108">[I/O 스레드 풀 이벤트](#io-thread-events). 이러한 스레드 풀 이벤트는 스레드 풀에서 생성되거나, 만료되거나, 만료되지 않거나, 종료된 I/O 스레드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-108">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="30dff-109">작업자 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-109">Worker Thread Pool Events</span></span>
 <span data-ttu-id="30dff-110">이러한 이벤트는 런타임의 작업자 스레드 풀과 관련이 있으며, 스레드 이벤트에 대한 알림을 제공합니다(예: 스레드가 만들어지거나 중지될 때).</span><span class="sxs-lookup"><span data-stu-id="30dff-110">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="30dff-111">작업자 스레드 풀은 동시성 제어를 위해 측정된 처리량을 기준으로 스레드 수가 계산되는 자동 선택 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-111">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="30dff-112">작업자 스레드 풀 이벤트는 애플리케이션이 스레드 풀을 사용하는 방법 그리고 특정 작업 부하가 동시성 제어에 미칠 수 있는 영향을 이해하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-112">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="30dff-113">ThreadPoolWorkerThreadStart 및 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="30dff-113">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="30dff-114">다음 표에서는 이러한 이벤트의 키워드 및 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-114">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="30dff-115">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30dff-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="30dff-116">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-116">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-117">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-118">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-118">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-119">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-119">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-120">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-120">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-121">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-121">Event</span></span>|<span data-ttu-id="30dff-122">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-122">Event ID</span></span>|<span data-ttu-id="30dff-123">발생 시기</span><span class="sxs-lookup"><span data-stu-id="30dff-123">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="30dff-124">50</span><span class="sxs-lookup"><span data-stu-id="30dff-124">50</span></span>|<span data-ttu-id="30dff-125">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-125">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="30dff-126">51</span><span class="sxs-lookup"><span data-stu-id="30dff-126">51</span></span>|<span data-ttu-id="30dff-127">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-127">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="30dff-128">52</span><span class="sxs-lookup"><span data-stu-id="30dff-128">52</span></span>|<span data-ttu-id="30dff-129">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-129">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="30dff-130">53</span><span class="sxs-lookup"><span data-stu-id="30dff-130">53</span></span>|<span data-ttu-id="30dff-131">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-131">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="30dff-132">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-132">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-133">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-133">Field name</span></span>|<span data-ttu-id="30dff-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-134">Data type</span></span>|<span data-ttu-id="30dff-135">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-135">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-136">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="30dff-136">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="30dff-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30dff-137">win:UInt32</span></span>|<span data-ttu-id="30dff-138">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-138">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="30dff-139">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="30dff-139">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="30dff-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30dff-140">win:UInt32</span></span>|<span data-ttu-id="30dff-141">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-141">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="30dff-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-142">ClrInstanceID</span></span>|<span data-ttu-id="30dff-143">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-143">Win:UInt16</span></span>|<span data-ttu-id="30dff-144">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="30dff-145">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="30dff-145">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="30dff-146">이러한 스레드 풀 이벤트는 스레드 삽입(동시성 제어) 알고리즘의 동작을 이해하고 디버깅하기 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-146">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="30dff-147">이 정보는 작업자 스레드 풀에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-147">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="30dff-148">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="30dff-148">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="30dff-149">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-149">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-150">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-150">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-151">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-151">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-152">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-152">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-153">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-153">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-154">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-154">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-155">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-155">Event</span></span>|<span data-ttu-id="30dff-156">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-156">Event ID</span></span>|<span data-ttu-id="30dff-157">설명</span><span class="sxs-lookup"><span data-stu-id="30dff-157">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="30dff-158">54</span><span class="sxs-lookup"><span data-stu-id="30dff-158">54</span></span>|<span data-ttu-id="30dff-159">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-159">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="30dff-160">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-160">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-161">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-161">Field name</span></span>|<span data-ttu-id="30dff-162">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-162">Data type</span></span>|<span data-ttu-id="30dff-163">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-163">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-164">처리량</span><span class="sxs-lookup"><span data-stu-id="30dff-164">Throughput</span></span>|<span data-ttu-id="30dff-165">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-165">win:Double</span></span>|<span data-ttu-id="30dff-166">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-166">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="30dff-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-167">ClrInstanceID</span></span>|<span data-ttu-id="30dff-168">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-168">Win:UInt16</span></span>|<span data-ttu-id="30dff-169">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="30dff-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="30dff-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="30dff-171">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-171">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-172">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-172">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-173">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-173">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-174">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-174">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-175">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-175">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-176">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-176">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-177">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-177">Event</span></span>|<span data-ttu-id="30dff-178">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-178">Event ID</span></span>|<span data-ttu-id="30dff-179">설명</span><span class="sxs-lookup"><span data-stu-id="30dff-179">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="30dff-180">55</span><span class="sxs-lookup"><span data-stu-id="30dff-180">55</span></span>|<span data-ttu-id="30dff-181">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-181">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="30dff-182">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-182">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-183">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-183">Field name</span></span>|<span data-ttu-id="30dff-184">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-184">Data type</span></span>|<span data-ttu-id="30dff-185">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-185">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-186">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="30dff-186">AverageThroughput</span></span>|<span data-ttu-id="30dff-187">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-187">win:Double</span></span>|<span data-ttu-id="30dff-188">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-188">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="30dff-189">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="30dff-189">NewWorkerThreadCount</span></span>|<span data-ttu-id="30dff-190">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30dff-190">win:UInt32</span></span>|<span data-ttu-id="30dff-191">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-191">New number of active worker threads.</span></span>|  
|<span data-ttu-id="30dff-192">이유</span><span class="sxs-lookup"><span data-stu-id="30dff-192">Reason</span></span>|<span data-ttu-id="30dff-193">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30dff-193">win:UInt32</span></span>|<span data-ttu-id="30dff-194">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-194">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="30dff-195">0x00 - 준비</span><span class="sxs-lookup"><span data-stu-id="30dff-195">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="30dff-196">0x01 - 초기화 중</span><span class="sxs-lookup"><span data-stu-id="30dff-196">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="30dff-197">0x02 - 무작위 이동</span><span class="sxs-lookup"><span data-stu-id="30dff-197">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="30dff-198">0x03 - 오르기 이동</span><span class="sxs-lookup"><span data-stu-id="30dff-198">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="30dff-199">0x04 - 포인트 변경</span><span class="sxs-lookup"><span data-stu-id="30dff-199">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="30dff-200">0x05 - 안정화 중</span><span class="sxs-lookup"><span data-stu-id="30dff-200">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="30dff-201">0x06 - 고갈</span><span class="sxs-lookup"><span data-stu-id="30dff-201">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="30dff-202">0x07 - 스레드 시간 초과</span><span class="sxs-lookup"><span data-stu-id="30dff-202">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="30dff-203">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-203">ClrInstanceID</span></span>|<span data-ttu-id="30dff-204">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-204">Win:UInt16</span></span>|<span data-ttu-id="30dff-205">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-205">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="30dff-206">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="30dff-206">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="30dff-207">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-207">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-208">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-208">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-209">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-209">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-210">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-210">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-211">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-211">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-212">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-212">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-213">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-213">Event</span></span>|<span data-ttu-id="30dff-214">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-214">Event ID</span></span>|<span data-ttu-id="30dff-215">설명</span><span class="sxs-lookup"><span data-stu-id="30dff-215">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="30dff-216">56</span><span class="sxs-lookup"><span data-stu-id="30dff-216">56</span></span>|<span data-ttu-id="30dff-217">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-217">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="30dff-218">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-218">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-219">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-219">Field name</span></span>|<span data-ttu-id="30dff-220">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-220">Data type</span></span>|<span data-ttu-id="30dff-221">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-221">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-222">Duration</span><span class="sxs-lookup"><span data-stu-id="30dff-222">Duration</span></span>|<span data-ttu-id="30dff-223">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-223">win:Double</span></span>|<span data-ttu-id="30dff-224">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-224">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="30dff-225">처리량</span><span class="sxs-lookup"><span data-stu-id="30dff-225">Throughput</span></span>|<span data-ttu-id="30dff-226">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-226">win:Double</span></span>|<span data-ttu-id="30dff-227">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-227">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="30dff-228">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="30dff-228">ThreadWave</span></span>|<span data-ttu-id="30dff-229">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-229">win:Double</span></span>|<span data-ttu-id="30dff-230">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-230">Reserved for internal use.</span></span>|  
|<span data-ttu-id="30dff-231">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="30dff-231">ThroughputWave</span></span>|<span data-ttu-id="30dff-232">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-232">win:Double</span></span>|<span data-ttu-id="30dff-233">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-233">Reserved for internal use.</span></span>|  
|<span data-ttu-id="30dff-234">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="30dff-234">ThroughputErrorEstimate</span></span>|<span data-ttu-id="30dff-235">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-235">win:Double</span></span>|<span data-ttu-id="30dff-236">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-236">Reserved for internal use.</span></span>|  
|<span data-ttu-id="30dff-237">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="30dff-237">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="30dff-238">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-238">win:Double</span></span>|<span data-ttu-id="30dff-239">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-239">Reserved for internal use.</span></span>|  
|<span data-ttu-id="30dff-240">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="30dff-240">ThroughputRatio</span></span>|<span data-ttu-id="30dff-241">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-241">win:Double</span></span>|<span data-ttu-id="30dff-242">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-242">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="30dff-243">신뢰도</span><span class="sxs-lookup"><span data-stu-id="30dff-243">Confidence</span></span>|<span data-ttu-id="30dff-244">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-244">win:Double</span></span>|<span data-ttu-id="30dff-245">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-245">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="30dff-246">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="30dff-246">NewcontrolSetting</span></span>|<span data-ttu-id="30dff-247">win:Double</span><span class="sxs-lookup"><span data-stu-id="30dff-247">win:Double</span></span>|<span data-ttu-id="30dff-248">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-248">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="30dff-249">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="30dff-249">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="30dff-250">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-250">Win:UInt16</span></span>|<span data-ttu-id="30dff-251">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-251">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="30dff-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-252">ClrInstanceID</span></span>|<span data-ttu-id="30dff-253">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-253">Win:UInt16</span></span>|<span data-ttu-id="30dff-254">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="30dff-255">I/O 스레드 이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-255">I/O Thread Events</span></span>  
 <span data-ttu-id="30dff-256">이러한 스레드 풀 이벤트는 비동기적인 I/O 스레드 풀(완료 포트)에서 스레드에 대해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-256">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="30dff-257">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="30dff-257">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="30dff-258">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-258">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-259">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-259">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-260">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-260">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-261">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-261">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-262">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-262">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-263">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-263">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-264">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-264">Event</span></span>|<span data-ttu-id="30dff-265">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-265">Event ID</span></span>|<span data-ttu-id="30dff-266">발생 시기</span><span class="sxs-lookup"><span data-stu-id="30dff-266">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="30dff-267">44</span><span class="sxs-lookup"><span data-stu-id="30dff-267">44</span></span>|<span data-ttu-id="30dff-268">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-268">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="30dff-269">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-269">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-270">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-270">Field name</span></span>|<span data-ttu-id="30dff-271">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-271">Data type</span></span>|<span data-ttu-id="30dff-272">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-272">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-273">개수</span><span class="sxs-lookup"><span data-stu-id="30dff-273">Count</span></span>|<span data-ttu-id="30dff-274">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-274">win:UInt64</span></span>|<span data-ttu-id="30dff-275">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-275">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="30dff-276">NumRetired</span><span class="sxs-lookup"><span data-stu-id="30dff-276">NumRetired</span></span>|<span data-ttu-id="30dff-277">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-277">win:UInt64</span></span>|<span data-ttu-id="30dff-278">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-278">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="30dff-279">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-279">ClrInstanceID</span></span>|<span data-ttu-id="30dff-280">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-280">Win:UInt16</span></span>|<span data-ttu-id="30dff-281">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-281">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="30dff-282">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="30dff-282">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="30dff-283">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-284">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-284">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-285">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-286">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-286">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-287">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-288">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-289">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-289">Event</span></span>|<span data-ttu-id="30dff-290">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-290">Event ID</span></span>|<span data-ttu-id="30dff-291">발생 시기</span><span class="sxs-lookup"><span data-stu-id="30dff-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="30dff-292">46</span><span class="sxs-lookup"><span data-stu-id="30dff-292">46</span></span>|<span data-ttu-id="30dff-293">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-293">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="30dff-294">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-295">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-295">Field name</span></span>|<span data-ttu-id="30dff-296">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-296">Data type</span></span>|<span data-ttu-id="30dff-297">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-298">개수</span><span class="sxs-lookup"><span data-stu-id="30dff-298">Count</span></span>|<span data-ttu-id="30dff-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-299">win:UInt64</span></span>|<span data-ttu-id="30dff-300">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-300">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="30dff-301">NumRetired</span><span class="sxs-lookup"><span data-stu-id="30dff-301">NumRetired</span></span>|<span data-ttu-id="30dff-302">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-302">win:UInt64</span></span>|<span data-ttu-id="30dff-303">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-303">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="30dff-304">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-304">ClrInstanceID</span></span>|<span data-ttu-id="30dff-305">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-305">Win:UInt16</span></span>|<span data-ttu-id="30dff-306">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-306">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="30dff-307">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="30dff-307">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="30dff-308">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-308">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-309">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-309">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-310">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-310">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-311">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-311">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-312">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-312">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-313">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-313">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-314">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-314">Event</span></span>|<span data-ttu-id="30dff-315">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-315">Event ID</span></span>|<span data-ttu-id="30dff-316">발생 시기</span><span class="sxs-lookup"><span data-stu-id="30dff-316">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="30dff-317">47</span><span class="sxs-lookup"><span data-stu-id="30dff-317">47</span></span>|<span data-ttu-id="30dff-318">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-318">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="30dff-319">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-319">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-320">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-320">Field name</span></span>|<span data-ttu-id="30dff-321">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-321">Data type</span></span>|<span data-ttu-id="30dff-322">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-322">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-323">개수</span><span class="sxs-lookup"><span data-stu-id="30dff-323">Count</span></span>|<span data-ttu-id="30dff-324">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-324">win:UInt64</span></span>|<span data-ttu-id="30dff-325">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-325">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="30dff-326">NumRetired</span><span class="sxs-lookup"><span data-stu-id="30dff-326">NumRetired</span></span>|<span data-ttu-id="30dff-327">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-327">win:UInt64</span></span>|<span data-ttu-id="30dff-328">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-328">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="30dff-329">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-329">ClrInstanceID</span></span>|<span data-ttu-id="30dff-330">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-330">Win:UInt16</span></span>|<span data-ttu-id="30dff-331">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-331">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="30dff-332">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="30dff-332">IOThreadTerminate</span></span>  
 <span data-ttu-id="30dff-333">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-333">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30dff-334">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="30dff-334">Keyword for raising the event</span></span>|<span data-ttu-id="30dff-335">수준</span><span class="sxs-lookup"><span data-stu-id="30dff-335">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30dff-336">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="30dff-336">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="30dff-337">정보(4)</span><span class="sxs-lookup"><span data-stu-id="30dff-337">Informational (4)</span></span>|  
  
 <span data-ttu-id="30dff-338">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-338">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30dff-339">이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-339">Event</span></span>|<span data-ttu-id="30dff-340">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="30dff-340">Event ID</span></span>|<span data-ttu-id="30dff-341">발생 시기</span><span class="sxs-lookup"><span data-stu-id="30dff-341">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="30dff-342">45</span><span class="sxs-lookup"><span data-stu-id="30dff-342">45</span></span>|<span data-ttu-id="30dff-343">스레드 풀에서 i/o 스레드가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-343">An I/O thread is terminated in the thread pool.</span></span>|  
  
 <span data-ttu-id="30dff-344">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-344">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30dff-345">필드 이름</span><span class="sxs-lookup"><span data-stu-id="30dff-345">Field name</span></span>|<span data-ttu-id="30dff-346">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="30dff-346">Data type</span></span>|<span data-ttu-id="30dff-347">Description</span><span class="sxs-lookup"><span data-stu-id="30dff-347">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30dff-348">개수</span><span class="sxs-lookup"><span data-stu-id="30dff-348">Count</span></span>|<span data-ttu-id="30dff-349">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-349">win:UInt64</span></span>|<span data-ttu-id="30dff-350">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-350">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="30dff-351">NumRetired</span><span class="sxs-lookup"><span data-stu-id="30dff-351">NumRetired</span></span>|<span data-ttu-id="30dff-352">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="30dff-352">win:UInt64</span></span>|<span data-ttu-id="30dff-353">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-353">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="30dff-354">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30dff-354">ClrInstanceID</span></span>|<span data-ttu-id="30dff-355">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30dff-355">Win:UInt16</span></span>|<span data-ttu-id="30dff-356">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="30dff-356">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30dff-357">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30dff-357">See also</span></span>

- [<span data-ttu-id="30dff-358">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="30dff-358">CLR ETW Events</span></span>](clr-etw-events.md)
