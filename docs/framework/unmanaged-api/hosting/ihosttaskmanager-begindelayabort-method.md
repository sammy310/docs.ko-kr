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
ms.openlocfilehash: ea3269d06fdd3f5a2e365465d45ba6e569127b0a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842376"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="533fe-102">IHostTaskManager::BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="533fe-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="533fe-103">관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 입력 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="533fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="533fe-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="533fe-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="533fe-105">Return Value</span></span>  
  
|<span data-ttu-id="533fe-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="533fe-106">HRESULT</span></span>|<span data-ttu-id="533fe-107">Description</span><span class="sxs-lookup"><span data-stu-id="533fe-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="533fe-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="533fe-108">S_OK</span></span>|<span data-ttu-id="533fe-109">`BeginDelayAbort`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="533fe-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="533fe-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="533fe-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="533fe-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="533fe-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="533fe-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-113">The call timed out.</span></span>|  
|<span data-ttu-id="533fe-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="533fe-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="533fe-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="533fe-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="533fe-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="533fe-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="533fe-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="533fe-118">E_FAIL</span></span>|<span data-ttu-id="533fe-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="533fe-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="533fe-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="533fe-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="533fe-122">E_UNEXPECTED</span></span>|<span data-ttu-id="533fe-123">`BeginDelayAbort`가 이미 호출 되었지만 [Enddelayabort](ihosttaskmanager-enddelayabort-method.md) 에 대 한 해당 호출을 아직 받지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="533fe-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="533fe-124">설명</span><span class="sxs-lookup"><span data-stu-id="533fe-124">Remarks</span></span>  
 <span data-ttu-id="533fe-125">호스트는가 호출 될 때까지 현재 작업을 중단 해서는 안 됩니다 `EndDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="533fe-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="533fe-126">에 대 한 중간 호출 없이에 대 한 다른 호출을 수행 하는 경우 `BeginDelayAbort` `EndDelayAbort` 호스트는에서 E_UNEXPECTED을 반환 해야 `BeginDelayAbort` 하며 작업을 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="533fe-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="533fe-127">Requirements</span></span>  
 <span data-ttu-id="533fe-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="533fe-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="533fe-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="533fe-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="533fe-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="533fe-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="533fe-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="533fe-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533fe-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="533fe-132">See also</span></span>

- [<span data-ttu-id="533fe-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533fe-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="533fe-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533fe-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="533fe-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533fe-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
