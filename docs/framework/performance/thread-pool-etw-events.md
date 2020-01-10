---
title: 스레드 풀 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
ms.openlocfilehash: e1deb17dfdfea4c8b66eb8d836a10bf888727e1a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715897"
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="f8f74-102">스레드 풀 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8f74-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="f8f74-103">이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-103">These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="f8f74-104">스레드 풀 이벤트에는 다음과 같은 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-104">There are two groups of thread pool events:</span></span>  
  
- <span data-ttu-id="f8f74-105">[작업자 스레드 풀 이벤트](#worker-thread-pool-events). 이러한 스레드 풀 이벤트는 애플리케이션에서 스레드 풀을 사용하는 방식에 대한 정보 및 작업 부하가 동시성 제어에 미치는 영향에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-105">[Worker thread pool events](#worker-thread-pool-events), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
- <span data-ttu-id="f8f74-106">[I/O 스레드 풀 이벤트](#io-thread-events). 이러한 스레드 풀 이벤트는 스레드 풀에서 생성되거나, 만료되거나, 만료되지 않거나, 종료된 I/O 스레드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-106">[I/O thread pool events](#io-thread-events), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  

## <a name="worker-thread-pool-events"></a><span data-ttu-id="f8f74-107">작업자 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8f74-107">Worker Thread Pool Events</span></span>
 <span data-ttu-id="f8f74-108">이러한 이벤트는 런타임의 작업자 스레드 풀과 관련이 있으며, 스레드 이벤트에 대한 알림을 제공합니다(예: 스레드가 만들어지거나 중지될 때).</span><span class="sxs-lookup"><span data-stu-id="f8f74-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="f8f74-109">작업자 스레드 풀은 동시성 제어를 위해 측정된 처리량을 기준으로 스레드 수가 계산되는 자동 선택 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="f8f74-110">작업자 스레드 풀 이벤트는 애플리케이션이 스레드 풀을 사용하는 방법 그리고 특정 작업 부하가 동시성 제어에 미칠 수 있는 영향을 이해하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="f8f74-111">ThreadPoolWorkerThreadStart 및 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="f8f74-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="f8f74-112">다음 표에서는 이러한 이벤트의 키워드 및 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="f8f74-113">자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8f74-113">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f8f74-114">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-114">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-115">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-117">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-118">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-119">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-119">Event</span></span>|<span data-ttu-id="f8f74-120">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-120">Event ID</span></span>|<span data-ttu-id="f8f74-121">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f8f74-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="f8f74-122">50</span><span class="sxs-lookup"><span data-stu-id="f8f74-122">50</span></span>|<span data-ttu-id="f8f74-123">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="f8f74-124">51</span><span class="sxs-lookup"><span data-stu-id="f8f74-124">51</span></span>|<span data-ttu-id="f8f74-125">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="f8f74-126">52</span><span class="sxs-lookup"><span data-stu-id="f8f74-126">52</span></span>|<span data-ttu-id="f8f74-127">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="f8f74-128">53</span><span class="sxs-lookup"><span data-stu-id="f8f74-128">53</span></span>|<span data-ttu-id="f8f74-129">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="f8f74-130">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-131">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-131">Field name</span></span>|<span data-ttu-id="f8f74-132">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-132">Data type</span></span>|<span data-ttu-id="f8f74-133">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="f8f74-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="f8f74-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f8f74-135">win:UInt32</span></span>|<span data-ttu-id="f8f74-136">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="f8f74-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="f8f74-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="f8f74-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f8f74-138">win:UInt32</span></span>|<span data-ttu-id="f8f74-139">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="f8f74-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-140">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-141">Win:UInt16</span></span>|<span data-ttu-id="f8f74-142">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="f8f74-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="f8f74-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="f8f74-144">이러한 스레드 풀 이벤트는 스레드 삽입(동시성 제어) 알고리즘의 동작을 이해하고 디버깅하기 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="f8f74-145">이 정보는 작업자 스레드 풀에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="f8f74-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="f8f74-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="f8f74-147">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-148">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-148">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-149">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-151">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-152">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-153">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-153">Event</span></span>|<span data-ttu-id="f8f74-154">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-154">Event ID</span></span>|<span data-ttu-id="f8f74-155">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="f8f74-156">54</span><span class="sxs-lookup"><span data-stu-id="f8f74-156">54</span></span>|<span data-ttu-id="f8f74-157">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="f8f74-158">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-159">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-159">Field name</span></span>|<span data-ttu-id="f8f74-160">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-160">Data type</span></span>|<span data-ttu-id="f8f74-161">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-162">처리량</span><span class="sxs-lookup"><span data-stu-id="f8f74-162">Throughput</span></span>|<span data-ttu-id="f8f74-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-163">win:Double</span></span>|<span data-ttu-id="f8f74-164">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="f8f74-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-165">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-166">Win:UInt16</span></span>|<span data-ttu-id="f8f74-167">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="f8f74-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="f8f74-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="f8f74-169">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-170">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-170">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-171">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-173">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-174">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-175">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-175">Event</span></span>|<span data-ttu-id="f8f74-176">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-176">Event ID</span></span>|<span data-ttu-id="f8f74-177">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="f8f74-178">55</span><span class="sxs-lookup"><span data-stu-id="f8f74-178">55</span></span>|<span data-ttu-id="f8f74-179">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="f8f74-180">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-181">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-181">Field name</span></span>|<span data-ttu-id="f8f74-182">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-182">Data type</span></span>|<span data-ttu-id="f8f74-183">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="f8f74-184">AverageThroughput</span></span>|<span data-ttu-id="f8f74-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-185">win:Double</span></span>|<span data-ttu-id="f8f74-186">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="f8f74-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="f8f74-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="f8f74-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f8f74-188">win:UInt32</span></span>|<span data-ttu-id="f8f74-189">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="f8f74-190">Reason</span><span class="sxs-lookup"><span data-stu-id="f8f74-190">Reason</span></span>|<span data-ttu-id="f8f74-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f8f74-191">win:UInt32</span></span>|<span data-ttu-id="f8f74-192">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="f8f74-193">0x00 - 준비</span><span class="sxs-lookup"><span data-stu-id="f8f74-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="f8f74-194">0x01 - 초기화 중</span><span class="sxs-lookup"><span data-stu-id="f8f74-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="f8f74-195">0x02 - 무작위 이동</span><span class="sxs-lookup"><span data-stu-id="f8f74-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="f8f74-196">0x03 - 오르기 이동</span><span class="sxs-lookup"><span data-stu-id="f8f74-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="f8f74-197">0x04 - 포인트 변경</span><span class="sxs-lookup"><span data-stu-id="f8f74-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="f8f74-198">0x05 - 안정화 중</span><span class="sxs-lookup"><span data-stu-id="f8f74-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="f8f74-199">0x06 - 고갈</span><span class="sxs-lookup"><span data-stu-id="f8f74-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="f8f74-200">0x07 - 스레드 시간 초과</span><span class="sxs-lookup"><span data-stu-id="f8f74-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="f8f74-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-201">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-202">Win:UInt16</span></span>|<span data-ttu-id="f8f74-203">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="f8f74-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="f8f74-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="f8f74-205">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-206">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-206">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-207">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-209">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-210">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-211">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-211">Event</span></span>|<span data-ttu-id="f8f74-212">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-212">Event ID</span></span>|<span data-ttu-id="f8f74-213">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="f8f74-214">56</span><span class="sxs-lookup"><span data-stu-id="f8f74-214">56</span></span>|<span data-ttu-id="f8f74-215">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="f8f74-216">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-217">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-217">Field name</span></span>|<span data-ttu-id="f8f74-218">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-218">Data type</span></span>|<span data-ttu-id="f8f74-219">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-220">지속 시간</span><span class="sxs-lookup"><span data-stu-id="f8f74-220">Duration</span></span>|<span data-ttu-id="f8f74-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-221">win:Double</span></span>|<span data-ttu-id="f8f74-222">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="f8f74-223">처리량</span><span class="sxs-lookup"><span data-stu-id="f8f74-223">Throughput</span></span>|<span data-ttu-id="f8f74-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-224">win:Double</span></span>|<span data-ttu-id="f8f74-225">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="f8f74-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="f8f74-226">ThreadWave</span></span>|<span data-ttu-id="f8f74-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-227">win:Double</span></span>|<span data-ttu-id="f8f74-228">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="f8f74-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="f8f74-229">ThroughputWave</span></span>|<span data-ttu-id="f8f74-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-230">win:Double</span></span>|<span data-ttu-id="f8f74-231">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="f8f74-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="f8f74-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="f8f74-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-233">win:Double</span></span>|<span data-ttu-id="f8f74-234">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="f8f74-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="f8f74-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="f8f74-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-236">win:Double</span></span>|<span data-ttu-id="f8f74-237">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="f8f74-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="f8f74-238">ThroughputRatio</span></span>|<span data-ttu-id="f8f74-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-239">win:Double</span></span>|<span data-ttu-id="f8f74-240">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="f8f74-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="f8f74-241">Confidence</span></span>|<span data-ttu-id="f8f74-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-242">win:Double</span></span>|<span data-ttu-id="f8f74-243">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="f8f74-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="f8f74-244">NewcontrolSetting</span></span>|<span data-ttu-id="f8f74-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="f8f74-245">win:Double</span></span>|<span data-ttu-id="f8f74-246">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="f8f74-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="f8f74-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="f8f74-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-248">Win:UInt16</span></span>|<span data-ttu-id="f8f74-249">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="f8f74-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-250">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-251">Win:UInt16</span></span>|<span data-ttu-id="f8f74-252">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="io-thread-events"></a><span data-ttu-id="f8f74-253">I/O 스레드 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8f74-253">I/O Thread Events</span></span>  
 <span data-ttu-id="f8f74-254">이러한 스레드 풀 이벤트는 비동기적인 I/O 스레드 풀(완료 포트)에서 스레드에 대해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-254">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreate_v1"></a><span data-ttu-id="f8f74-255">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="f8f74-255">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="f8f74-256">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-256">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-257">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-257">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-258">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-258">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-259">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-259">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-260">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-260">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-261">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-261">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-262">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-262">Event</span></span>|<span data-ttu-id="f8f74-263">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-263">Event ID</span></span>|<span data-ttu-id="f8f74-264">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f8f74-264">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="f8f74-265">44</span><span class="sxs-lookup"><span data-stu-id="f8f74-265">44</span></span>|<span data-ttu-id="f8f74-266">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-266">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="f8f74-267">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-267">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-268">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-268">Field name</span></span>|<span data-ttu-id="f8f74-269">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-269">Data type</span></span>|<span data-ttu-id="f8f74-270">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-270">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-271">개수</span><span class="sxs-lookup"><span data-stu-id="f8f74-271">Count</span></span>|<span data-ttu-id="f8f74-272">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-272">win:UInt64</span></span>|<span data-ttu-id="f8f74-273">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-273">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="f8f74-274">NumRetired</span><span class="sxs-lookup"><span data-stu-id="f8f74-274">NumRetired</span></span>|<span data-ttu-id="f8f74-275">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-275">win:UInt64</span></span>|<span data-ttu-id="f8f74-276">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-276">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="f8f74-277">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-277">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-278">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-278">Win:UInt16</span></span>|<span data-ttu-id="f8f74-279">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-279">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretire_v1"></a><span data-ttu-id="f8f74-280">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="f8f74-280">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="f8f74-281">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-281">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-282">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-282">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-283">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-283">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-284">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-284">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-285">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-285">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-286">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-286">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-287">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-287">Event</span></span>|<span data-ttu-id="f8f74-288">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-288">Event ID</span></span>|<span data-ttu-id="f8f74-289">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f8f74-289">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="f8f74-290">46</span><span class="sxs-lookup"><span data-stu-id="f8f74-290">46</span></span>|<span data-ttu-id="f8f74-291">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-291">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="f8f74-292">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-292">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-293">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-293">Field name</span></span>|<span data-ttu-id="f8f74-294">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-294">Data type</span></span>|<span data-ttu-id="f8f74-295">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-295">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-296">개수</span><span class="sxs-lookup"><span data-stu-id="f8f74-296">Count</span></span>|<span data-ttu-id="f8f74-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-297">win:UInt64</span></span>|<span data-ttu-id="f8f74-298">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-298">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="f8f74-299">NumRetired</span><span class="sxs-lookup"><span data-stu-id="f8f74-299">NumRetired</span></span>|<span data-ttu-id="f8f74-300">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-300">win:UInt64</span></span>|<span data-ttu-id="f8f74-301">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-301">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="f8f74-302">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-302">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-303">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-303">Win:UInt16</span></span>|<span data-ttu-id="f8f74-304">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-304">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretire_v1"></a><span data-ttu-id="f8f74-305">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="f8f74-305">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="f8f74-306">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-307">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-307">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-308">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-309">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-309">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-310">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-311">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-312">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-312">Event</span></span>|<span data-ttu-id="f8f74-313">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-313">Event ID</span></span>|<span data-ttu-id="f8f74-314">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f8f74-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="f8f74-315">47</span><span class="sxs-lookup"><span data-stu-id="f8f74-315">47</span></span>|<span data-ttu-id="f8f74-316">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-316">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="f8f74-317">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-317">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-318">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-318">Field name</span></span>|<span data-ttu-id="f8f74-319">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-319">Data type</span></span>|<span data-ttu-id="f8f74-320">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-320">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-321">개수</span><span class="sxs-lookup"><span data-stu-id="f8f74-321">Count</span></span>|<span data-ttu-id="f8f74-322">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-322">win:UInt64</span></span>|<span data-ttu-id="f8f74-323">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-323">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="f8f74-324">NumRetired</span><span class="sxs-lookup"><span data-stu-id="f8f74-324">NumRetired</span></span>|<span data-ttu-id="f8f74-325">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-325">win:UInt64</span></span>|<span data-ttu-id="f8f74-326">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-326">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="f8f74-327">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-327">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-328">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-328">Win:UInt16</span></span>|<span data-ttu-id="f8f74-329">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-329">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="f8f74-330">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="f8f74-330">IOThreadTerminate</span></span>  
 <span data-ttu-id="f8f74-331">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-331">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f8f74-332">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="f8f74-332">Keyword for raising the event</span></span>|<span data-ttu-id="f8f74-333">수준</span><span class="sxs-lookup"><span data-stu-id="f8f74-333">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f8f74-334">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f8f74-334">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f8f74-335">정보(4)</span><span class="sxs-lookup"><span data-stu-id="f8f74-335">Informational (4)</span></span>|  
  
 <span data-ttu-id="f8f74-336">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-336">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f8f74-337">Event</span><span class="sxs-lookup"><span data-stu-id="f8f74-337">Event</span></span>|<span data-ttu-id="f8f74-338">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f8f74-338">Event ID</span></span>|<span data-ttu-id="f8f74-339">발생 시기</span><span class="sxs-lookup"><span data-stu-id="f8f74-339">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="f8f74-340">45</span><span class="sxs-lookup"><span data-stu-id="f8f74-340">45</span></span>|<span data-ttu-id="f8f74-341">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-341">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="f8f74-342">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-342">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f8f74-343">필드 이름</span><span class="sxs-lookup"><span data-stu-id="f8f74-343">Field name</span></span>|<span data-ttu-id="f8f74-344">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f8f74-344">Data type</span></span>|<span data-ttu-id="f8f74-345">설명</span><span class="sxs-lookup"><span data-stu-id="f8f74-345">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f8f74-346">개수</span><span class="sxs-lookup"><span data-stu-id="f8f74-346">Count</span></span>|<span data-ttu-id="f8f74-347">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-347">win:UInt64</span></span>|<span data-ttu-id="f8f74-348">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-348">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="f8f74-349">NumRetired</span><span class="sxs-lookup"><span data-stu-id="f8f74-349">NumRetired</span></span>|<span data-ttu-id="f8f74-350">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f8f74-350">win:UInt64</span></span>|<span data-ttu-id="f8f74-351">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-351">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="f8f74-352">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f8f74-352">ClrInstanceID</span></span>|<span data-ttu-id="f8f74-353">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f8f74-353">Win:UInt16</span></span>|<span data-ttu-id="f8f74-354">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f74-354">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8f74-355">참조</span><span class="sxs-lookup"><span data-stu-id="f8f74-355">See also</span></span>

- [<span data-ttu-id="f8f74-356">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="f8f74-356">CLR ETW Events</span></span>](clr-etw-events.md)
