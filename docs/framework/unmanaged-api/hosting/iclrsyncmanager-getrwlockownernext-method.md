---
title: ICLRSyncManager::GetRWLockOwnerNext 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb91a49086eae4d9e8d43a2d38b51d9dd0a6814e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473733"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="a526a-102">ICLRSyncManager::GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="a526a-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="a526a-103">다음을 가져옵니다 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 현재 판독기-기록기 잠금을 차단 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a526a-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a526a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a526a-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a526a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a526a-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="a526a-106">[in] 에 대 한 호출을 사용 하 여 생성 된 반복기 [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="a526a-107">[out] 다음에 대 한 포인터 `IHostTask` 잠금 또는 null에 대기 중인 작업이 대기 중인 경우.</span><span class="sxs-lookup"><span data-stu-id="a526a-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a526a-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a526a-108">Return Value</span></span>  
  
|<span data-ttu-id="a526a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a526a-109">HRESULT</span></span>|<span data-ttu-id="a526a-110">설명</span><span class="sxs-lookup"><span data-stu-id="a526a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a526a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a526a-111">S_OK</span></span>|<span data-ttu-id="a526a-112">`GetRWLockOwnerNext` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="a526a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a526a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a526a-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a526a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a526a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a526a-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-116">The call timed out.</span></span>|  
|<span data-ttu-id="a526a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a526a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a526a-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a526a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a526a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a526a-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a526a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a526a-121">E_FAIL</span></span>|<span data-ttu-id="a526a-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a526a-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a526a-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a526a-125">설명</span><span class="sxs-lookup"><span data-stu-id="a526a-125">Remarks</span></span>  
 <span data-ttu-id="a526a-126">하는 경우 `ppOwnerHostTask` 로 설정 되어 null 인 반복 종료 및 호스트를 호출 해야 합니다 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a526a-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a526a-127">CLR 호출 `AddRef` 에 `IHostTask` 하려는 `ppOwnerHostTask` 호스트 포인터를 보유 하는 동안 종료에서이 작업을 방지 하는 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="a526a-128">호스트를 호출 해야 `Release` 완료 되 면 참조 횟수를 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a526a-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a526a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a526a-129">Requirements</span></span>  
 <span data-ttu-id="a526a-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a526a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a526a-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a526a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a526a-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a526a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a526a-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a526a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a526a-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="a526a-134">See also</span></span>
- [<span data-ttu-id="a526a-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a526a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a526a-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a526a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
