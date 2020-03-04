---
title: 스레드 풀 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: 249d0607ddd280bcb4e9cf3ef34b28ff8ada3b04
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240495"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="b27da-102">스레드 풀 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b27da-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="b27da-103">이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="b27da-104">스레드 풀 이벤트에는 다음과 같은 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="b27da-105">[작업자 스레드 풀 이벤트](#worker-thread-pool-events). 이러한 스레드 풀 이벤트는 애플리케이션에서 스레드 풀을 사용하는 방식에 대한 정보 및 작업 부하가 동시성 제어에 미치는 영향에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="b27da-106">[I/O 스레드 풀 이벤트](#io-thread-events). 이러한 스레드 풀 이벤트는 스레드 풀에서 생성되거나, 만료되거나, 만료되지 않거나, 종료된 I/O 스레드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="b27da-107">작업자 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="b27da-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="b27da-108">이러한 이벤트는 런타임의 작업자 스레드 풀과 관련이 있으며, 스레드 이벤트에 대한 알림을 제공합니다(예: 스레드가 만들어지거나 중지될 때).</span><span class="sxs-lookup"><span data-stu-id="b27da-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="b27da-109">작업자 스레드 풀은 동시성 제어를 위해 측정된 처리량을 기준으로 스레드 수가 계산되는 자동 선택 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="b27da-110">작업자 스레드 풀 이벤트는 애플리케이션이 스레드 풀을 사용하는 방법 그리고 특정 작업 부하가 동시성 제어에 미칠 수 있는 영향을 이해하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="b27da-111">ThreadPoolWorkerThreadStart 및 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="b27da-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="b27da-112">다음 표에서는 이러한 이벤트의 키워드 및 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="b27da-113">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b27da-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b27da-114">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-114">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-115">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-117">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-118">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-119">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-119">Event</span></span>|<span data-ttu-id="b27da-120">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-120">Event ID</span></span>|<span data-ttu-id="b27da-121">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b27da-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="b27da-122">50</span><span class="sxs-lookup"><span data-stu-id="b27da-122">50</span></span>|<span data-ttu-id="b27da-123">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="b27da-124">51</span><span class="sxs-lookup"><span data-stu-id="b27da-124">51</span></span>|<span data-ttu-id="b27da-125">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="b27da-126">52</span><span class="sxs-lookup"><span data-stu-id="b27da-126">52</span></span>|<span data-ttu-id="b27da-127">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="b27da-128">53</span><span class="sxs-lookup"><span data-stu-id="b27da-128">53</span></span>|<span data-ttu-id="b27da-129">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="b27da-130">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-131">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-131">Field name</span></span>|<span data-ttu-id="b27da-132">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-132">Data type</span></span>|<span data-ttu-id="b27da-133">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b27da-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="b27da-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b27da-135">win:UInt32</span></span>|<span data-ttu-id="b27da-136">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="b27da-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b27da-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="b27da-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b27da-138">win:UInt32</span></span>|<span data-ttu-id="b27da-139">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="b27da-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-140">ClrInstanceID</span></span>|<span data-ttu-id="b27da-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-141">Win:UInt16</span></span>|<span data-ttu-id="b27da-142">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="b27da-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="b27da-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="b27da-144">이러한 스레드 풀 이벤트는 스레드 삽입(동시성 제어) 알고리즘의 동작을 이해하고 디버깅하기 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="b27da-145">이 정보는 작업자 스레드 풀에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="b27da-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="b27da-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="b27da-147">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-148">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-148">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-149">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-151">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-152">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-153">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-153">Event</span></span>|<span data-ttu-id="b27da-154">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-154">Event ID</span></span>|<span data-ttu-id="b27da-155">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="b27da-156">54</span><span class="sxs-lookup"><span data-stu-id="b27da-156">54</span></span>|<span data-ttu-id="b27da-157">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="b27da-158">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-159">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-159">Field name</span></span>|<span data-ttu-id="b27da-160">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-160">Data type</span></span>|<span data-ttu-id="b27da-161">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-162">처리량</span><span class="sxs-lookup"><span data-stu-id="b27da-162">Throughput</span></span>|<span data-ttu-id="b27da-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-163">win:Double</span></span>|<span data-ttu-id="b27da-164">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="b27da-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-165">ClrInstanceID</span></span>|<span data-ttu-id="b27da-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-166">Win:UInt16</span></span>|<span data-ttu-id="b27da-167">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="b27da-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="b27da-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="b27da-169">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-170">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-170">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-171">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-173">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-174">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-175">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-175">Event</span></span>|<span data-ttu-id="b27da-176">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-176">Event ID</span></span>|<span data-ttu-id="b27da-177">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="b27da-178">55</span><span class="sxs-lookup"><span data-stu-id="b27da-178">55</span></span>|<span data-ttu-id="b27da-179">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="b27da-180">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-181">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-181">Field name</span></span>|<span data-ttu-id="b27da-182">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-182">Data type</span></span>|<span data-ttu-id="b27da-183">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="b27da-184">AverageThroughput</span></span>|<span data-ttu-id="b27da-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-185">win:Double</span></span>|<span data-ttu-id="b27da-186">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="b27da-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b27da-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="b27da-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b27da-188">win:UInt32</span></span>|<span data-ttu-id="b27da-189">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="b27da-190">Reason</span><span class="sxs-lookup"><span data-stu-id="b27da-190">Reason</span></span>|<span data-ttu-id="b27da-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b27da-191">win:UInt32</span></span>|<span data-ttu-id="b27da-192">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="b27da-193">0x00 - 준비</span><span class="sxs-lookup"><span data-stu-id="b27da-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="b27da-194">0x01 - 초기화 중</span><span class="sxs-lookup"><span data-stu-id="b27da-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="b27da-195">0x02 - 무작위 이동</span><span class="sxs-lookup"><span data-stu-id="b27da-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="b27da-196">0x03 - 오르기 이동</span><span class="sxs-lookup"><span data-stu-id="b27da-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="b27da-197">0x04 - 포인트 변경</span><span class="sxs-lookup"><span data-stu-id="b27da-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="b27da-198">0x05 - 안정화 중</span><span class="sxs-lookup"><span data-stu-id="b27da-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="b27da-199">0x06 - 고갈</span><span class="sxs-lookup"><span data-stu-id="b27da-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="b27da-200">0x07 - 스레드 시간 초과</span><span class="sxs-lookup"><span data-stu-id="b27da-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="b27da-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-201">ClrInstanceID</span></span>|<span data-ttu-id="b27da-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-202">Win:UInt16</span></span>|<span data-ttu-id="b27da-203">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="b27da-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="b27da-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="b27da-205">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-206">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-206">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-207">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-209">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-210">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-211">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-211">Event</span></span>|<span data-ttu-id="b27da-212">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-212">Event ID</span></span>|<span data-ttu-id="b27da-213">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="b27da-214">56</span><span class="sxs-lookup"><span data-stu-id="b27da-214">56</span></span>|<span data-ttu-id="b27da-215">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="b27da-216">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-217">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-217">Field name</span></span>|<span data-ttu-id="b27da-218">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-218">Data type</span></span>|<span data-ttu-id="b27da-219">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-220">기간</span><span class="sxs-lookup"><span data-stu-id="b27da-220">Duration</span></span>|<span data-ttu-id="b27da-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-221">win:Double</span></span>|<span data-ttu-id="b27da-222">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="b27da-223">처리량</span><span class="sxs-lookup"><span data-stu-id="b27da-223">Throughput</span></span>|<span data-ttu-id="b27da-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-224">win:Double</span></span>|<span data-ttu-id="b27da-225">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="b27da-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="b27da-226">ThreadWave</span></span>|<span data-ttu-id="b27da-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-227">win:Double</span></span>|<span data-ttu-id="b27da-228">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b27da-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="b27da-229">ThroughputWave</span></span>|<span data-ttu-id="b27da-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-230">win:Double</span></span>|<span data-ttu-id="b27da-231">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b27da-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="b27da-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="b27da-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-233">win:Double</span></span>|<span data-ttu-id="b27da-234">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b27da-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="b27da-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="b27da-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-236">win:Double</span></span>|<span data-ttu-id="b27da-237">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b27da-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="b27da-238">ThroughputRatio</span></span>|<span data-ttu-id="b27da-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-239">win:Double</span></span>|<span data-ttu-id="b27da-240">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="b27da-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="b27da-241">Confidence</span></span>|<span data-ttu-id="b27da-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-242">win:Double</span></span>|<span data-ttu-id="b27da-243">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="b27da-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="b27da-244">NewcontrolSetting</span></span>|<span data-ttu-id="b27da-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="b27da-245">win:Double</span></span>|<span data-ttu-id="b27da-246">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="b27da-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="b27da-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="b27da-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-248">Win:UInt16</span></span>|<span data-ttu-id="b27da-249">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="b27da-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-250">ClrInstanceID</span></span>|<span data-ttu-id="b27da-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-251">Win:UInt16</span></span>|<span data-ttu-id="b27da-252">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="b27da-253">I/O 스레드 이벤트</span><span class="sxs-lookup"><span data-stu-id="b27da-253">I/O Thread Events</span></span>  
 <span data-ttu-id="b27da-254">이러한 스레드 풀 이벤트는 비동기적인 I/O 스레드 풀(완료 포트)에서 스레드에 대해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="b27da-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="b27da-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="b27da-256">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-257">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-257">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-258">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-260">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-261">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-262">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-262">Event</span></span>|<span data-ttu-id="b27da-263">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-263">Event ID</span></span>|<span data-ttu-id="b27da-264">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b27da-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="b27da-265">44</span><span class="sxs-lookup"><span data-stu-id="b27da-265">44</span></span>|<span data-ttu-id="b27da-266">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="b27da-267">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-268">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-268">Field name</span></span>|<span data-ttu-id="b27da-269">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-269">Data type</span></span>|<span data-ttu-id="b27da-270">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-271">개수</span><span class="sxs-lookup"><span data-stu-id="b27da-271">Count</span></span>|<span data-ttu-id="b27da-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-272">win:UInt64</span></span>|<span data-ttu-id="b27da-273">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="b27da-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b27da-274">NumRetired</span></span>|<span data-ttu-id="b27da-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-275">win:UInt64</span></span>|<span data-ttu-id="b27da-276">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="b27da-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-277">ClrInstanceID</span></span>|<span data-ttu-id="b27da-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-278">Win:UInt16</span></span>|<span data-ttu-id="b27da-279">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="b27da-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="b27da-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="b27da-281">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-282">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-282">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-283">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-285">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-286">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-287">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-287">Event</span></span>|<span data-ttu-id="b27da-288">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-288">Event ID</span></span>|<span data-ttu-id="b27da-289">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b27da-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="b27da-290">46</span><span class="sxs-lookup"><span data-stu-id="b27da-290">46</span></span>|<span data-ttu-id="b27da-291">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="b27da-292">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-293">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-293">Field name</span></span>|<span data-ttu-id="b27da-294">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-294">Data type</span></span>|<span data-ttu-id="b27da-295">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-296">개수</span><span class="sxs-lookup"><span data-stu-id="b27da-296">Count</span></span>|<span data-ttu-id="b27da-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-297">win:UInt64</span></span>|<span data-ttu-id="b27da-298">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="b27da-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b27da-299">NumRetired</span></span>|<span data-ttu-id="b27da-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-300">win:UInt64</span></span>|<span data-ttu-id="b27da-301">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b27da-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-302">ClrInstanceID</span></span>|<span data-ttu-id="b27da-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-303">Win:UInt16</span></span>|<span data-ttu-id="b27da-304">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="b27da-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="b27da-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="b27da-306">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-307">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-307">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-308">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-310">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-311">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-312">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-312">Event</span></span>|<span data-ttu-id="b27da-313">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-313">Event ID</span></span>|<span data-ttu-id="b27da-314">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b27da-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="b27da-315">47</span><span class="sxs-lookup"><span data-stu-id="b27da-315">47</span></span>|<span data-ttu-id="b27da-316">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="b27da-317">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-318">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-318">Field name</span></span>|<span data-ttu-id="b27da-319">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-319">Data type</span></span>|<span data-ttu-id="b27da-320">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-321">개수</span><span class="sxs-lookup"><span data-stu-id="b27da-321">Count</span></span>|<span data-ttu-id="b27da-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-322">win:UInt64</span></span>|<span data-ttu-id="b27da-323">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="b27da-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b27da-324">NumRetired</span></span>|<span data-ttu-id="b27da-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-325">win:UInt64</span></span>|<span data-ttu-id="b27da-326">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b27da-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-327">ClrInstanceID</span></span>|<span data-ttu-id="b27da-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-328">Win:UInt16</span></span>|<span data-ttu-id="b27da-329">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="b27da-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="b27da-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="b27da-331">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b27da-332">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b27da-332">Keyword for raising the event</span></span>|<span data-ttu-id="b27da-333">Level</span><span class="sxs-lookup"><span data-stu-id="b27da-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b27da-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b27da-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b27da-335">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b27da-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="b27da-336">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b27da-337">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="b27da-337">Event</span></span>|<span data-ttu-id="b27da-338">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b27da-338">Event ID</span></span>|<span data-ttu-id="b27da-339">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b27da-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="b27da-340">45</span><span class="sxs-lookup"><span data-stu-id="b27da-340">45</span></span>|<span data-ttu-id="b27da-341">스레드 풀에서 i/o 스레드가 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-341">An I/O thread is terminated in the thread pool.</span></span>|  
  
 <span data-ttu-id="b27da-342">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b27da-343">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b27da-343">Field name</span></span>|<span data-ttu-id="b27da-344">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b27da-344">Data type</span></span>|<span data-ttu-id="b27da-345">설명</span><span class="sxs-lookup"><span data-stu-id="b27da-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b27da-346">개수</span><span class="sxs-lookup"><span data-stu-id="b27da-346">Count</span></span>|<span data-ttu-id="b27da-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-347">win:UInt64</span></span>|<span data-ttu-id="b27da-348">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="b27da-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b27da-349">NumRetired</span></span>|<span data-ttu-id="b27da-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b27da-350">win:UInt64</span></span>|<span data-ttu-id="b27da-351">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b27da-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b27da-352">ClrInstanceID</span></span>|<span data-ttu-id="b27da-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b27da-353">Win:UInt16</span></span>|<span data-ttu-id="b27da-354">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b27da-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b27da-355">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b27da-355">See also</span></span>

- [<span data-ttu-id="b27da-356">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b27da-356">CLR ETW Events</span></span>](clr-etw-events.md)
