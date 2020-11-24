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
ms.openlocfilehash: 2b6a2082d27fca4c78dcb15a13cfd87e8066e388
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687218"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="8bd18-102">ICLRSyncManager::CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="8bd18-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>

<span data-ttu-id="8bd18-103">CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd18-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bd18-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bd18-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bd18-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="8bd18-106">진행 원하는 판독기-작성기 잠금과 연결 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="8bd18-107">제한이 [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) 및 [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드에 전달할 수 있는 반복기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bd18-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="8bd18-108">Return Value</span></span>  
  
|<span data-ttu-id="8bd18-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bd18-109">HRESULT</span></span>|<span data-ttu-id="8bd18-110">설명</span><span class="sxs-lookup"><span data-stu-id="8bd18-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bd18-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bd18-111">S_OK</span></span>|<span data-ttu-id="8bd18-112">`CreateRWLockOwnerIterator` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="8bd18-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8bd18-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8bd18-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8bd18-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8bd18-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8bd18-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-116">The call timed out.</span></span>|  
|<span data-ttu-id="8bd18-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8bd18-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8bd18-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8bd18-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8bd18-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8bd18-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8bd18-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8bd18-121">E_FAIL</span></span>|<span data-ttu-id="8bd18-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8bd18-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8bd18-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8bd18-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8bd18-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8bd18-126">`CreateRWLockOwnerIterator` 현재 관리 코드를 실행 하 고 있는 스레드에서를 호출 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bd18-127">설명</span><span class="sxs-lookup"><span data-stu-id="8bd18-127">Remarks</span></span>  

 <span data-ttu-id="8bd18-128">호스트는 일반적으로 `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` 교착 상태를 검색 하는 동안, 및 메서드를 호출 합니다 `GetRWLockOwnerNext` .</span><span class="sxs-lookup"><span data-stu-id="8bd18-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="8bd18-129">이 경우에는 CLR에서 판독기-작성기 잠금을 활성 상태로 유지할 필요가 없기 때문에 호스트에서 판독기-작성기 잠금이 여전히 유효한 지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="8bd18-130">호스트에서 잠금의 유효성을 확인 하는 데 사용할 수 있는 몇 가지 전략이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="8bd18-131">이 블록이 교착 상태를 발생 시 키 지 않도록 하는 동시에 호스트는 판독기-작성기 잠금 (예 [: IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md))에서 릴리스 호출을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="8bd18-132">호스트는 판독기-작성기 잠금과 연결 된 이벤트 개체를 대기 하는 것을 차단 하 여이 블록이 교착 상태를 발생 시 키 지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8bd18-133">`CreateRWLockOwnerIterator` 는 현재 비관리 코드를 실행 하는 스레드에서만 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd18-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bd18-134">Requirements</span></span>  

 <span data-ttu-id="8bd18-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bd18-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd18-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8bd18-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bd18-137">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd18-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bd18-138">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd18-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd18-139">참조</span><span class="sxs-lookup"><span data-stu-id="8bd18-139">See also</span></span>

- [<span data-ttu-id="8bd18-140">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bd18-140">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8bd18-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bd18-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
