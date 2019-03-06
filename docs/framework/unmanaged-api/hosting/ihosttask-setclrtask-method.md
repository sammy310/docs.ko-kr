---
title: IHostTask::SetCLRTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 239a73bac205f111f7ba299af7613c0fd78ab060
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466909"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="e0ee0-102">IHostTask::SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="e0ee0-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="e0ee0-103">연결 프로그램 `ICLRTask` 현재 인스턴스와 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ee0-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0ee0-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0ee0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0ee0-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="e0ee0-106">[in] 에 대 한 인터페이스 포인터를 `ICLRTask` 인스턴스가 현재 연관된 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0ee0-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e0ee0-107">Return Value</span></span>  
  
|<span data-ttu-id="e0ee0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0ee0-108">HRESULT</span></span>|<span data-ttu-id="e0ee0-109">설명</span><span class="sxs-lookup"><span data-stu-id="e0ee0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0ee0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0ee0-110">S_OK</span></span>|<span data-ttu-id="e0ee0-111">`SetCLRTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="e0ee0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0ee0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0ee0-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0ee0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0ee0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0ee0-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-115">The call timed out.</span></span>|  
|<span data-ttu-id="e0ee0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0ee0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0ee0-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0ee0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0ee0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0ee0-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0ee0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0ee0-120">E_FAIL</span></span>|<span data-ttu-id="e0ee0-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0ee0-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0ee0-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ee0-124">설명</span><span class="sxs-lookup"><span data-stu-id="e0ee0-124">Remarks</span></span>  
 <span data-ttu-id="e0ee0-125">CLR 호출 `SetCLRTask` 연결 하는 `ICLRTask` 현재 인스턴스와 `IHostTask` 인스턴스를 호출 하 여 만든 [ihosttaskmanager:: Createtask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ee0-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0ee0-126">Requirements</span></span>  
 <span data-ttu-id="e0ee0-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0ee0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ee0-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0ee0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0ee0-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e0ee0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0ee0-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ee0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ee0-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0ee0-131">See also</span></span>
- [<span data-ttu-id="e0ee0-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ee0-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e0ee0-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ee0-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e0ee0-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ee0-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e0ee0-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0ee0-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
