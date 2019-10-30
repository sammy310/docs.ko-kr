---
title: IHostSemaphore::ReleaseSemaphore 메서드
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139467"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="2e2f9-102">IHostSemaphore::ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="2e2f9-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="2e2f9-103">지정 된 크기 만큼 현재 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 인스턴스의 수를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e2f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e2f9-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e2f9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e2f9-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="2e2f9-106">진행 현재 `IHostSemaphore` 인스턴스의 개수를 증가 시킬 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="2e2f9-107">이 크기는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="2e2f9-108">제한이 이전 개수에 대 한 포인터 이거나, 호출자에 게 이전 개수가 필요 하지 않은 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e2f9-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="2e2f9-109">Return Value</span></span>  
  
|<span data-ttu-id="2e2f9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e2f9-110">HRESULT</span></span>|<span data-ttu-id="2e2f9-111">설명</span><span class="sxs-lookup"><span data-stu-id="2e2f9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e2f9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e2f9-112">S_OK</span></span>|<span data-ttu-id="2e2f9-113">`ReleaseSemaphore` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="2e2f9-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e2f9-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e2f9-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e2f9-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e2f9-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e2f9-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-117">The call timed out.</span></span>|  
|<span data-ttu-id="2e2f9-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e2f9-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e2f9-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e2f9-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e2f9-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e2f9-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e2f9-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e2f9-122">E_FAIL</span></span>|<span data-ttu-id="2e2f9-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e2f9-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e2f9-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e2f9-126">주의</span><span class="sxs-lookup"><span data-stu-id="2e2f9-126">Remarks</span></span>  
 <span data-ttu-id="2e2f9-127">일반적으로 CLR은 `ReleaseSemaphore`를 호출 하 여 리소스 사용을 완료 했음을 호스트에 알리고 `lReleaseCount` 매개 변수에 1 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e2f9-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e2f9-128">Requirements</span></span>  
 <span data-ttu-id="2e2f9-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e2f9-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e2f9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e2f9-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2f9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e2f9-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e2f9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2f9-133">참조</span><span class="sxs-lookup"><span data-stu-id="2e2f9-133">See also</span></span>

- [<span data-ttu-id="2e2f9-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e2f9-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2e2f9-135">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e2f9-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="2e2f9-136">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e2f9-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="2e2f9-137">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e2f9-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="2e2f9-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e2f9-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
