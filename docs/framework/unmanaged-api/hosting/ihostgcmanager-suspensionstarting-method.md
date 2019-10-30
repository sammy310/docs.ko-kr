---
title: IHostGCManager::SuspensionStarting 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: bf1b830f55110c00356527bc9caa41dfd94ae377
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130464"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="9afd6-102">IHostGCManager::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="9afd6-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="9afd6-103">CLR (공용 언어 런타임)에서 가비지 수집을 수행 하기 위해 작업 실행을 일시 중단 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9afd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="9afd6-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9afd6-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="9afd6-105">Return Value</span></span>  
  
|<span data-ttu-id="9afd6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9afd6-106">HRESULT</span></span>|<span data-ttu-id="9afd6-107">설명</span><span class="sxs-lookup"><span data-stu-id="9afd6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9afd6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9afd6-108">S_OK</span></span>|<span data-ttu-id="9afd6-109">`SuspensionStarting` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="9afd6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9afd6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9afd6-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9afd6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9afd6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9afd6-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-113">The call timed out.</span></span>|  
|<span data-ttu-id="9afd6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9afd6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9afd6-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9afd6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9afd6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9afd6-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9afd6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9afd6-118">E_FAIL</span></span>|<span data-ttu-id="9afd6-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9afd6-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9afd6-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9afd6-122">주의</span><span class="sxs-lookup"><span data-stu-id="9afd6-122">Remarks</span></span>  
 <span data-ttu-id="9afd6-123">CLR은 `SuspensionStarting`를 호출 하 여 가비지 수집이 발생 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9afd6-124">이 작업을 다시 예약 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-124">Do not reschedule this task.</span></span> <span data-ttu-id="9afd6-125">[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) 가 호출 될 때 호스트에서 작업을 다시 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9afd6-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9afd6-126">Requirements</span></span>  
 <span data-ttu-id="9afd6-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9afd6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9afd6-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9afd6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9afd6-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9afd6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9afd6-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9afd6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afd6-131">참조</span><span class="sxs-lookup"><span data-stu-id="9afd6-131">See also</span></span>

- [<span data-ttu-id="9afd6-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9afd6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9afd6-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9afd6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9afd6-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9afd6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9afd6-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9afd6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="9afd6-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9afd6-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
