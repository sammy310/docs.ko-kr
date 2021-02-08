---
description: '자세히 알아보기: IHostTaskManager:: BeginDelayAbort 메서드'
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
ms.openlocfilehash: f991690af4f7e634c8d845bdbd09f690b4ea3af7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784615"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="6b44f-103">IHostTaskManager::BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="6b44f-103">IHostTaskManager::BeginDelayAbort Method</span></span>

<span data-ttu-id="6b44f-104">관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 입력 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-104">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b44f-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b44f-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6b44f-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="6b44f-106">Return Value</span></span>  
  
|<span data-ttu-id="6b44f-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b44f-107">HRESULT</span></span>|<span data-ttu-id="6b44f-108">설명</span><span class="sxs-lookup"><span data-stu-id="6b44f-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b44f-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b44f-109">S_OK</span></span>|<span data-ttu-id="6b44f-110">`BeginDelayAbort` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-110">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="6b44f-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b44f-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b44f-112">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6b44f-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6b44f-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6b44f-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-114">The call timed out.</span></span>|  
|<span data-ttu-id="6b44f-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b44f-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6b44f-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6b44f-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6b44f-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6b44f-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6b44f-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b44f-119">E_FAIL</span></span>|<span data-ttu-id="6b44f-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6b44f-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6b44f-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6b44f-123">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="6b44f-123">E_UNEXPECTED</span></span>|<span data-ttu-id="6b44f-124">`BeginDelayAbort` 가 이미 호출 되었지만 [Enddelayabort](ihosttaskmanager-enddelayabort-method.md) 에 대 한 해당 호출을 아직 받지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="6b44f-124">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b44f-125">설명</span><span class="sxs-lookup"><span data-stu-id="6b44f-125">Remarks</span></span>  

 <span data-ttu-id="6b44f-126">호스트는가 호출 될 때까지 현재 작업을 중단 해서는 안 됩니다 `EndDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="6b44f-126">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="6b44f-127">에 대 한 중간 호출 없이에 대 한 다른 호출을 수행 하는 경우 `BeginDelayAbort` `EndDelayAbort` 호스트는에서 E_UNEXPECTED을 반환 해야 `BeginDelayAbort` 하며 작업을 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-127">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b44f-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b44f-128">Requirements</span></span>  

 <span data-ttu-id="6b44f-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b44f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b44f-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6b44f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b44f-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b44f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b44f-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b44f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b44f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b44f-133">See also</span></span>

- [<span data-ttu-id="6b44f-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b44f-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6b44f-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b44f-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6b44f-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b44f-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
