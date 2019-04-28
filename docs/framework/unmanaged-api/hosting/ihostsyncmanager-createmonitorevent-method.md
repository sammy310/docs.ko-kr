---
title: IHostSyncManager::CreateMonitorEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12b0e32ab46b3e8ba5120da4b16a10db85f105a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696303"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="ba608-102">IHostSyncManager::CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="ba608-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="ba608-103">자동 재설정 이벤트를 모니터링 대상된 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba608-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba608-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba608-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba608-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ba608-106">[in] 이벤트 개체를 사용 하 여 연결 하는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="ba608-107">[out] 주소에 대 한 포인터를 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스이거나, 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba608-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="ba608-108">Return Value</span></span>  
  
|<span data-ttu-id="ba608-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba608-109">HRESULT</span></span>|<span data-ttu-id="ba608-110">설명</span><span class="sxs-lookup"><span data-stu-id="ba608-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba608-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba608-111">S_OK</span></span>|<span data-ttu-id="ba608-112">`CreateMonitorEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ba608-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba608-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba608-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba608-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba608-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba608-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-116">The call timed out.</span></span>|  
|<span data-ttu-id="ba608-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba608-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba608-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba608-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba608-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba608-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba608-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba608-121">E_FAIL</span></span>|<span data-ttu-id="ba608-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba608-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba608-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ba608-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ba608-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ba608-126">메모리가 부족 하 여 요청 된 이벤트 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba608-127">설명</span><span class="sxs-lookup"><span data-stu-id="ba608-127">Remarks</span></span>  
 <span data-ttu-id="ba608-128">`CreateMonitorEvent` 반환 합니다는 `IHostAutoEvent` CLR의 관리 되는 구현에서 사용 하는 <xref:System.Threading.Monitor?displayProperty=nameWithType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ba608-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="ba608-129">이 메서드는 Win32를 미러링합니다 `CreateEvent` 값을 사용 하 여 함수를 `false` 에 대해 지정 된 된 `bManualReset` 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="ba608-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="ba608-130">호스트를 호출 하 여 작업 모니터의 대기를 확인 하려면 쿠키를 사용할 수는 [iclrsyncmanager:: Getmonitorowner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ba608-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba608-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba608-131">Requirements</span></span>  
 <span data-ttu-id="ba608-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba608-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba608-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba608-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba608-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ba608-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba608-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba608-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba608-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba608-136">See also</span></span>

- [<span data-ttu-id="ba608-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba608-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ba608-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba608-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="ba608-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba608-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
