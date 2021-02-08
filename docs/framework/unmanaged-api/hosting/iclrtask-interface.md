---
description: '자세한 정보: ICLRTask 인터페이스'
title: ICLRTask 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: f48216b19dd2c1d0d0ba64117169b74767dbdf2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799538"
---
# <a name="iclrtask-interface"></a><span data-ttu-id="bc7ea-103">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-103">ICLRTask Interface</span></span>

<span data-ttu-id="bc7ea-104">호스트가 CLR (공용 언어 런타임)에 대 한 요청을 수행 하거나 CLR에 연결 된 작업에 대 한 알림을 제공할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-104">Provides methods that allow the host to make requests of the common language runtime (CLR), or to provide notification to the CLR about the associated task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc7ea-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-105">Methods</span></span>  
  
|<span data-ttu-id="bc7ea-106">메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-106">Method</span></span>|<span data-ttu-id="bc7ea-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc7ea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc7ea-108">Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-108">Abort Method</span></span>](iclrtask-abort-method.md)|<span data-ttu-id="bc7ea-109">현재 인스턴스가 나타내는 작업을 CLR에서 중단 하도록 요청 `ICLRTask` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-109">Requests that the CLR abort the task that the current `ICLRTask` instance represents.</span></span>|  
|[<span data-ttu-id="bc7ea-110">ExitTask 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-110">ExitTask Method</span></span>](iclrtask-exittask-method.md)|<span data-ttu-id="bc7ea-111">현재 인스턴스와 연결 된 태스크가 종료 되 고 있음을 CLR에 알리고 `ICLRTask` 작업을 정상적으로 종료 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-111">Notifies the CLR that the task associated with the current `ICLRTask` instance is ending, and attempts to shut the task down gracefully.</span></span>|  
|[<span data-ttu-id="bc7ea-112">GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-112">GetMemStats Method</span></span>](iclrtask-getmemstats-method.md)|<span data-ttu-id="bc7ea-113">현재 인스턴스에서 나타내는 작업의 메모리 리소스 사용에 대 한 통계 정보를 가져옵니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-113">Gets statistical information on the use of memory resources by the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="bc7ea-114">LocksHeld 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-114">LocksHeld Method</span></span>](iclrtask-locksheld-method.md)|<span data-ttu-id="bc7ea-115">작업에 대해 현재 보유 하 고 있는 잠금 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-115">Gets the number of locks currently held on the task.</span></span>|  
|[<span data-ttu-id="bc7ea-116">NeedsPriorityScheduling 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-116">NeedsPriorityScheduling Method</span></span>](iclrtask-needspriorityscheduling-method.md)|<span data-ttu-id="bc7ea-117">현재 인스턴스가 나타내는 작업을 다시 예약 하기 위해 호스트에서 높은 우선 순위를 할당 해야 하는지 여부를 나타내는 값을 가져옵니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-117">Gets a value indicating whether the host should assign a high priority to rescheduling the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="bc7ea-118">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-118">Reset Method</span></span>](iclrtask-reset-method.md)|<span data-ttu-id="bc7ea-119">호스트가 작업을 완료 했음을 CLR에 알리고 CLR에서 현재 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-119">Informs the CLR that the host has completed a task, and enables the CLR to reuse the current `ICLRTask` instance to represent another task.</span></span>|  
|[<span data-ttu-id="bc7ea-120">RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-120">RudeAbort Method</span></span>](iclrtask-rudeabort-method.md)|<span data-ttu-id="bc7ea-121">`ICLRTask`종료 자가 실행 되는 것을 보장 하지 않고 CLR이 현재 인스턴스로 표시 된 작업을 즉시 중단 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-121">Causes the CLR to abort the task represented by the current `ICLRTask` instance immediately, without a guarantee that finalizers will be executed.</span></span>|  
|[<span data-ttu-id="bc7ea-122">SetTaskIdentifier 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-122">SetTaskIdentifier Method</span></span>](iclrtask-settaskidentifier-method.md)|<span data-ttu-id="bc7ea-123">디버깅에 사용 하기 위해 현재 인스턴스가 나타내는 작업의 고유 식별자를 설정 합니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-123">Sets a unique identifier for the task represented by the current `ICLRTask` instance, for use in debugging.</span></span>|  
|[<span data-ttu-id="bc7ea-124">SwitchIn 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-124">SwitchIn Method</span></span>](iclrtask-switchin-method.md)|<span data-ttu-id="bc7ea-125">현재 인스턴스가 나타내는 작업이 작동할 수 있는 상태임을 CLR에 알립니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-125">Notifies the CLR that the task represented by the current `ICLRTask` instance is in an operable state.</span></span>|  
|[<span data-ttu-id="bc7ea-126">SwitchOut 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-126">SwitchOut Method</span></span>](iclrtask-switchout-method.md)|<span data-ttu-id="bc7ea-127">현재 인스턴스가 나타내는 작업이 더 이상 작동 하지 않는 상태임을 CLR에 알립니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-127">Notifies the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>|  
|[<span data-ttu-id="bc7ea-128">YieldTask 메서드</span><span class="sxs-lookup"><span data-stu-id="bc7ea-128">YieldTask Method</span></span>](iclrtask-yieldtask-method.md)|<span data-ttu-id="bc7ea-129">CLR에서 프로세서 시간을 다른 작업에 사용할 수 있도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-129">Requests that the CLR make processor time available to other tasks.</span></span> <span data-ttu-id="bc7ea-130">CLR은 태스크가 처리 시간을 얻을 수 있는 상태로 전환 되는 것을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-130">The CLR makes no guarantee that the task will be put in a state where it can yield processing time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc7ea-131">설명</span><span class="sxs-lookup"><span data-stu-id="bc7ea-131">Remarks</span></span>  

 <span data-ttu-id="bc7ea-132">는 `ICLRTask` CLR의 작업 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-132">An `ICLRTask` is the representation of a task for the CLR.</span></span> <span data-ttu-id="bc7ea-133">코드를 실행 하는 동안 언제 든 지 실행 중이거나 실행 대기 중으로 작업을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-133">At any point during code execution, a task can be described either as running or waiting to run.</span></span> <span data-ttu-id="bc7ea-134">호스트는 메서드를 호출 `ICLRTask::SwitchIn` 하 여 현재 인스턴스를 나타내는 작업이 현재 작동 가능한 상태 임을 CLR에 알립니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-134">The host calls the `ICLRTask::SwitchIn` method to notify the CLR that the task that the current `ICLRTask` instance represents is now in an operable state.</span></span> <span data-ttu-id="bc7ea-135">를 호출한 후 `ICLRTask::SwitchIn` 호스트는 [IHostTaskManager:: beginthreadaffinity](ihosttaskmanager-beginthreadaffinity-method.md) 및 [IHostTaskManager:: endthreadaffinity](ihosttaskmanager-endthreadaffinity-method.md) 메서드 호출에 지정 된 대로 런타임에 스레드 선호도가 필요한 경우를 제외 하 고 모든 운영 체제 스레드에서 작업을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-135">After a call to `ICLRTask::SwitchIn`, the host can schedule the task on any operating system thread, except in cases where the runtime requires thread-affinity, as specified by calls to the [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md) and [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md) methods.</span></span> <span data-ttu-id="bc7ea-136">잠시 후 운영 체제에서 작업을 스레드에서 제거 하 고 실행 되지 않는 상태로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-136">Some time later, the operating system might decide to remove the task from the thread and place it in a non-running state.</span></span> <span data-ttu-id="bc7ea-137">예를 들어 작업이 동기화 기본 형식에서 차단 될 때마다 또는 i/o 작업이 완료 될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-137">For example, this might happen whenever the task blocks on synchronization primitives, or waits for I/O operations to complete.</span></span> <span data-ttu-id="bc7ea-138">호스트는 [Switchout](iclrtask-switchout-method.md) 을 호출 하 여 현재 인스턴스가 나타내는 작업이 더 이상 작동 하지 않는 상태임을 CLR에 알립니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-138">The host calls [SwitchOut](iclrtask-switchout-method.md) to notify the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>  
  
 <span data-ttu-id="bc7ea-139">일반적으로 작업은 코드 실행이 끝날 때 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-139">A task typically terminates at the end of code execution.</span></span> <span data-ttu-id="bc7ea-140">이때 호스트는를 호출 하 여 `ICLRTask::ExitTask` 연결 된를 제거 합니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="bc7ea-140">At that time, the host calls `ICLRTask::ExitTask` to destroy the associated `ICLRTask`.</span></span> <span data-ttu-id="bc7ea-141">그러나에 대 한 호출을 사용 하 여 작업을 재활용할 수도 있습니다 .이를 통해 `ICLRTask::Reset` `ICLRTask` 인스턴스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-141">However, tasks can also be recycled by using a call to `ICLRTask::Reset`, which allows the `ICLRTask` instance to be used again.</span></span> <span data-ttu-id="bc7ea-142">이 방법은 인스턴스를 반복적으로 만들고 삭제 하는 오버 헤드를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-142">This approach prevents the overhead of repeatedly creating and destroying instances.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc7ea-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc7ea-143">Requirements</span></span>  

 <span data-ttu-id="bc7ea-144">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc7ea-145">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bc7ea-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc7ea-146">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc7ea-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc7ea-147">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc7ea-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7ea-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc7ea-148">See also</span></span>

- [<span data-ttu-id="bc7ea-149">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-149">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bc7ea-150">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-150">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bc7ea-151">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="bc7ea-152">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-152">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="bc7ea-153">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc7ea-153">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
