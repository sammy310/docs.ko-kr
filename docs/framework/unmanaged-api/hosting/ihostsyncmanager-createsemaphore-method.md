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
ms.openlocfilehash: 02066d3923714e66bf287f1435b7854280c97cb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195826"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="adb7e-102">IHostSyncManager::CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="adb7e-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="adb7e-103">대기 이벤트에 대 한 세마포에 사용할 CLR (공용 언어 런타임)에 대 한 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adb7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="adb7e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adb7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="adb7e-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="adb7e-106">진행 `ppSemaphore`의 초기 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="adb7e-107">진행 `ppSemaphore`의 최대 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="adb7e-108">제한이 `IHostSemaphore` 인스턴스의 주소에 대 한 포인터 이거나, 세마포를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adb7e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="adb7e-109">Return Value</span></span>  
  
|<span data-ttu-id="adb7e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adb7e-110">HRESULT</span></span>|<span data-ttu-id="adb7e-111">설명</span><span class="sxs-lookup"><span data-stu-id="adb7e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adb7e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="adb7e-112">S_OK</span></span>|<span data-ttu-id="adb7e-113">`CreateSemaphore` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="adb7e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adb7e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adb7e-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adb7e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adb7e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adb7e-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-117">The call timed out.</span></span>|  
|<span data-ttu-id="adb7e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adb7e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adb7e-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adb7e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adb7e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adb7e-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adb7e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adb7e-122">E_FAIL</span></span>|<span data-ttu-id="adb7e-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adb7e-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adb7e-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="adb7e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="adb7e-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="adb7e-127">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adb7e-128">주의</span><span class="sxs-lookup"><span data-stu-id="adb7e-128">Remarks</span></span>  
 <span data-ttu-id="adb7e-129">`CreateSemaphore`는 이름이 같은 Win32 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="adb7e-130">`dwInitial` 및 `dwMax` 매개 변수는 각각 Win32 `lInitialCount` 및 `lMaximumCount` 매개 변수와 동일한 세마포 수의 의미 체계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="adb7e-131">`dwInitial`는 0에서 `dwMax`(포함) 사이 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="adb7e-132">`dwMax`는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adb7e-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adb7e-133">Requirements</span></span>  
 <span data-ttu-id="adb7e-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adb7e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adb7e-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="adb7e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adb7e-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb7e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adb7e-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adb7e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb7e-138">참조</span><span class="sxs-lookup"><span data-stu-id="adb7e-138">See also</span></span>

- [<span data-ttu-id="adb7e-139">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adb7e-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="adb7e-140">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adb7e-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="adb7e-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adb7e-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
