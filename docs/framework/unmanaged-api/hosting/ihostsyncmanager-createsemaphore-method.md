---
title: IHostSyncManager::CreateSemaphore 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43935829d11a925d4a3389149f5c316df15f06bb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764592"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="0a65d-102">IHostSyncManager::CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="0a65d-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="0a65d-103">만듭니다는 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 대기 이벤트 세마포로 사용할 공용 언어 런타임 (CLR)에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a65d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a65d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a65d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a65d-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="0a65d-106">[in] 초기 카운트 `ppSemaphore`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="0a65d-107">[in] 최대 수 `ppSemaphore`입니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="0a65d-108">[out] 주소에 대 한 포인터는 `IHostSemaphore` 인스턴스이거나, 세마포를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a65d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0a65d-109">Return Value</span></span>  
  
|<span data-ttu-id="0a65d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a65d-110">HRESULT</span></span>|<span data-ttu-id="0a65d-111">설명</span><span class="sxs-lookup"><span data-stu-id="0a65d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a65d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a65d-112">S_OK</span></span>|<span data-ttu-id="0a65d-113">`CreateSemaphore` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="0a65d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a65d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a65d-115">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a65d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a65d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a65d-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-117">The call timed out.</span></span>|  
|<span data-ttu-id="0a65d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a65d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a65d-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a65d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a65d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a65d-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a65d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a65d-122">E_FAIL</span></span>|<span data-ttu-id="0a65d-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a65d-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a65d-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0a65d-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0a65d-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0a65d-127">메모리가 부족 하 여 요청 된 이벤트 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a65d-128">설명</span><span class="sxs-lookup"><span data-stu-id="0a65d-128">Remarks</span></span>  
 <span data-ttu-id="0a65d-129">`CreateSemaphore` 이름이 같은 Win32 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="0a65d-130">합니다 `dwInitial` 하 고 `dwMax` 매개 변수 win32 세마포 개수에 대 한 동일한 의미 체계를 사용 `lInitialCount` 및 `lMaximumCount` 매개 변수를 각각.</span><span class="sxs-lookup"><span data-stu-id="0a65d-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="0a65d-131">`dwInitial` 0 사이 여야 하 고 `dwMax`(포함).</span><span class="sxs-lookup"><span data-stu-id="0a65d-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="0a65d-132">`dwMax` 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a65d-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a65d-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a65d-133">Requirements</span></span>  
 <span data-ttu-id="0a65d-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a65d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a65d-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a65d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a65d-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0a65d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a65d-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a65d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a65d-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a65d-138">See also</span></span>

- [<span data-ttu-id="0a65d-139">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a65d-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0a65d-140">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a65d-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="0a65d-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a65d-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
