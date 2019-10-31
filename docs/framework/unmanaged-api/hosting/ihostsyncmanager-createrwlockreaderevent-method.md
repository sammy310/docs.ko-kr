---
title: IHostSyncManager::CreateRWLockReaderEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: 64cf6c80ab1cf4b3ca52c60d6e72b54c438f9f4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195847"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="d5684-102">IHostSyncManager::CreateRWLockReaderEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="d5684-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="d5684-103">판독기 잠금 구현에 대 한 수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5684-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5684-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5684-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5684-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="d5684-106">[in] `true``ppEvent` 신호를 받아야 하는 경우 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="d5684-107">진행 판독기 잠금과 연결할 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d5684-108">제한이 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5684-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d5684-109">Return Value</span></span>  
  
|<span data-ttu-id="d5684-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5684-110">HRESULT</span></span>|<span data-ttu-id="d5684-111">설명</span><span class="sxs-lookup"><span data-stu-id="d5684-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5684-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5684-112">S_OK</span></span>|<span data-ttu-id="d5684-113">`CreateRWLockReaderEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d5684-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5684-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5684-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5684-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5684-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5684-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-117">The call timed out.</span></span>|  
|<span data-ttu-id="d5684-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5684-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5684-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5684-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5684-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5684-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5684-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5684-122">E_FAIL</span></span>|<span data-ttu-id="d5684-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5684-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5684-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5684-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d5684-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d5684-127">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5684-128">주의</span><span class="sxs-lookup"><span data-stu-id="d5684-128">Remarks</span></span>  
 <span data-ttu-id="d5684-129">CLR은 `CreateRWLockReaderEvent`를 호출 하 여 판독기 잠금을 구현 하는 데 사용할 `IHostManualEvent` 인스턴스에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="d5684-130">호스트는 쿠키를 사용 하 여 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인터페이스를 쿼리하여 판독기 잠금에서 대기 중인 작업을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5684-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5684-131">Requirements</span></span>  
 <span data-ttu-id="d5684-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5684-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5684-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d5684-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5684-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5684-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5684-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5684-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5684-136">참조</span><span class="sxs-lookup"><span data-stu-id="d5684-136">See also</span></span>

- [<span data-ttu-id="d5684-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5684-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d5684-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5684-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d5684-139">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5684-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="d5684-140">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5684-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
