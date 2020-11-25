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
ms.openlocfilehash: b87bc026a2cac2d0b913128c43142d56aee03025
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725198"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="cc8c2-102">ICLRTask::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="cc8c2-102">ICLRTask::Reset Method</span></span>

<span data-ttu-id="cc8c2-103">호스트가 작업을 완료 했음을 CLR (공용 언어 런타임)에 알리고 CLR에서 현재 [ICLRTask](iclrtask-interface.md) 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc8c2-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc8c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc8c2-105">Parameters</span></span>  

 `fFull`  
 <span data-ttu-id="cc8c2-106">[in] `true` 런타임에 현재 인스턴스와 관련 된 보안 및 로캘 정보와 함께 모든 스레드 관련 정적 값을 다시 설정 해야 하면 `ICLRTask` 이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="cc8c2-107">값이 이면 `true` 런타임은 또는를 사용 하 여 저장 된 데이터를 다시 설정 합니다 <xref:System.Threading.Thread.AllocateDataSlot%2A> <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc8c2-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="cc8c2-108">Return Value</span></span>  
  
|<span data-ttu-id="cc8c2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc8c2-109">HRESULT</span></span>|<span data-ttu-id="cc8c2-110">설명</span><span class="sxs-lookup"><span data-stu-id="cc8c2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc8c2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc8c2-111">S_OK</span></span>|<span data-ttu-id="cc8c2-112">`Reset` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="cc8c2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc8c2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc8c2-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="cc8c2-115">성공할</span><span class="sxs-lookup"><span data-stu-id="cc8c2-115">successfully</span></span>|  
|<span data-ttu-id="cc8c2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc8c2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc8c2-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-117">The call timed out.</span></span>|  
|<span data-ttu-id="cc8c2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc8c2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc8c2-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc8c2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc8c2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc8c2-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc8c2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc8c2-122">E_FAIL</span></span>|<span data-ttu-id="cc8c2-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc8c2-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc8c2-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc8c2-126">설명</span><span class="sxs-lookup"><span data-stu-id="cc8c2-126">Remarks</span></span>  

 <span data-ttu-id="cc8c2-127">CLR은 이전에 만든 `ICLRTask` 인스턴스를 재활용 하 여 새 작업을 필요할 때마다 반복 해 서 새 인스턴스를 만들 때의 오버 헤드를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="cc8c2-128">호스트에서는 `ICLRTask::Reset` 작업을 완료 했을 때 [ICLRTask:: exittask](iclrtask-exittask-method.md) 대신를 호출 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="cc8c2-129">다음 목록에서는 인스턴스의 일반적인 수명 주기를 요약 합니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="cc8c2-130">런타임이 새 인스턴스를 만듭니다 `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="cc8c2-131">런타임은 [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) 를 호출 하 여 현재 호스트 태스크에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-131">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="cc8c2-132">런타임은 [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) 를 호출 하 여 새 인스턴스를 호스트 태스크에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-132">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="cc8c2-133">태스크가 실행 되 고 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="cc8c2-134">호스트는를 호출 하 여 작업을 소멸 시킵니다 `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="cc8c2-135">`Reset` 에서는 두 가지 방법으로이 시나리오를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="cc8c2-136">위의 5 단계에서 호스트는를 호출 `Reset` 하 여 작업을 정리 상태로 다시 설정 하 고 `ICLRTask` 해당 인스턴스를 연결 된 [IHostTask](ihosttask-interface.md) 인스턴스에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="cc8c2-137">원하는 경우 호스트는 다시 사용할 인스턴스를 캐시할 수도 있습니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="cc8c2-138">위의 1 단계에서 런타임은 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서 재활용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="cc8c2-139">이 방법은 호스트에 재사용 가능한 작업자 태스크의 풀도 있는 경우에 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="cc8c2-140">호스트는 인스턴스 중 하나를 소멸 시키는 경우를 `IHostTask` 호출 하 여 해당 하는를 소멸 시킵니다 `ICLRTask` `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="cc8c2-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc8c2-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc8c2-141">Requirements</span></span>  

 <span data-ttu-id="cc8c2-142">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8c2-143">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cc8c2-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc8c2-144">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc8c2-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc8c2-145">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8c2-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8c2-146">참조</span><span class="sxs-lookup"><span data-stu-id="cc8c2-146">See also</span></span>

- [<span data-ttu-id="cc8c2-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc8c2-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cc8c2-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc8c2-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cc8c2-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc8c2-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="cc8c2-150">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc8c2-150">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
