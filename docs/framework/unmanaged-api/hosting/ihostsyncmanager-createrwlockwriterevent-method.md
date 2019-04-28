---
title: IHostSyncManager::CreateRWLockWriterEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e994cf5c68871d6e81d53ac522259bc973c173ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696296"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="8ff4f-102">IHostSyncManager::CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="8ff4f-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="8ff4f-103">기록기 잠금 구현에 대 한 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff4f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ff4f-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ff4f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ff4f-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="8ff4f-106">[in] 자동 재설정 이벤트와 연결 하는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="8ff4f-107">[out] 주소에 대 한 포인터를 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ff4f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="8ff4f-108">Return Value</span></span>  
  
|<span data-ttu-id="8ff4f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ff4f-109">HRESULT</span></span>|<span data-ttu-id="8ff4f-110">설명</span><span class="sxs-lookup"><span data-stu-id="8ff4f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ff4f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ff4f-111">S_OK</span></span>|<span data-ttu-id="8ff4f-112">`CreateRWLockWriterEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8ff4f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ff4f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ff4f-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ff4f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ff4f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ff4f-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-116">The call timed out.</span></span>|  
|<span data-ttu-id="8ff4f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ff4f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ff4f-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ff4f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ff4f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ff4f-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ff4f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ff4f-121">E_FAIL</span></span>|<span data-ttu-id="8ff4f-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ff4f-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ff4f-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ff4f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ff4f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8ff4f-126">메모리가 부족 하 여 요청 된 이벤트 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ff4f-127">설명</span><span class="sxs-lookup"><span data-stu-id="8ff4f-127">Remarks</span></span>  
 <span data-ttu-id="8ff4f-128">CLR에서는 합니다 `CreateRWLockWriterEvent` 을 참조 하는 방법은 `IHostAutoEvent` 기록기 잠금 구현에 사용할 인스턴스를 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="8ff4f-129">호스트의 반복 메서드를 호출 하 여 잠금을 기다리는 작업을 확인 하려면 지정된 된 쿠키를 사용할 수는 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff4f-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ff4f-130">Requirements</span></span>  
 <span data-ttu-id="8ff4f-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ff4f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff4f-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ff4f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ff4f-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8ff4f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ff4f-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff4f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff4f-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ff4f-135">See also</span></span>

- [<span data-ttu-id="8ff4f-136">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ff4f-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8ff4f-137">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ff4f-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8ff4f-138">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ff4f-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8ff4f-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ff4f-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
