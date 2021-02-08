---
description: '자세히 알아보기: IHostTaskManager:: CreateTask 메서드'
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
ms.openlocfilehash: c14c80ea9067b0a28e7b9186ea66eb695687bf27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784576"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="c63c1-103">IHostTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="c63c1-103">IHostTaskManager::CreateTask Method</span></span>

<span data-ttu-id="c63c1-104">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-104">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c63c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="c63c1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c63c1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c63c1-106">Parameters</span></span>  

 `stacksize`  
 <span data-ttu-id="c63c1-107">진행 요청 된 스택의 요청 된 크기 (바이트) 이거나, 기본 크기의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-107">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="c63c1-108">진행 태스크가 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-108">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="c63c1-109">진행 함수에 전달 될 사용자 데이터에 대 한 포인터 이거나, 함수에서 매개 변수를 사용 하지 않는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-109">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="c63c1-110">제한이 호스트에서 만든 [IHostTask](ihosttask-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 태스크를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-110">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="c63c1-111">작업은 [IHostTask:: Start](ihosttask-start-method.md)를 호출 하 여 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-111">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c63c1-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="c63c1-112">Return Value</span></span>  
  
|<span data-ttu-id="c63c1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c63c1-113">HRESULT</span></span>|<span data-ttu-id="c63c1-114">설명</span><span class="sxs-lookup"><span data-stu-id="c63c1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c63c1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c63c1-115">S_OK</span></span>|<span data-ttu-id="c63c1-116">`CreateTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-116">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="c63c1-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c63c1-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c63c1-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c63c1-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c63c1-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c63c1-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-120">The call timed out.</span></span>|  
|<span data-ttu-id="c63c1-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c63c1-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c63c1-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c63c1-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c63c1-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c63c1-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c63c1-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c63c1-125">E_FAIL</span></span>|<span data-ttu-id="c63c1-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c63c1-127">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c63c1-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c63c1-129">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c63c1-129">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c63c1-130">메모리가 부족 하 여 요청한 작업을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-130">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c63c1-131">설명</span><span class="sxs-lookup"><span data-stu-id="c63c1-131">Remarks</span></span>  

 <span data-ttu-id="c63c1-132">CLR에서 `CreateTask` 를 호출 하 여 호스트가 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-132">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="c63c1-133">호스트는 인스턴스에 대 한 인터페이스 포인터를 반환 합니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="c63c1-133">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="c63c1-134">반환 된 작업은에 대 한 호출에 의해 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 되어야 합니다 `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="c63c1-134">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c63c1-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c63c1-135">Requirements</span></span>  

 <span data-ttu-id="c63c1-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c63c1-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c63c1-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c63c1-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c63c1-138">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c63c1-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c63c1-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c63c1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63c1-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c63c1-140">See also</span></span>

- [<span data-ttu-id="c63c1-141">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c63c1-141">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c63c1-142">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c63c1-142">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c63c1-143">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c63c1-143">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c63c1-144">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c63c1-144">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
