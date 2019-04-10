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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197973"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="f6b41-102">IHostTaskManager::BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="f6b41-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="f6b41-103">관리 코드는 호스트는 현재 작업 중단할 수 없는 기간이 시작 됨을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b41-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6b41-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f6b41-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f6b41-105">Return Value</span></span>  
  
|<span data-ttu-id="f6b41-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6b41-106">HRESULT</span></span>|<span data-ttu-id="f6b41-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6b41-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6b41-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6b41-108">S_OK</span></span>|`BeginDelayAbort` <span data-ttu-id="f6b41-109">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-109">returned successfully.</span></span>|  
|<span data-ttu-id="f6b41-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6b41-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6b41-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6b41-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6b41-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6b41-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-113">The call timed out.</span></span>|  
|<span data-ttu-id="f6b41-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6b41-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6b41-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6b41-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6b41-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6b41-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6b41-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6b41-118">E_FAIL</span></span>|<span data-ttu-id="f6b41-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6b41-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6b41-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6b41-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f6b41-122">E_UNEXPECTED</span></span>|`BeginDelayAbort` <span data-ttu-id="f6b41-123">가 이미 호출 된 해당 호출 되지만 [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) 아직 수신 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-123">has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6b41-124">설명</span><span class="sxs-lookup"><span data-stu-id="f6b41-124">Remarks</span></span>  
 <span data-ttu-id="f6b41-125">호스트 될 때까지 현재 작업을 중단 하지 해야 `EndDelayAbort` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="f6b41-126">다시 호출 하는 경우 `BeginDelayAbort` 에 대 한 중간 호출 없이 이루어집니다 `EndDelayAbort`, 호스트에서 E_UNEXPECTED를 반환 해야 `BeginDelayAbort`, 어떠한 작업도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b41-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b41-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6b41-127">Requirements</span></span>  
 <span data-ttu-id="f6b41-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f6b41-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b41-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6b41-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6b41-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f6b41-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f6b41-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f6b41-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6b41-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="f6b41-132">See also</span></span>

- [<span data-ttu-id="f6b41-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6b41-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f6b41-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6b41-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f6b41-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6b41-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
