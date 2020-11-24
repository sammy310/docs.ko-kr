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
ms.openlocfilehash: 660062fb69bb8fe0a06bbca9046d65175fb72f9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683032"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="3db61-102">IHostSemaphore::ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="3db61-102">IHostSemaphore::ReleaseSemaphore Method</span></span>

<span data-ttu-id="3db61-103">지정 된 크기 만큼 현재 [IHostSemaphore](ihostsemaphore-interface.md) 인스턴스의 수를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db61-104">구문</span><span class="sxs-lookup"><span data-stu-id="3db61-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3db61-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3db61-105">Parameters</span></span>  

 `lReleaseCount`  
 <span data-ttu-id="3db61-106">진행 현재 인스턴스의 개수를 증가 시킬 크기입니다 `IHostSemaphore` .</span><span class="sxs-lookup"><span data-stu-id="3db61-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="3db61-107">이 크기는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="3db61-108">제한이 이전 개수에 대 한 포인터 이거나, 호출자에 게 이전 개수가 필요 하지 않은 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3db61-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="3db61-109">Return Value</span></span>  
  
|<span data-ttu-id="3db61-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3db61-110">HRESULT</span></span>|<span data-ttu-id="3db61-111">설명</span><span class="sxs-lookup"><span data-stu-id="3db61-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3db61-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3db61-112">S_OK</span></span>|<span data-ttu-id="3db61-113">`ReleaseSemaphore` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="3db61-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3db61-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3db61-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3db61-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3db61-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3db61-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-117">The call timed out.</span></span>|  
|<span data-ttu-id="3db61-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3db61-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3db61-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3db61-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3db61-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3db61-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3db61-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3db61-122">E_FAIL</span></span>|<span data-ttu-id="3db61-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3db61-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3db61-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3db61-126">설명</span><span class="sxs-lookup"><span data-stu-id="3db61-126">Remarks</span></span>  

 <span data-ttu-id="3db61-127">일반적으로 CLR은 `ReleaseSemaphore` 를 호출 하 여 리소스 사용을 완료 했음을 호스트에 알리고 매개 변수에 1 값을 전달 `lReleaseCount` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db61-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3db61-128">Requirements</span></span>  

 <span data-ttu-id="3db61-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3db61-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db61-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3db61-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3db61-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db61-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3db61-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3db61-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db61-133">참조</span><span class="sxs-lookup"><span data-stu-id="3db61-133">See also</span></span>

- [<span data-ttu-id="3db61-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db61-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3db61-135">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db61-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3db61-136">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db61-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="3db61-137">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db61-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="3db61-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db61-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
