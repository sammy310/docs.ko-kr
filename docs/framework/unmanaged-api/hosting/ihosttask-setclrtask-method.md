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
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121362"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="74474-102">IHostTask::SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="74474-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="74474-103">`ICLRTask` 인스턴스를 현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="74474-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74474-104">구문</span><span class="sxs-lookup"><span data-stu-id="74474-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74474-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74474-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="74474-106">진행 현재 `IHostTask` 인스턴스와 연결할 `ICLRTask` 인스턴스에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74474-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74474-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="74474-107">Return Value</span></span>  
  
|<span data-ttu-id="74474-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74474-108">HRESULT</span></span>|<span data-ttu-id="74474-109">설명</span><span class="sxs-lookup"><span data-stu-id="74474-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74474-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74474-110">S_OK</span></span>|<span data-ttu-id="74474-111">`SetCLRTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="74474-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74474-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74474-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74474-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74474-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74474-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-115">The call timed out.</span></span>|  
|<span data-ttu-id="74474-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74474-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74474-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74474-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74474-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74474-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74474-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74474-120">E_FAIL</span></span>|<span data-ttu-id="74474-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74474-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74474-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74474-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="74474-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74474-124">주의</span><span class="sxs-lookup"><span data-stu-id="74474-124">Remarks</span></span>  
 <span data-ttu-id="74474-125">CLR은 `SetCLRTask`를 호출 하 여 `ICLRTask` 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다 .이 인스턴스는 [IHostTaskManager:: Createtask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)를 호출 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74474-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74474-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74474-126">Requirements</span></span>  
 <span data-ttu-id="74474-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74474-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74474-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="74474-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74474-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74474-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74474-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74474-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74474-131">참조</span><span class="sxs-lookup"><span data-stu-id="74474-131">See also</span></span>

- [<span data-ttu-id="74474-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74474-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="74474-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74474-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="74474-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74474-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="74474-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74474-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
