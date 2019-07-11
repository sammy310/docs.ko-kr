---
title: ICLRSyncManager::GetMonitorOwner 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1c986de068cd79ae3662c82ed24906d42bf2780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759043"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="11a59-102">ICLRSyncManager::GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="11a59-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="11a59-103">가져옵니다 합니다 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 지정한 쿠키로 식별 되는 모니터를 소유 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="11a59-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a59-104">구문</span><span class="sxs-lookup"><span data-stu-id="11a59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a59-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11a59-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="11a59-106">[in] 모니터와 관련 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="11a59-107">[out] 에 대 한 포인터를 `IHostTask` 현재 소유 하는 모니터 또는 null 소유권이 없는 작업 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="11a59-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a59-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="11a59-108">Return Value</span></span>  
  
|<span data-ttu-id="11a59-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11a59-109">HRESULT</span></span>|<span data-ttu-id="11a59-110">설명</span><span class="sxs-lookup"><span data-stu-id="11a59-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11a59-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="11a59-111">S_OK</span></span>|<span data-ttu-id="11a59-112">`GetMonitorOwner` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="11a59-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11a59-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11a59-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11a59-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11a59-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11a59-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-116">The call timed out.</span></span>|  
|<span data-ttu-id="11a59-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11a59-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11a59-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11a59-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11a59-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11a59-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11a59-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11a59-121">E_FAIL</span></span>|<span data-ttu-id="11a59-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11a59-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11a59-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11a59-125">설명</span><span class="sxs-lookup"><span data-stu-id="11a59-125">Remarks</span></span>  
 <span data-ttu-id="11a59-126">호스트는 일반적으로 호출 `GetMonitorOwner` 교착 상태 감지 메커니즘의 일부분으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="11a59-127">쿠키와 관련이 모니터에 대 한 호출을 사용 하 여 만들어지면 [ihostsyncmanager:: Createmonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11a59-128">모니터를 내부 이벤트를 해제 하는 호출 되지 않을-교착 상태가 되지 않고-이 메서드에 대 한 호출에서 실행 되는 모니터와 관련 된 쿠키에 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="11a59-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="11a59-129">이 모니터를 획득 하려고 할 경우에 다른 작업 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="11a59-130">`GetMonitorOwner` 항상 즉시 반환 하 고 호출 후 언제 든 지 호출할 수 있습니다 `CreateMonitorEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="11a59-131">호스트는 태스크가 대기 하는 이벤트에 대 한 때까지 대기 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a59-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a59-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11a59-132">Requirements</span></span>  
 <span data-ttu-id="11a59-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="11a59-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a59-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11a59-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11a59-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="11a59-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11a59-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a59-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a59-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="11a59-137">See also</span></span>

- [<span data-ttu-id="11a59-138">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11a59-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="11a59-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11a59-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
