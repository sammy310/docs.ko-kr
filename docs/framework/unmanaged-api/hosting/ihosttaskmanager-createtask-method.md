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
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177996"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="0e79a-102">IHostTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="0e79a-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="0e79a-103">호스트가 새 작업을 만들라는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e79a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0e79a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e79a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e79a-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="0e79a-106">【인】 요청된 크기(바이트)의 요청된 스택 또는 기본 크기의 경우 0(0)입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="0e79a-107">【인】 작업이 실행되는 함수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="0e79a-108">【인】 함수에 전달할 사용자 데이터에 대한 포인터 또는 함수에 매개 변수가 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="0e79a-109">【아웃】 호스트에서 만든 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스의 주소에 대한 포인터 또는 작업을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="0e79a-110">작업은 [IHostTask ::Start에](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)대한 호출에 의해 명시적으로 시작될 때까지 일시 중단된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e79a-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="0e79a-111">Return Value</span></span>  
  
|<span data-ttu-id="0e79a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e79a-112">HRESULT</span></span>|<span data-ttu-id="0e79a-113">Description</span><span class="sxs-lookup"><span data-stu-id="0e79a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e79a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e79a-114">S_OK</span></span>|<span data-ttu-id="0e79a-115">`CreateTask`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="0e79a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e79a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e79a-117">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e79a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e79a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e79a-119">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-119">The call timed out.</span></span>|  
|<span data-ttu-id="0e79a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e79a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e79a-121">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e79a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e79a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e79a-123">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e79a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e79a-124">E_FAIL</span></span>|<span data-ttu-id="0e79a-125">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e79a-126">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e79a-127">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0e79a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0e79a-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0e79a-129">요청된 작업을 만들 수 있는 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e79a-130">설명</span><span class="sxs-lookup"><span data-stu-id="0e79a-130">Remarks</span></span>  
 <span data-ttu-id="0e79a-131">CLR은 `CreateTask` 호스트가 새 작업을 만들도록 요청하도록 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="0e79a-132">호스트는 인스턴스에 인터페이스 `IHostTask` 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="0e79a-133">반환된 작업은 `IHostTask::Start`에 대한 호출에 의해 명시적으로 시작될 때까지 일시 중단된 상태로 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e79a-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e79a-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e79a-134">Requirements</span></span>  
 <span data-ttu-id="0e79a-135">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e79a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e79a-136">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="0e79a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e79a-137">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0e79a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e79a-138">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e79a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e79a-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e79a-139">See also</span></span>

- [<span data-ttu-id="0e79a-140">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e79a-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0e79a-141">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e79a-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0e79a-142">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e79a-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0e79a-143">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0e79a-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
