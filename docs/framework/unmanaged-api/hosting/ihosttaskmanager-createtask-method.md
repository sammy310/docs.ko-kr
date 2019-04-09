---
title: IHostTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eddb11ab56bae5243ea7d00614090bbfe774f71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096383"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="a4b6f-102">IHostTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="a4b6f-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="a4b6f-103">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4b6f-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4b6f-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="a4b6f-106">[in] 요청 된 크기 (바이트) 요청 된 스택을의 기본 크기에 대 한 0 (영)입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="a4b6f-107">[in] 함수에 대 한 포인터는 태스크를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="a4b6f-108">[in] 매개 변수를 사용 하는 함수, 함수 또는 null 전달 될 사용자 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="a4b6f-109">[out] 주소에 대 한 포인터를 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 태스크를 만들 수 없는 경우 호스트 또는 null가 만든 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="a4b6f-110">작업은 명시적으로 호출 하 여 시작 될 때까지 일시 중단 된 상태를 유지 [ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4b6f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a4b6f-111">Return Value</span></span>  
  
|<span data-ttu-id="a4b6f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4b6f-112">HRESULT</span></span>|<span data-ttu-id="a4b6f-113">설명</span><span class="sxs-lookup"><span data-stu-id="a4b6f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4b6f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4b6f-114">S_OK</span></span>|`CreateTask` <span data-ttu-id="a4b6f-115">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-115">returned successfully.</span></span>|  
|<span data-ttu-id="a4b6f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4b6f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4b6f-117">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4b6f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4b6f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4b6f-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-119">The call timed out.</span></span>|  
|<span data-ttu-id="a4b6f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4b6f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4b6f-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4b6f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4b6f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4b6f-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4b6f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4b6f-124">E_FAIL</span></span>|<span data-ttu-id="a4b6f-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4b6f-126">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4b6f-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a4b6f-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a4b6f-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a4b6f-129">메모리가 부족 하 여 요청된 작업을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4b6f-130">설명</span><span class="sxs-lookup"><span data-stu-id="a4b6f-130">Remarks</span></span>  
 <span data-ttu-id="a4b6f-131">CLR에서는 `CreateTask` 호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="a4b6f-132">호스트에 대 한 인터페이스 포인터를 반환 합니다.는 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="a4b6f-133">반환된 된 작업은 명시적으로 호출 하 여 시작 될 때까지 일시 중지 해야 `IHostTask::Start`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b6f-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4b6f-134">Requirements</span></span>  
 <span data-ttu-id="a4b6f-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4b6f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b6f-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4b6f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4b6f-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a4b6f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a4b6f-138">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a4b6f-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4b6f-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="a4b6f-139">See also</span></span>

- [<span data-ttu-id="a4b6f-140">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b6f-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a4b6f-141">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b6f-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a4b6f-142">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b6f-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a4b6f-143">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b6f-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
