---
title: 스레드 풀 ETW 이벤트
description: .NET의 스레드에 대 한 정보를 수집 하는 스레드 풀 ETW 이벤트를 검토 합니다. 스레드 풀 이벤트는 작업자 스레드 풀 이벤트 또는 i/o 스레드 풀 이벤트입니다.
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: 8b00c20e82ee1b1efa6a8a123e66a4cfc239143b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236171"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="5a52d-104">스레드 풀 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-104">Thread Pool ETW Events</span></span>

<span data-ttu-id="5a52d-105">이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-105">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="5a52d-106">스레드 풀 이벤트에는 다음과 같은 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-106">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="5a52d-107">[작업자 스레드 풀 이벤트](#worker-thread-pool-events). 이러한 스레드 풀 이벤트는 애플리케이션에서 스레드 풀을 사용하는 방식에 대한 정보 및 작업 부하가 동시성 제어에 미치는 영향에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-107">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="5a52d-108">[I/O 스레드 풀 이벤트](#io-thread-events). 이러한 스레드 풀 이벤트는 스레드 풀에서 생성되거나, 만료되거나, 만료되지 않거나, 종료된 I/O 스레드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-108">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="5a52d-109">작업자 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-109">Worker Thread Pool Events</span></span>

 <span data-ttu-id="5a52d-110">이러한 이벤트는 런타임의 작업자 스레드 풀과 관련이 있으며, 스레드 이벤트에 대한 알림을 제공합니다(예: 스레드가 만들어지거나 중지될 때).</span><span class="sxs-lookup"><span data-stu-id="5a52d-110">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="5a52d-111">작업자 스레드 풀은 동시성 제어를 위해 측정된 처리량을 기준으로 스레드 수가 계산되는 자동 선택 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-111">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="5a52d-112">작업자 스레드 풀 이벤트는 애플리케이션이 스레드 풀을 사용하는 방법 그리고 특정 작업 부하가 동시성 제어에 미칠 수 있는 영향을 이해하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-112">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="5a52d-113">ThreadPoolWorkerThreadStart 및 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="5a52d-113">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  

 <span data-ttu-id="5a52d-114">다음 표에서는 이러한 이벤트의 키워드 및 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-114">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="5a52d-115">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a52d-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="5a52d-116">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-116">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-117">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-118">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-118">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-119">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-119">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-120">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-120">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-121">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-121">Event</span></span>|<span data-ttu-id="5a52d-122">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-122">Event ID</span></span>|<span data-ttu-id="5a52d-123">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5a52d-123">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="5a52d-124">50</span><span class="sxs-lookup"><span data-stu-id="5a52d-124">50</span></span>|<span data-ttu-id="5a52d-125">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-125">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="5a52d-126">51</span><span class="sxs-lookup"><span data-stu-id="5a52d-126">51</span></span>|<span data-ttu-id="5a52d-127">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-127">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="5a52d-128">52</span><span class="sxs-lookup"><span data-stu-id="5a52d-128">52</span></span>|<span data-ttu-id="5a52d-129">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-129">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="5a52d-130">53</span><span class="sxs-lookup"><span data-stu-id="5a52d-130">53</span></span>|<span data-ttu-id="5a52d-131">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-131">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="5a52d-132">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-132">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-133">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-133">Field name</span></span>|<span data-ttu-id="5a52d-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-134">Data type</span></span>|<span data-ttu-id="5a52d-135">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-135">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-136">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="5a52d-136">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="5a52d-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5a52d-137">win:UInt32</span></span>|<span data-ttu-id="5a52d-138">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-138">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="5a52d-139">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="5a52d-139">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="5a52d-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5a52d-140">win:UInt32</span></span>|<span data-ttu-id="5a52d-141">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-141">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="5a52d-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-142">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-143">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-143">Win:UInt16</span></span>|<span data-ttu-id="5a52d-144">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="5a52d-145">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="5a52d-145">ThreadPoolWorkerThreadAdjustment</span></span>  

 <span data-ttu-id="5a52d-146">이러한 스레드 풀 이벤트는 스레드 삽입(동시성 제어) 알고리즘의 동작을 이해하고 디버깅하기 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-146">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="5a52d-147">이 정보는 작업자 스레드 풀에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-147">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="5a52d-148">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="5a52d-148">ThreadPoolWorkerThreadAdjustmentSample</span></span>  

 <span data-ttu-id="5a52d-149">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-149">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-150">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-150">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-151">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-151">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-152">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-152">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-153">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-153">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-154">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-154">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-155">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-155">Event</span></span>|<span data-ttu-id="5a52d-156">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-156">Event ID</span></span>|<span data-ttu-id="5a52d-157">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-157">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="5a52d-158">54</span><span class="sxs-lookup"><span data-stu-id="5a52d-158">54</span></span>|<span data-ttu-id="5a52d-159">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-159">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="5a52d-160">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-160">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-161">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-161">Field name</span></span>|<span data-ttu-id="5a52d-162">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-162">Data type</span></span>|<span data-ttu-id="5a52d-163">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-163">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-164">처리량</span><span class="sxs-lookup"><span data-stu-id="5a52d-164">Throughput</span></span>|<span data-ttu-id="5a52d-165">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-165">win:Double</span></span>|<span data-ttu-id="5a52d-166">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-166">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="5a52d-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-167">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-168">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-168">Win:UInt16</span></span>|<span data-ttu-id="5a52d-169">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="5a52d-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="5a52d-170">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  

 <span data-ttu-id="5a52d-171">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-171">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-172">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-172">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-173">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-173">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-174">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-174">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-175">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-175">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-176">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-176">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-177">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-177">Event</span></span>|<span data-ttu-id="5a52d-178">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-178">Event ID</span></span>|<span data-ttu-id="5a52d-179">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-179">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="5a52d-180">55</span><span class="sxs-lookup"><span data-stu-id="5a52d-180">55</span></span>|<span data-ttu-id="5a52d-181">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-181">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="5a52d-182">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-182">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-183">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-183">Field name</span></span>|<span data-ttu-id="5a52d-184">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-184">Data type</span></span>|<span data-ttu-id="5a52d-185">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-185">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-186">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="5a52d-186">AverageThroughput</span></span>|<span data-ttu-id="5a52d-187">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-187">win:Double</span></span>|<span data-ttu-id="5a52d-188">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-188">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="5a52d-189">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="5a52d-189">NewWorkerThreadCount</span></span>|<span data-ttu-id="5a52d-190">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5a52d-190">win:UInt32</span></span>|<span data-ttu-id="5a52d-191">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-191">New number of active worker threads.</span></span>|  
|<span data-ttu-id="5a52d-192">이유</span><span class="sxs-lookup"><span data-stu-id="5a52d-192">Reason</span></span>|<span data-ttu-id="5a52d-193">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="5a52d-193">win:UInt32</span></span>|<span data-ttu-id="5a52d-194">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-194">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="5a52d-195">0x00 - 준비</span><span class="sxs-lookup"><span data-stu-id="5a52d-195">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="5a52d-196">0x01 - 초기화 중</span><span class="sxs-lookup"><span data-stu-id="5a52d-196">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="5a52d-197">0x02 - 무작위 이동</span><span class="sxs-lookup"><span data-stu-id="5a52d-197">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="5a52d-198">0x03 - 오르기 이동</span><span class="sxs-lookup"><span data-stu-id="5a52d-198">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="5a52d-199">0x04 - 포인트 변경</span><span class="sxs-lookup"><span data-stu-id="5a52d-199">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="5a52d-200">0x05 - 안정화 중</span><span class="sxs-lookup"><span data-stu-id="5a52d-200">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="5a52d-201">0x06 - 고갈</span><span class="sxs-lookup"><span data-stu-id="5a52d-201">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="5a52d-202">0x07 - 스레드 시간 초과</span><span class="sxs-lookup"><span data-stu-id="5a52d-202">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="5a52d-203">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-203">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-204">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-204">Win:UInt16</span></span>|<span data-ttu-id="5a52d-205">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-205">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="5a52d-206">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="5a52d-206">ThreadPoolWorkerThreadAdjustmentStats</span></span>  

 <span data-ttu-id="5a52d-207">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-207">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-208">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-208">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-209">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-209">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-210">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-210">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-211">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-211">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-212">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-212">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-213">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-213">Event</span></span>|<span data-ttu-id="5a52d-214">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-214">Event ID</span></span>|<span data-ttu-id="5a52d-215">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-215">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="5a52d-216">56</span><span class="sxs-lookup"><span data-stu-id="5a52d-216">56</span></span>|<span data-ttu-id="5a52d-217">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-217">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="5a52d-218">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-218">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-219">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-219">Field name</span></span>|<span data-ttu-id="5a52d-220">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-220">Data type</span></span>|<span data-ttu-id="5a52d-221">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-221">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-222">기간</span><span class="sxs-lookup"><span data-stu-id="5a52d-222">Duration</span></span>|<span data-ttu-id="5a52d-223">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-223">win:Double</span></span>|<span data-ttu-id="5a52d-224">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-224">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="5a52d-225">처리량</span><span class="sxs-lookup"><span data-stu-id="5a52d-225">Throughput</span></span>|<span data-ttu-id="5a52d-226">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-226">win:Double</span></span>|<span data-ttu-id="5a52d-227">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-227">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="5a52d-228">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="5a52d-228">ThreadWave</span></span>|<span data-ttu-id="5a52d-229">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-229">win:Double</span></span>|<span data-ttu-id="5a52d-230">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-230">Reserved for internal use.</span></span>|  
|<span data-ttu-id="5a52d-231">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="5a52d-231">ThroughputWave</span></span>|<span data-ttu-id="5a52d-232">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-232">win:Double</span></span>|<span data-ttu-id="5a52d-233">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-233">Reserved for internal use.</span></span>|  
|<span data-ttu-id="5a52d-234">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="5a52d-234">ThroughputErrorEstimate</span></span>|<span data-ttu-id="5a52d-235">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-235">win:Double</span></span>|<span data-ttu-id="5a52d-236">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-236">Reserved for internal use.</span></span>|  
|<span data-ttu-id="5a52d-237">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="5a52d-237">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="5a52d-238">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-238">win:Double</span></span>|<span data-ttu-id="5a52d-239">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-239">Reserved for internal use.</span></span>|  
|<span data-ttu-id="5a52d-240">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="5a52d-240">ThroughputRatio</span></span>|<span data-ttu-id="5a52d-241">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-241">win:Double</span></span>|<span data-ttu-id="5a52d-242">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-242">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="5a52d-243">신뢰도</span><span class="sxs-lookup"><span data-stu-id="5a52d-243">Confidence</span></span>|<span data-ttu-id="5a52d-244">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-244">win:Double</span></span>|<span data-ttu-id="5a52d-245">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-245">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="5a52d-246">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="5a52d-246">NewcontrolSetting</span></span>|<span data-ttu-id="5a52d-247">win:Double</span><span class="sxs-lookup"><span data-stu-id="5a52d-247">win:Double</span></span>|<span data-ttu-id="5a52d-248">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-248">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="5a52d-249">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="5a52d-249">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="5a52d-250">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-250">Win:UInt16</span></span>|<span data-ttu-id="5a52d-251">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-251">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="5a52d-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-252">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-253">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-253">Win:UInt16</span></span>|<span data-ttu-id="5a52d-254">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="5a52d-255">I/O 스레드 이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-255">I/O Thread Events</span></span>  

 <span data-ttu-id="5a52d-256">이러한 스레드 풀 이벤트는 비동기적인 I/O 스레드 풀(완료 포트)에서 스레드에 대해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-256">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="5a52d-257">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="5a52d-257">IOThreadCreate_V1</span></span>  

 <span data-ttu-id="5a52d-258">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-258">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-259">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-259">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-260">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-260">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-261">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-261">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-262">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-262">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-263">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-263">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-264">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-264">Event</span></span>|<span data-ttu-id="5a52d-265">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-265">Event ID</span></span>|<span data-ttu-id="5a52d-266">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5a52d-266">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="5a52d-267">44</span><span class="sxs-lookup"><span data-stu-id="5a52d-267">44</span></span>|<span data-ttu-id="5a52d-268">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-268">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="5a52d-269">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-269">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-270">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-270">Field name</span></span>|<span data-ttu-id="5a52d-271">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-271">Data type</span></span>|<span data-ttu-id="5a52d-272">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-272">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-273">개수</span><span class="sxs-lookup"><span data-stu-id="5a52d-273">Count</span></span>|<span data-ttu-id="5a52d-274">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-274">win:UInt64</span></span>|<span data-ttu-id="5a52d-275">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-275">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="5a52d-276">NumRetired</span><span class="sxs-lookup"><span data-stu-id="5a52d-276">NumRetired</span></span>|<span data-ttu-id="5a52d-277">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-277">win:UInt64</span></span>|<span data-ttu-id="5a52d-278">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-278">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="5a52d-279">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-279">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-280">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-280">Win:UInt16</span></span>|<span data-ttu-id="5a52d-281">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-281">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="5a52d-282">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="5a52d-282">IOThreadRetire_V1</span></span>  

 <span data-ttu-id="5a52d-283">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-284">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-284">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-285">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-286">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-286">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-287">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-288">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-289">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-289">Event</span></span>|<span data-ttu-id="5a52d-290">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-290">Event ID</span></span>|<span data-ttu-id="5a52d-291">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5a52d-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="5a52d-292">46</span><span class="sxs-lookup"><span data-stu-id="5a52d-292">46</span></span>|<span data-ttu-id="5a52d-293">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-293">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="5a52d-294">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-295">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-295">Field name</span></span>|<span data-ttu-id="5a52d-296">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-296">Data type</span></span>|<span data-ttu-id="5a52d-297">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-298">개수</span><span class="sxs-lookup"><span data-stu-id="5a52d-298">Count</span></span>|<span data-ttu-id="5a52d-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-299">win:UInt64</span></span>|<span data-ttu-id="5a52d-300">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-300">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="5a52d-301">NumRetired</span><span class="sxs-lookup"><span data-stu-id="5a52d-301">NumRetired</span></span>|<span data-ttu-id="5a52d-302">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-302">win:UInt64</span></span>|<span data-ttu-id="5a52d-303">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-303">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="5a52d-304">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-304">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-305">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-305">Win:UInt16</span></span>|<span data-ttu-id="5a52d-306">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-306">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="5a52d-307">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="5a52d-307">IOThreadUnretire_V1</span></span>  

 <span data-ttu-id="5a52d-308">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-308">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-309">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-309">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-310">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-310">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-311">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-311">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-312">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-312">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-313">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-313">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-314">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-314">Event</span></span>|<span data-ttu-id="5a52d-315">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-315">Event ID</span></span>|<span data-ttu-id="5a52d-316">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5a52d-316">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="5a52d-317">47</span><span class="sxs-lookup"><span data-stu-id="5a52d-317">47</span></span>|<span data-ttu-id="5a52d-318">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-318">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="5a52d-319">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-319">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-320">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-320">Field name</span></span>|<span data-ttu-id="5a52d-321">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-321">Data type</span></span>|<span data-ttu-id="5a52d-322">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-322">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-323">개수</span><span class="sxs-lookup"><span data-stu-id="5a52d-323">Count</span></span>|<span data-ttu-id="5a52d-324">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-324">win:UInt64</span></span>|<span data-ttu-id="5a52d-325">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-325">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="5a52d-326">NumRetired</span><span class="sxs-lookup"><span data-stu-id="5a52d-326">NumRetired</span></span>|<span data-ttu-id="5a52d-327">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-327">win:UInt64</span></span>|<span data-ttu-id="5a52d-328">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-328">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="5a52d-329">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-329">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-330">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-330">Win:UInt16</span></span>|<span data-ttu-id="5a52d-331">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-331">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="5a52d-332">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="5a52d-332">IOThreadTerminate</span></span>  

 <span data-ttu-id="5a52d-333">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-333">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="5a52d-334">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="5a52d-334">Keyword for raising the event</span></span>|<span data-ttu-id="5a52d-335">Level</span><span class="sxs-lookup"><span data-stu-id="5a52d-335">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="5a52d-336">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="5a52d-336">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="5a52d-337">정보(4)</span><span class="sxs-lookup"><span data-stu-id="5a52d-337">Informational (4)</span></span>|  
  
 <span data-ttu-id="5a52d-338">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-338">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="5a52d-339">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-339">Event</span></span>|<span data-ttu-id="5a52d-340">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="5a52d-340">Event ID</span></span>|<span data-ttu-id="5a52d-341">발생 시기</span><span class="sxs-lookup"><span data-stu-id="5a52d-341">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="5a52d-342">45</span><span class="sxs-lookup"><span data-stu-id="5a52d-342">45</span></span>|<span data-ttu-id="5a52d-343">스레드 풀에서 i/o 스레드가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-343">An I/O thread is terminated in the thread pool.</span></span>|  
  
 <span data-ttu-id="5a52d-344">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-344">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="5a52d-345">필드 이름</span><span class="sxs-lookup"><span data-stu-id="5a52d-345">Field name</span></span>|<span data-ttu-id="5a52d-346">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a52d-346">Data type</span></span>|<span data-ttu-id="5a52d-347">Description</span><span class="sxs-lookup"><span data-stu-id="5a52d-347">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="5a52d-348">개수</span><span class="sxs-lookup"><span data-stu-id="5a52d-348">Count</span></span>|<span data-ttu-id="5a52d-349">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-349">win:UInt64</span></span>|<span data-ttu-id="5a52d-350">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-350">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="5a52d-351">NumRetired</span><span class="sxs-lookup"><span data-stu-id="5a52d-351">NumRetired</span></span>|<span data-ttu-id="5a52d-352">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="5a52d-352">win:UInt64</span></span>|<span data-ttu-id="5a52d-353">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-353">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="5a52d-354">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="5a52d-354">ClrInstanceID</span></span>|<span data-ttu-id="5a52d-355">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="5a52d-355">Win:UInt16</span></span>|<span data-ttu-id="5a52d-356">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a52d-356">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a52d-357">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a52d-357">See also</span></span>

- [<span data-ttu-id="5a52d-358">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="5a52d-358">CLR ETW Events</span></span>](clr-etw-events.md)
