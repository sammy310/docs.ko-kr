---
title: IHostGCManager::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb78026f875c18a557951108518c9280f5eb567d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937675"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="f5b57-102">IHostGCManager::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="f5b57-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="f5b57-103">메서드 호출이 수행 된 스레드가 가비지 컬렉션에 대해 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5b57-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5b57-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f5b57-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f5b57-105">Return Value</span></span>  
  
|<span data-ttu-id="f5b57-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5b57-106">HRESULT</span></span>|<span data-ttu-id="f5b57-107">설명</span><span class="sxs-lookup"><span data-stu-id="f5b57-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5b57-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5b57-108">S_OK</span></span>|<span data-ttu-id="f5b57-109">`ThreadIsBlockingForSuspension`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="f5b57-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5b57-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5b57-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5b57-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5b57-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5b57-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-113">The call timed out.</span></span>|  
|<span data-ttu-id="f5b57-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5b57-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5b57-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5b57-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5b57-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5b57-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5b57-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5b57-118">E_FAIL</span></span>|<span data-ttu-id="f5b57-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5b57-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5b57-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5b57-122">설명</span><span class="sxs-lookup"><span data-stu-id="f5b57-122">Remarks</span></span>  
 <span data-ttu-id="f5b57-123">CLR은 일반적으로 가비지 `ThreadIsBlockForSuspension` 수집을 준비 하는 메서드를 호출 하 여 호스트에 관리 되지 않는 작업에 대 한 스레드를 다시 예약할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f5b57-124">호스트는를 호출한 후에만 작업을 `ThreadIsBlockingForSuspension`다시 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="f5b57-125">런타임에서 [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)를 호출한 후에는 호스트에서 작업을 다시 예약 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5b57-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5b57-126">Requirements</span></span>  
 <span data-ttu-id="f5b57-127">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5b57-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5b57-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5b57-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5b57-129">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b57-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5b57-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5b57-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b57-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5b57-131">See also</span></span>

- [<span data-ttu-id="f5b57-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5b57-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f5b57-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5b57-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f5b57-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5b57-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f5b57-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5b57-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f5b57-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5b57-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
