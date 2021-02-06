---
description: '다음에 대 한 자세한 정보: ICLRTask:: Reset 메서드'
title: ICLRTask::Reset 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: d30738b98003e0543c1a2a31c7471b15811efe5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636990"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="39b6d-103">ICLRTask::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="39b6d-103">ICLRTask::Reset Method</span></span>

<span data-ttu-id="39b6d-104">호스트가 작업을 완료 했음을 CLR (공용 언어 런타임)에 알리고 CLR에서 현재 [ICLRTask](iclrtask-interface.md) 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-104">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b6d-105">구문</span><span class="sxs-lookup"><span data-stu-id="39b6d-105">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b6d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39b6d-106">Parameters</span></span>  

 `fFull`  
 <span data-ttu-id="39b6d-107">[in] `true` 런타임에 현재 인스턴스와 관련 된 보안 및 로캘 정보와 함께 모든 스레드 관련 정적 값을 다시 설정 해야 하면 `ICLRTask` 이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-107">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="39b6d-108">값이 이면 `true` 런타임은 또는를 사용 하 여 저장 된 데이터를 다시 설정 합니다 <xref:System.Threading.Thread.AllocateDataSlot%2A> <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="39b6d-108">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39b6d-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="39b6d-109">Return Value</span></span>  
  
|<span data-ttu-id="39b6d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39b6d-110">HRESULT</span></span>|<span data-ttu-id="39b6d-111">설명</span><span class="sxs-lookup"><span data-stu-id="39b6d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39b6d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="39b6d-112">S_OK</span></span>|<span data-ttu-id="39b6d-113">`Reset` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-113">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="39b6d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39b6d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39b6d-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="39b6d-116">성공할</span><span class="sxs-lookup"><span data-stu-id="39b6d-116">successfully</span></span>|  
|<span data-ttu-id="39b6d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39b6d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39b6d-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-118">The call timed out.</span></span>|  
|<span data-ttu-id="39b6d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39b6d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39b6d-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39b6d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39b6d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39b6d-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39b6d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39b6d-123">E_FAIL</span></span>|<span data-ttu-id="39b6d-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39b6d-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39b6d-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b6d-127">설명</span><span class="sxs-lookup"><span data-stu-id="39b6d-127">Remarks</span></span>  

 <span data-ttu-id="39b6d-128">CLR은 이전에 만든 `ICLRTask` 인스턴스를 재활용 하 여 새 작업을 필요할 때마다 반복 해 서 새 인스턴스를 만들 때의 오버 헤드를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-128">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="39b6d-129">호스트에서는 `ICLRTask::Reset` 작업을 완료 했을 때 [ICLRTask:: exittask](iclrtask-exittask-method.md) 대신를 호출 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-129">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="39b6d-130">다음 목록에서는 인스턴스의 일반적인 수명 주기를 요약 합니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-130">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="39b6d-131">런타임이 새 인스턴스를 만듭니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-131">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="39b6d-132">런타임은 [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) 를 호출 하 여 현재 호스트 태스크에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-132">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="39b6d-133">런타임은 [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) 를 호출 하 여 새 인스턴스를 호스트 태스크에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-133">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="39b6d-134">태스크가 실행 되 고 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-134">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="39b6d-135">호스트는를 호출 하 여 작업을 소멸 시킵니다 `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-135">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="39b6d-136">`Reset` 에서는 두 가지 방법으로이 시나리오를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-136">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="39b6d-137">위의 5 단계에서 호스트는를 호출 `Reset` 하 여 작업을 정리 상태로 다시 설정 하 고 `ICLRTask` 해당 인스턴스를 연결 된 [IHostTask](ihosttask-interface.md) 인스턴스에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-137">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="39b6d-138">원하는 경우 호스트는 다시 사용할 인스턴스를 캐시할 수도 있습니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-138">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="39b6d-139">위의 1 단계에서 런타임은 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서 재활용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-139">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="39b6d-140">이 방법은 호스트에 재사용 가능한 작업자 태스크의 풀도 있는 경우에 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-140">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="39b6d-141">호스트는 인스턴스 중 하나를 소멸 시키는 경우를 `IHostTask` 호출 하 여 해당 하는를 소멸 시킵니다 `ICLRTask` `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-141">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b6d-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39b6d-142">Requirements</span></span>  

 <span data-ttu-id="39b6d-143">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39b6d-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39b6d-144">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39b6d-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39b6d-145">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b6d-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39b6d-146">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b6d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b6d-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39b6d-147">See also</span></span>

- [<span data-ttu-id="39b6d-148">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39b6d-148">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="39b6d-149">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39b6d-149">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="39b6d-150">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39b6d-150">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="39b6d-151">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39b6d-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
