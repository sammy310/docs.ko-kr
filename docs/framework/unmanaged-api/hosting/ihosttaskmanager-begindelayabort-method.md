---
title: IHostTaskManager::BeginDelayAbort 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: b765d5449cebbdec5f106a8e4743fee2f0ee5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133131"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="09938-102">IHostTaskManager::BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="09938-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="09938-103">관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 입력 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="09938-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09938-104">구문</span><span class="sxs-lookup"><span data-stu-id="09938-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="09938-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="09938-105">Return Value</span></span>  
  
|<span data-ttu-id="09938-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09938-106">HRESULT</span></span>|<span data-ttu-id="09938-107">설명</span><span class="sxs-lookup"><span data-stu-id="09938-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09938-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="09938-108">S_OK</span></span>|<span data-ttu-id="09938-109">`BeginDelayAbort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="09938-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09938-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09938-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09938-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09938-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09938-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-113">The call timed out.</span></span>|  
|<span data-ttu-id="09938-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09938-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09938-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09938-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09938-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09938-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09938-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09938-118">E_FAIL</span></span>|<span data-ttu-id="09938-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09938-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09938-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09938-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09938-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="09938-122">E_UNEXPECTED</span></span>|<span data-ttu-id="09938-123">`BeginDelayAbort` 이미 호출 되었지만 [Enddelayabort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) 에 대 한 해당 호출이 아직 수신 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="09938-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09938-124">주의</span><span class="sxs-lookup"><span data-stu-id="09938-124">Remarks</span></span>  
 <span data-ttu-id="09938-125">`EndDelayAbort`가 호출 될 때까지 호스트에서 현재 작업을 중단 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09938-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="09938-126">`EndDelayAbort`를 중간에 호출 하지 않고 `BeginDelayAbort`에 대 한 다른 호출을 수행 하는 경우 호스트는 `BeginDelayAbort`에서 E_UNEXPECTED를 반환 해야 하며 아무 작업도 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09938-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09938-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09938-127">Requirements</span></span>  
 <span data-ttu-id="09938-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09938-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09938-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09938-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09938-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09938-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09938-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09938-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09938-132">참조</span><span class="sxs-lookup"><span data-stu-id="09938-132">See also</span></span>

- [<span data-ttu-id="09938-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09938-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="09938-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09938-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="09938-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09938-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
