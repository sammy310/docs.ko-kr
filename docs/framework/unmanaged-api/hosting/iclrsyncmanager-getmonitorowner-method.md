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
ms.openlocfilehash: 77debe047f5b379237022f44ef8f9d96718b227d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762502"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="09968-102">ICLRSyncManager::GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="09968-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="09968-103">지정 된 쿠키로 식별 되는 모니터를 소유 하는 [IHostTask](ihosttask-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09968-103">Gets the [IHostTask](ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09968-104">구문</span><span class="sxs-lookup"><span data-stu-id="09968-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09968-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09968-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="09968-106">진행 모니터와 연결 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="09968-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="09968-107">제한이 현재 모니터를 소유 하 고 있는에 대 한 포인터 `IHostTask` 이거나, 소유 하는 작업이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="09968-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09968-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="09968-108">Return Value</span></span>  
  
|<span data-ttu-id="09968-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09968-109">HRESULT</span></span>|<span data-ttu-id="09968-110">Description</span><span class="sxs-lookup"><span data-stu-id="09968-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09968-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="09968-111">S_OK</span></span>|<span data-ttu-id="09968-112">`GetMonitorOwner`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="09968-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09968-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09968-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09968-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09968-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09968-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-116">The call timed out.</span></span>|  
|<span data-ttu-id="09968-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09968-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09968-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09968-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09968-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09968-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09968-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09968-121">E_FAIL</span></span>|<span data-ttu-id="09968-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09968-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09968-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09968-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09968-125">설명</span><span class="sxs-lookup"><span data-stu-id="09968-125">Remarks</span></span>  
 <span data-ttu-id="09968-126">호스트는 일반적으로 `GetMonitorOwner` 교착 상태 검색 메커니즘의 일부로를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="09968-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="09968-127">쿠키는 [IHostSyncManager:: CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md)에 대 한 호출을 사용 하 여 생성 될 때 모니터와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09968-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09968-128">모니터의 기반이 되는 이벤트를 해제 하는 호출은이 메서드에 대 한 호출이 현재 해당 모니터와 연결 된 쿠키에 적용 되는 경우에는 교착 상태를 차단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="09968-129">다른 작업은이 모니터를 얻으려고 시도 하는 경우에도 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="09968-130">`GetMonitorOwner`는 항상 즉시 반환 되며를 호출한 후 언제 든 지 호출할 수 있습니다 `CreateMonitorEvent` .</span><span class="sxs-lookup"><span data-stu-id="09968-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="09968-131">호스트는 태스크가 이벤트를 기다릴 때까지 기다릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09968-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09968-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09968-132">Requirements</span></span>  
 <span data-ttu-id="09968-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09968-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09968-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09968-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09968-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09968-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09968-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09968-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09968-137">참조</span><span class="sxs-lookup"><span data-stu-id="09968-137">See also</span></span>

- [<span data-ttu-id="09968-138">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09968-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="09968-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09968-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
