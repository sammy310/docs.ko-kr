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
ms.openlocfilehash: 93a8b3884d831b7da412b6c53dd599af216cbbf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728318"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="27df7-102">ICLRSyncManager::GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="27df7-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>

<span data-ttu-id="27df7-103">현재 판독기-작성기 잠금에서 차단 된 다음 [IHostTask](ihosttask-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27df7-104">구문</span><span class="sxs-lookup"><span data-stu-id="27df7-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27df7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27df7-105">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="27df7-106">진행 [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)에 대 한 호출을 사용 하 여 만든 반복기입니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="27df7-107">제한이 잠금을 기다리는 다음에 대 한 포인터 `IHostTask` 이거나, 대기 중인 태스크가 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27df7-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="27df7-108">Return Value</span></span>  
  
|<span data-ttu-id="27df7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27df7-109">HRESULT</span></span>|<span data-ttu-id="27df7-110">설명</span><span class="sxs-lookup"><span data-stu-id="27df7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27df7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="27df7-111">S_OK</span></span>|<span data-ttu-id="27df7-112">`GetRWLockOwnerNext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="27df7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27df7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27df7-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27df7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27df7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27df7-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-116">The call timed out.</span></span>|  
|<span data-ttu-id="27df7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27df7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27df7-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27df7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27df7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27df7-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27df7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27df7-121">E_FAIL</span></span>|<span data-ttu-id="27df7-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27df7-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27df7-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27df7-125">설명</span><span class="sxs-lookup"><span data-stu-id="27df7-125">Remarks</span></span>  

 <span data-ttu-id="27df7-126">`ppOwnerHostTask`가 null로 설정 되 면 반복이 종료 되 고 호스트에서 [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27df7-127">CLR은에 `AddRef` 대해를 호출 하 여 `IHostTask` `ppOwnerHostTask` 호스트가 포인터를 보유 하는 동안이 작업을 종료 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="27df7-128">`Release`완료 되 면 호스트는를 호출 하 여 참조 횟수를 감소 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27df7-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27df7-129">Requirements</span></span>  

 <span data-ttu-id="27df7-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27df7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27df7-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27df7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27df7-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27df7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27df7-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27df7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27df7-134">참조</span><span class="sxs-lookup"><span data-stu-id="27df7-134">See also</span></span>

- [<span data-ttu-id="27df7-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27df7-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="27df7-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27df7-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
