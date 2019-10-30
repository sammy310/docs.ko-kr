---
title: IHostTaskManager::EndDelayAbort 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: cf79c0d0f6def46d7f4d55f17afbd1f1dff00ad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133068"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="c6865-102">IHostTaskManager::EndDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="c6865-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="c6865-103">이전에 [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)를 호출한 후 관리 코드가 현재 작업을 중단 하지 않아야 하는 기간 동안 관리 되는 코드가 종료 됨을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6865-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6865-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c6865-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6865-105">Return Value</span></span>  
  
|<span data-ttu-id="c6865-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6865-106">HRESULT</span></span>|<span data-ttu-id="c6865-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6865-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6865-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6865-108">S_OK</span></span>|<span data-ttu-id="c6865-109">`EndDelayAbort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="c6865-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6865-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6865-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6865-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6865-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6865-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-113">The call timed out.</span></span>|  
|<span data-ttu-id="c6865-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6865-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6865-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6865-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6865-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6865-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6865-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6865-118">E_FAIL</span></span>|<span data-ttu-id="c6865-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6865-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6865-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6865-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c6865-122">E_UNEXPECTED</span></span>|<span data-ttu-id="c6865-123">`BeginDelayAbort`에 대 한 해당 호출 없이 `EndDelayAbort`가 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6865-124">주의</span><span class="sxs-lookup"><span data-stu-id="c6865-124">Remarks</span></span>  
 <span data-ttu-id="c6865-125">CLR은 `EndDelayAbort`를 호출 하기 전에 현재 작업에 대 한 `BeginDelayAbort` 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="c6865-126">이러한 상응 하는 호출이 없으면 호스트의 [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) 구현에서 `EndDelayAbort`의 E_UNEXPECTED을 반환 해야 하 고 아무 작업도 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6865-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6865-127">Requirements</span></span>  
 <span data-ttu-id="c6865-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6865-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6865-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6865-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6865-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6865-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6865-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6865-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6865-132">참조</span><span class="sxs-lookup"><span data-stu-id="c6865-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="c6865-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6865-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c6865-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6865-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c6865-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6865-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c6865-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6865-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
