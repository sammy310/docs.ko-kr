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
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176294"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="18860-102">IHostTaskManager::CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="18860-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="18860-103">호스트가 공통 언어 런타임(CLR)이 지정된 호출을 관리되지 않는 함수에 인라인할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18860-104">구문</span><span class="sxs-lookup"><span data-stu-id="18860-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18860-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18860-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="18860-106">【인】 호출할 관리되지 않는 함수의 매핑된 이식형 실행 파일(PE) 내의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="18860-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="18860-107">【아웃】 호스트에 연결해야 하는 호출을 사용할지 여부를 나타내는 부울 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18860-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18860-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="18860-108">Return Value</span></span>  
  
|<span data-ttu-id="18860-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18860-109">HRESULT</span></span>|<span data-ttu-id="18860-110">Description</span><span class="sxs-lookup"><span data-stu-id="18860-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18860-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="18860-111">S_OK</span></span>|<span data-ttu-id="18860-112">`CallNeedsHostHook`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="18860-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="18860-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="18860-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18860-114">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="18860-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18860-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18860-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18860-116">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-116">The call timed out.</span></span>|  
|<span data-ttu-id="18860-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18860-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18860-118">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18860-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18860-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18860-120">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18860-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18860-121">E_FAIL</span></span>|<span data-ttu-id="18860-122">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="18860-123">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18860-124">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18860-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18860-125">설명</span><span class="sxs-lookup"><span data-stu-id="18860-125">Remarks</span></span>  
 <span data-ttu-id="18860-126">코드 실행을 최적화하기 위해 CLR은 컴파일 중에 호출을 호출하는 각 플랫폼에 대한 분석을 수행하여 호출을 인라인할 수 있는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="18860-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="18860-127">`CallNeedsHostHook`호스트가 관리되지 않는 함수에 대한 호출을 연결하도록 요구하여 해당 결정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="18860-128">호스트에 후크가 필요한 경우 런타임이 호출에 인라인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18860-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="18860-129">호스트는 일반적으로 부동 지점 상태를 조정해야 하는 후크가 필요하거나 호출이 런타임의 메모리 요청 또는 잠금 을 추적할 수 없는 상태가 된다는 알림을 받을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="18860-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="18860-130">호스트가 호출을 연결해야 하는 경우 런타임은 [EnterRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) [LeaveRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)및 [ReverseLeaveRunTime에](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)대한 호출을 사용하여 관리 코드로 전환 호스트를 통보합니다.</span><span class="sxs-lookup"><span data-stu-id="18860-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18860-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18860-131">Requirements</span></span>  
 <span data-ttu-id="18860-132">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18860-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18860-133">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="18860-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18860-134">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="18860-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18860-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18860-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18860-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18860-136">See also</span></span>

- [<span data-ttu-id="18860-137">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18860-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="18860-138">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18860-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="18860-139">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18860-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="18860-140">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18860-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
