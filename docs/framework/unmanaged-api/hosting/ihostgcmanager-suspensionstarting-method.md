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
ms.openlocfilehash: f2b4028c78daf266e4ffecd86e6b0b30b9607d5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804811"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="fe7e8-102">IHostGCManager::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="fe7e8-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="fe7e8-103">CLR (공용 언어 런타임)에서 가비지 수집을 수행 하기 위해 작업 실행을 일시 중단 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe7e8-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fe7e8-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="fe7e8-105">Return Value</span></span>  
  
|<span data-ttu-id="fe7e8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe7e8-106">HRESULT</span></span>|<span data-ttu-id="fe7e8-107">Description</span><span class="sxs-lookup"><span data-stu-id="fe7e8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe7e8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe7e8-108">S_OK</span></span>|<span data-ttu-id="fe7e8-109">`SuspensionStarting`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="fe7e8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe7e8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe7e8-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe7e8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe7e8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe7e8-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-113">The call timed out.</span></span>|  
|<span data-ttu-id="fe7e8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe7e8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe7e8-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe7e8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe7e8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe7e8-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe7e8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe7e8-118">E_FAIL</span></span>|<span data-ttu-id="fe7e8-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe7e8-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe7e8-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe7e8-122">설명</span><span class="sxs-lookup"><span data-stu-id="fe7e8-122">Remarks</span></span>  
 <span data-ttu-id="fe7e8-123">CLR에서 `SuspensionStarting` 를 호출 하 여 가비지 수집이 발생 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fe7e8-124">이 작업을 다시 예약 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-124">Do not reschedule this task.</span></span> <span data-ttu-id="fe7e8-125">[ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) 가 호출 될 때 호스트에서 작업을 다시 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe7e8-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe7e8-126">Requirements</span></span>  
 <span data-ttu-id="fe7e8-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe7e8-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fe7e8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe7e8-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe7e8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe7e8-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe7e8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7e8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe7e8-131">See also</span></span>

- [<span data-ttu-id="fe7e8-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe7e8-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="fe7e8-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe7e8-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="fe7e8-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe7e8-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="fe7e8-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe7e8-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="fe7e8-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe7e8-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
