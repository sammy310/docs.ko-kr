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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ef5bb2539820d5a7bcd4ca6b4de86564290709
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213092"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="ec54b-102">IHostGCManager::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="ec54b-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="ec54b-103">CLR (공용 언어 런타임) 가비지 수집을 수행 하기 위해 작업 실행을 중단 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec54b-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec54b-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ec54b-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ec54b-105">Return Value</span></span>  
  
|<span data-ttu-id="ec54b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec54b-106">HRESULT</span></span>|<span data-ttu-id="ec54b-107">설명</span><span class="sxs-lookup"><span data-stu-id="ec54b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec54b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec54b-108">S_OK</span></span>|<span data-ttu-id="ec54b-109">`SuspensionStarting` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="ec54b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec54b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec54b-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec54b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec54b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec54b-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-113">The call timed out.</span></span>|  
|<span data-ttu-id="ec54b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec54b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec54b-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec54b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec54b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec54b-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec54b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec54b-118">E_FAIL</span></span>|<span data-ttu-id="ec54b-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec54b-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec54b-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec54b-122">설명</span><span class="sxs-lookup"><span data-stu-id="ec54b-122">Remarks</span></span>  
 <span data-ttu-id="ec54b-123">CLR에서는 `SuspensionStarting` 가비지 수집이 발생 하는 호스트에 알림을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec54b-124">이 작업을 다시 예약 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-124">Do not reschedule this task.</span></span> <span data-ttu-id="ec54b-125">호스트에는 작업을 다시 예약 해야 하면 [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec54b-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec54b-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec54b-126">Requirements</span></span>  
 <span data-ttu-id="ec54b-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec54b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec54b-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec54b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec54b-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ec54b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec54b-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec54b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec54b-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="ec54b-131">See also</span></span>

- [<span data-ttu-id="ec54b-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec54b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ec54b-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec54b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ec54b-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec54b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ec54b-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec54b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ec54b-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec54b-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
