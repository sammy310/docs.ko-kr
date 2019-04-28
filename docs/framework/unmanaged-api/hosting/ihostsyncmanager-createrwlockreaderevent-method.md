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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5b640093184e10ef9e3b895ce2328969a45ac9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696342"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="0bbda-102">IHostSyncManager::CreateRWLockReaderEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="0bbda-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="0bbda-103">판독기 잠금 구현 하기 위한 수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbda-104">구문</span><span class="sxs-lookup"><span data-stu-id="0bbda-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bbda-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bbda-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="0bbda-106">[in] `true`이면 `ppEvent` 이 고, 그렇지 않으면 신호를 받은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="0bbda-107">[in] 판독기 잠금을 사용 하 여 연결 하는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="0bbda-108">[out] 주소에 대 한 포인터를 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bbda-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0bbda-109">Return Value</span></span>  
  
|<span data-ttu-id="0bbda-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bbda-110">HRESULT</span></span>|<span data-ttu-id="0bbda-111">설명</span><span class="sxs-lookup"><span data-stu-id="0bbda-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bbda-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bbda-112">S_OK</span></span>|<span data-ttu-id="0bbda-113">`CreateRWLockReaderEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="0bbda-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0bbda-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0bbda-115">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0bbda-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0bbda-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0bbda-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-117">The call timed out.</span></span>|  
|<span data-ttu-id="0bbda-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0bbda-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0bbda-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0bbda-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0bbda-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0bbda-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0bbda-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0bbda-122">E_FAIL</span></span>|<span data-ttu-id="0bbda-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0bbda-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0bbda-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0bbda-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0bbda-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0bbda-127">메모리가 부족 하 여 요청 된 이벤트 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bbda-128">설명</span><span class="sxs-lookup"><span data-stu-id="0bbda-128">Remarks</span></span>  
 <span data-ttu-id="0bbda-129">CLR 호출 `CreateRWLockReaderEvent` 을 참조 하는 `IHostManualEvent` 판독기 잠금 구현에 사용할 인스턴스를 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="0bbda-130">호스트를 쿼리하여 판독기 잠금을 기다리는 작업을 확인 하려면 쿠키를 사용할 수는 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbda-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bbda-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bbda-131">Requirements</span></span>  
 <span data-ttu-id="0bbda-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bbda-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbda-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0bbda-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bbda-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0bbda-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bbda-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbda-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbda-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bbda-136">See also</span></span>

- [<span data-ttu-id="0bbda-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bbda-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0bbda-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bbda-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="0bbda-139">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bbda-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="0bbda-140">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bbda-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
