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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ec56345a5b48540d2451769f739a236a85e47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100615"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="5b54e-102">IHostSemaphore::ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="5b54e-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="5b54e-103">현재 개수를 증가 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 인스턴스에 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b54e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b54e-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b54e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b54e-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="5b54e-106">[in] 현재 개수를 늘릴 수 있는 크기 `IHostSemaphore` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5b54e-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="5b54e-107">이 크기는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="5b54e-108">[out] 이전 개수 또는 호출자에 게 이전 카운트를 필요 하지 않은 경우 null 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b54e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5b54e-109">Return Value</span></span>  
  
|<span data-ttu-id="5b54e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b54e-110">HRESULT</span></span>|<span data-ttu-id="5b54e-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b54e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b54e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b54e-112">S_OK</span></span>|`ReleaseSemaphore` <span data-ttu-id="5b54e-113">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-113">returned successfully.</span></span>|  
|<span data-ttu-id="5b54e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5b54e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5b54e-115">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5b54e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5b54e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5b54e-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-117">The call timed out.</span></span>|  
|<span data-ttu-id="5b54e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5b54e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5b54e-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5b54e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5b54e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5b54e-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5b54e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5b54e-122">E_FAIL</span></span>|<span data-ttu-id="5b54e-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5b54e-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5b54e-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b54e-126">설명</span><span class="sxs-lookup"><span data-stu-id="5b54e-126">Remarks</span></span>  
 <span data-ttu-id="5b54e-127">CLR은 일반적으로 호출 `ReleaseSemaphore` 1에 대 한 값을 전달 하 여 리소스 사용을 완료 했음을 호스트에 알리기 위해는 `lReleaseCount` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5b54e-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b54e-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b54e-128">Requirements</span></span>  
 <span data-ttu-id="5b54e-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b54e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b54e-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b54e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b54e-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5b54e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b54e-132">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5b54e-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b54e-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="5b54e-133">See also</span></span>

- [<span data-ttu-id="5b54e-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b54e-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5b54e-135">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b54e-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5b54e-136">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b54e-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5b54e-137">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b54e-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="5b54e-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5b54e-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
