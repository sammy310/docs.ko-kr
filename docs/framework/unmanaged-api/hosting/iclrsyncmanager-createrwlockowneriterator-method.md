---
title: ICLRSyncManager::CreateRWLockOwnerIterator 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b9c2fb2a4ddcc39c7690d832a94d772e8b82a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497082"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="3fc81-102">ICLRSyncManager::CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="3fc81-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="3fc81-103">CLR (공용 언어 런타임)에서 판독기-기록기 잠금을 대기 하는 태스크 집합을 결정 하는 데 호스트에 대 한 반복기를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc81-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fc81-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fc81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fc81-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="3fc81-106">[in] 원하는 판독기-기록기 잠금과 사용 하 여 연결 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="3fc81-107">[out] 에 전달 될 수 있는 반복기에 대 한 포인터를 [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) 하 고 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3fc81-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fc81-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fc81-108">Return Value</span></span>  
  
|<span data-ttu-id="3fc81-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fc81-109">HRESULT</span></span>|<span data-ttu-id="3fc81-110">설명</span><span class="sxs-lookup"><span data-stu-id="3fc81-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fc81-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fc81-111">S_OK</span></span>|<span data-ttu-id="3fc81-112">`CreateRWLockOwnerIterator` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="3fc81-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fc81-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fc81-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fc81-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fc81-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fc81-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-116">The call timed out.</span></span>|  
|<span data-ttu-id="3fc81-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fc81-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fc81-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fc81-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fc81-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fc81-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fc81-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fc81-121">E_FAIL</span></span>|<span data-ttu-id="3fc81-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fc81-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fc81-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3fc81-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="3fc81-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="3fc81-126">`CreateRWLockOwnerIterator` 관리 되는 코드를 현재 실행 중인 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fc81-127">설명</span><span class="sxs-lookup"><span data-stu-id="3fc81-127">Remarks</span></span>  
 <span data-ttu-id="3fc81-128">일반적으로 호스트를 호출 합니다 `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, 및 `GetRWLockOwnerNext` 교착 상태 감지 하는 동안 메서드.</span><span class="sxs-lookup"><span data-stu-id="3fc81-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="3fc81-129">호스트는 CLR에서는 판독기-기록기 잠금을 유지 하지 때문에 판독기 / 기록기 잠금이 여전히 유효한 지 확인 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="3fc81-130">몇 가지 전략 호스트를 잠금의 유효성을 확인 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="3fc81-131">호스트는 판독기 및 작성기 잠금 해제 호출이 차단할 수 있습니다 (예를 들어 [ihostsemaphore:: Releasesemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) 하면서이 블록 교착 상태가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="3fc81-132">호스트에 다시이 블록 교착 상태가 발생 하지 않습니다을 보장 판독기-기록기 잠금과 사용 하 여 연결 된 이벤트 개체에 대 한 대기 종료를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fc81-133">`CreateRWLockOwnerIterator` 스레드가 현재 실행 중인 관리 되지 않는 코드 에서만 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fc81-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc81-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fc81-134">Requirements</span></span>  
 <span data-ttu-id="3fc81-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fc81-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc81-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fc81-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fc81-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3fc81-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fc81-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc81-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc81-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fc81-139">See also</span></span>
- [<span data-ttu-id="3fc81-140">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc81-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3fc81-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fc81-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
