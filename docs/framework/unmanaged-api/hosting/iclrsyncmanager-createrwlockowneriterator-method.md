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
ms.openlocfilehash: 64179e132cfaffbb1fcdc2cd0a47bbcc11be2ff0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943268"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="4a025-102">ICLRSyncManager::CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="4a025-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="4a025-103">CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a025-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a025-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a025-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a025-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="4a025-106">진행 원하는 판독기-작성기 잠금과 연결 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="4a025-107">제한이 [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) 및 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드에 전달할 수 있는 반복기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a025-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4a025-108">Return Value</span></span>  
  
|<span data-ttu-id="4a025-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a025-109">HRESULT</span></span>|<span data-ttu-id="4a025-110">Description</span><span class="sxs-lookup"><span data-stu-id="4a025-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a025-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a025-111">S_OK</span></span>|<span data-ttu-id="4a025-112">`CreateRWLockOwnerIterator`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="4a025-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a025-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a025-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a025-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a025-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a025-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a025-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a025-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a025-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a025-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a025-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a025-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a025-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a025-121">E_FAIL</span></span>|<span data-ttu-id="4a025-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a025-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a025-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a025-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="4a025-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="4a025-126">`CreateRWLockOwnerIterator`현재 관리 코드를 실행 하 고 있는 스레드에서를 호출 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a025-127">설명</span><span class="sxs-lookup"><span data-stu-id="4a025-127">Remarks</span></span>  
 <span data-ttu-id="4a025-128">호스트는 일반적으로 `CreateRWLockOwnerIterator`교착 `DeleteRWLockOwnerIterator`상태를 `GetRWLockOwnerNext` 검색 하는 동안, 및 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="4a025-129">이 경우에는 CLR에서 판독기-작성기 잠금을 활성 상태로 유지할 필요가 없기 때문에 호스트에서 판독기-작성기 잠금이 여전히 유효한 지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="4a025-130">호스트에서 잠금의 유효성을 확인 하는 데 사용할 수 있는 몇 가지 전략이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="4a025-131">이 블록이 교착 상태를 발생 시 키 지 않도록 하는 동시에 호스트는 판독기-작성기 잠금 (예 [: IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md))에서 릴리스 호출을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="4a025-132">호스트는 판독기-작성기 잠금과 연결 된 이벤트 개체를 대기 하는 것을 차단 하 여이 블록이 교착 상태를 발생 시 키 지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a025-133">`CreateRWLockOwnerIterator`는 현재 비관리 코드를 실행 하는 스레드에서만 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a025-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a025-134">Requirements</span></span>  
 <span data-ttu-id="4a025-135">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a025-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a025-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a025-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a025-137">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a025-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a025-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a025-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a025-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a025-139">See also</span></span>

- [<span data-ttu-id="4a025-140">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a025-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4a025-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a025-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
