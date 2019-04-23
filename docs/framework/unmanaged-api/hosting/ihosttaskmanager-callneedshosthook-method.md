---
title: IHostTaskManager::CallNeedsHostHook 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adc270be51988cba78c6e522b16b480baef725c4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139232"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="6ab88-102">IHostTaskManager::CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="6ab88-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="6ab88-103">호스트를에서 CLR (공용 언어 런타임) 관리 되지 않는 함수에 지정된 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ab88-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ab88-104">Syntax</span></span>  
  
```  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,   
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ab88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ab88-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="6ab88-106">[in] 관리 되지 않는 함수를 호출 하는 매핑된 pe (이식 가능) 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="6ab88-107">[out] 호스트 연결에 대 한 호출을 해야 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ab88-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6ab88-108">Return Value</span></span>  
  
|<span data-ttu-id="6ab88-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ab88-109">HRESULT</span></span>|<span data-ttu-id="6ab88-110">설명</span><span class="sxs-lookup"><span data-stu-id="6ab88-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ab88-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ab88-111">S_OK</span></span>|<span data-ttu-id="6ab88-112">`CallNeedsHostHook` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="6ab88-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ab88-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ab88-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ab88-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ab88-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ab88-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-116">The call timed out.</span></span>|  
|<span data-ttu-id="6ab88-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ab88-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ab88-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ab88-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ab88-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ab88-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ab88-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ab88-121">E_FAIL</span></span>|<span data-ttu-id="6ab88-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="6ab88-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ab88-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ab88-125">설명</span><span class="sxs-lookup"><span data-stu-id="6ab88-125">Remarks</span></span>  
 <span data-ttu-id="6ab88-126">CLR 코드 실행을 최적화할 수 있도록, 각 플랫폼의 분석을 수행 된 호출을 인라인 수 있는지 여부를 확인 하려면 컴파일하는 동안 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="6ab88-127">`CallNeedsHostHook` 호스트를를 관리 되지 않는 함수에 대 한 호출 후크 해야 하도록 요구 하 여 해당 결정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="6ab88-128">호스트를 후크에 필요한 런타임 호출 인라인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="6ab88-129">호스트 일반적으로 필요 후크를 부동 소수점 상태를 조정 해야 하는 경우 호출 상태 호스트 메모리 또는 모든 잠금에 대 한 런타임 요청을 추적할 수 없는 위치를 입력 하는 알림을 수신 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="6ab88-130">호스트 호출 후크 해야 필요한 경우에 대 한 호출을 사용 하 여 런타임에서 관리 코드에서 전환 호스트에 알립니다 [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)하십시오 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), 및 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab88-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ab88-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ab88-131">Requirements</span></span>  
 <span data-ttu-id="6ab88-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ab88-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ab88-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ab88-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ab88-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6ab88-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ab88-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ab88-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab88-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ab88-136">See also</span></span>

- [<span data-ttu-id="6ab88-137">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ab88-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6ab88-138">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ab88-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6ab88-139">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ab88-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6ab88-140">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ab88-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
