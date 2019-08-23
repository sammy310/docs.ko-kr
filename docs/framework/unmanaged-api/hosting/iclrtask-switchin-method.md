---
title: ICLRTask::SwitchIn 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938367"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="dac61-102">ICLRTask::SwitchIn 메서드</span><span class="sxs-lookup"><span data-stu-id="dac61-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="dac61-103">현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 작업이 현재 작동 가능한 상태 임을 CLR (공용 언어 런타임)에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac61-104">구문</span><span class="sxs-lookup"><span data-stu-id="dac61-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dac61-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dac61-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="dac61-106">진행 현재 `ICLRTask` 인스턴스가 나타내는 작업이 실행 중인 실제 스레드에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dac61-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="dac61-107">Return Value</span></span>  
  
|<span data-ttu-id="dac61-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dac61-108">HRESULT</span></span>|<span data-ttu-id="dac61-109">Description</span><span class="sxs-lookup"><span data-stu-id="dac61-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dac61-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dac61-110">S_OK</span></span>|<span data-ttu-id="dac61-111">`SwitchIn`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="dac61-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dac61-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dac61-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dac61-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dac61-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dac61-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-115">The call timed out.</span></span>|  
|<span data-ttu-id="dac61-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dac61-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dac61-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dac61-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dac61-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dac61-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dac61-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dac61-120">E_FAIL</span></span>|<span data-ttu-id="dac61-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dac61-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dac61-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dac61-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="dac61-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="dac61-125">`SwitchIn`는 [Switchout 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)를 이전에 호출 하지 않고 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dac61-126">설명</span><span class="sxs-lookup"><span data-stu-id="dac61-126">Remarks</span></span>  
 <span data-ttu-id="dac61-127">매개 `threadHandle` 변수는 현재 `ICLRTask` 인스턴스가 나타내는 작업이 예약 된 운영 체제 스레드에 대 한 핸들을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="dac61-128">이 스레드에서 가장이 발생 한 경우 작업에서 전환 하기 전에 [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) 를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dac61-129">에 대 `SwitchIn` `SwitchOut` 한 이전 호출 없이에 대 한 호출은 HRESULT 값 HOST_E_INVALIDOPERATION을 사용 하 여 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac61-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dac61-130">Requirements</span></span>  
 <span data-ttu-id="dac61-131">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dac61-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dac61-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dac61-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dac61-133">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dac61-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dac61-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dac61-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac61-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="dac61-135">See also</span></span>

- [<span data-ttu-id="dac61-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac61-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dac61-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac61-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dac61-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac61-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dac61-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dac61-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
