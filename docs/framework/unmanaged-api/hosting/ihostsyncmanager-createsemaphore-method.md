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
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803133"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="acc0d-102">IHostSyncManager::CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="acc0d-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="acc0d-103">대기 이벤트에 대 한 세마포에 사용할 CLR (공용 언어 런타임)에 대 한 [IHostSemaphore](ihostsemaphore-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="acc0d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc0d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="acc0d-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="acc0d-106">진행 의 초기 개수 `ppSemaphore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="acc0d-107">진행 의 최대 개수 `ppSemaphore` 입니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="acc0d-108">제한이 인스턴스의 주소에 대 한 포인터 `IHostSemaphore` 이거나, 세마포를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acc0d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="acc0d-109">Return Value</span></span>  
  
|<span data-ttu-id="acc0d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acc0d-110">HRESULT</span></span>|<span data-ttu-id="acc0d-111">Description</span><span class="sxs-lookup"><span data-stu-id="acc0d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acc0d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="acc0d-112">S_OK</span></span>|<span data-ttu-id="acc0d-113">`CreateSemaphore`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="acc0d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acc0d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acc0d-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="acc0d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="acc0d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="acc0d-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-117">The call timed out.</span></span>|  
|<span data-ttu-id="acc0d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="acc0d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="acc0d-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="acc0d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="acc0d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="acc0d-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="acc0d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acc0d-122">E_FAIL</span></span>|<span data-ttu-id="acc0d-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="acc0d-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="acc0d-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="acc0d-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="acc0d-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="acc0d-127">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acc0d-128">설명</span><span class="sxs-lookup"><span data-stu-id="acc0d-128">Remarks</span></span>  
 <span data-ttu-id="acc0d-129">`CreateSemaphore`이름이 같은 Win32 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="acc0d-130">`dwInitial`및 `dwMax` 매개 변수는 `lInitialCount` 각각 Win32 및 매개 변수와 동일한 세마포 수의 의미 체계를 사용 합니다 `lMaximumCount` .</span><span class="sxs-lookup"><span data-stu-id="acc0d-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="acc0d-131">`dwInitial`0과 (포함) 사이 여야 합니다 `dwMax` .</span><span class="sxs-lookup"><span data-stu-id="acc0d-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="acc0d-132">`dwMax`0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc0d-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acc0d-133">Requirements</span></span>  
 <span data-ttu-id="acc0d-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="acc0d-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc0d-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="acc0d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acc0d-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acc0d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acc0d-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc0d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc0d-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acc0d-138">See also</span></span>

- [<span data-ttu-id="acc0d-139">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc0d-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="acc0d-140">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc0d-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="acc0d-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acc0d-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
