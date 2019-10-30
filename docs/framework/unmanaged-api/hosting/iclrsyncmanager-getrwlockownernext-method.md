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
ms.openlocfilehash: 860a818b08cb88b0fa17adccdfac5c81c0ec502c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130567"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="786fb-102">ICLRSyncManager::GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="786fb-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="786fb-103">현재 판독기-작성기 잠금에서 차단 된 다음 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="786fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="786fb-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="786fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="786fb-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="786fb-106">진행 [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)에 대 한 호출을 사용 하 여 만든 반복기입니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="786fb-107">제한이 잠금을 기다리는 다음 `IHostTask`에 대 한 포인터 이거나, 대기 중인 태스크가 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="786fb-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="786fb-108">Return Value</span></span>  
  
|<span data-ttu-id="786fb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="786fb-109">HRESULT</span></span>|<span data-ttu-id="786fb-110">설명</span><span class="sxs-lookup"><span data-stu-id="786fb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="786fb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="786fb-111">S_OK</span></span>|<span data-ttu-id="786fb-112">`GetRWLockOwnerNext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="786fb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="786fb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="786fb-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="786fb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="786fb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="786fb-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-116">The call timed out.</span></span>|  
|<span data-ttu-id="786fb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="786fb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="786fb-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="786fb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="786fb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="786fb-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="786fb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="786fb-121">E_FAIL</span></span>|<span data-ttu-id="786fb-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="786fb-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="786fb-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="786fb-125">주의</span><span class="sxs-lookup"><span data-stu-id="786fb-125">Remarks</span></span>  
 <span data-ttu-id="786fb-126">`ppOwnerHostTask` null로 설정 된 경우 반복이 종료 되 고 호스트에서 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="786fb-127">CLR은 `ppOwnerHostTask` 가리키는 `IHostTask`에 대 한 `AddRef`를 호출 하 여 호스트가 포인터를 보유 하는 동안이 작업을 종료 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="786fb-128">완료 되 면 호스트는 참조 횟수를 감소 하기 위해 `Release`를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="786fb-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="786fb-129">Requirements</span></span>  
 <span data-ttu-id="786fb-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="786fb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="786fb-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="786fb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="786fb-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="786fb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="786fb-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="786fb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786fb-134">참조</span><span class="sxs-lookup"><span data-stu-id="786fb-134">See also</span></span>

- [<span data-ttu-id="786fb-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="786fb-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="786fb-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="786fb-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
