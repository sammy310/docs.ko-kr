---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3039855a58e6db6a403ab33c226b4b8b390668f7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758598"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="d0b60-102">ICLRTask::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="d0b60-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="d0b60-103">호스트 작업을 완료 하 고 현재 다시 사용 하려면 CLR을 사용 하도록 설정 된 CLR (공용 언어 런타임)에 게 알립니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 다른 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b60-104">구문</span><span class="sxs-lookup"><span data-stu-id="d0b60-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0b60-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="d0b60-106">[in] `true`런타임은 현재와 관련 된 보안 및 로캘 정보 외에도 모든 스레드 관련 정적 값을 다시 설정 해야 하는 경우 `ICLRTask` 인스턴스이면이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d0b60-107">값이 `true`, 런타임에서 사용 하 여 저장 된 데이터를 다시 설정 <xref:System.Threading.Thread.AllocateDataSlot%2A> 또는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0b60-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d0b60-108">Return Value</span></span>  
  
|<span data-ttu-id="d0b60-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0b60-109">HRESULT</span></span>|<span data-ttu-id="d0b60-110">Description</span><span class="sxs-lookup"><span data-stu-id="d0b60-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0b60-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0b60-111">S_OK</span></span>|<span data-ttu-id="d0b60-112">`Reset` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d0b60-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0b60-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0b60-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d0b60-115">successfully</span><span class="sxs-lookup"><span data-stu-id="d0b60-115">successfully</span></span>|  
|<span data-ttu-id="d0b60-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0b60-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0b60-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-117">The call timed out.</span></span>|  
|<span data-ttu-id="d0b60-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0b60-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0b60-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0b60-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0b60-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0b60-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0b60-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0b60-122">E_FAIL</span></span>|<span data-ttu-id="d0b60-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0b60-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0b60-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0b60-126">설명</span><span class="sxs-lookup"><span data-stu-id="d0b60-126">Remarks</span></span>  
 <span data-ttu-id="d0b60-127">이전에 만든 CLR 재활용할 수 `ICLRTask` 인스턴스를 반복적으로 새로 고침 작업이 필요할 때마다 새 인스턴스를 만드는 오버 헤드를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="d0b60-128">호스트를 호출 하 여이 기능을 활성화 `ICLRTask::Reset` of [iclrtask:: Exittask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) 때 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="d0b60-129">다음은 요약의 일반적인 수명 주기는 `ICLRTask` 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="d0b60-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="d0b60-130">런타임에서 새로 만들고 `ICLRTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d0b60-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="d0b60-131">런타임 호출 [ihosttaskmanager:: Getcurrenttask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) 현재 호스트 작업에 대 한 참조를 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="d0b60-132">런타임 호출 [ihosttask:: Setclrtask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) 호스트 작업을 사용 하 여 새 인스턴스를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="d0b60-133">태스크를 실행 하 고 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="d0b60-134">호스트를 호출 하 여 작업을 소멸 시킵니다 `ICLRTask::ExitTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="d0b60-135">`Reset` 두 가지 방법으로이 시나리오를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="d0b60-136">호스트를 호출 하 여 위의 5 단계에서 `Reset` 정리 된 상태로 작업을 다시 설정 하려면 다음을 `ICLRTask` 연결 된 인스턴스 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d0b60-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="d0b60-137">원하는 경우 호스트 캐시할 수도 있습니다는 `IHostTask` 인스턴스 다시 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="d0b60-138">위의 1 단계에서 공용 언어 런타임은 가져옵니다 재활용 된 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서.</span><span class="sxs-lookup"><span data-stu-id="d0b60-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="d0b60-139">이 방법은 호스트 역시 다시 사용할 수 있는 작업자 태스크의 풀 하는 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="d0b60-140">호스트 중 하나을 제거 하면 해당 `IHostTask` 인스턴스를 해당 소멸 시킵니다 `ICLRTask` 호출 하 여 `ExitTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b60-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b60-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0b60-141">Requirements</span></span>  
 <span data-ttu-id="d0b60-142">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0b60-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b60-143">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0b60-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0b60-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d0b60-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0b60-145">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b60-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b60-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0b60-146">See also</span></span>

- [<span data-ttu-id="d0b60-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b60-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d0b60-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b60-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d0b60-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b60-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d0b60-150">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0b60-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
