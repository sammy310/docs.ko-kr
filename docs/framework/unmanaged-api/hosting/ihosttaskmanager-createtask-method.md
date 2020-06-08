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
ms.openlocfilehash: 4037ffe63d8ebfca67cbd0b3293d36be7481b1bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501419"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="4e117-102">IHostTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="4e117-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="4e117-103">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e117-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e117-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e117-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e117-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="4e117-106">진행 요청 된 스택의 요청 된 크기 (바이트) 이거나, 기본 크기의 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="4e117-107">진행 태스크가 실행 되는 함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="4e117-108">진행 함수에 전달 될 사용자 데이터에 대 한 포인터 이거나, 함수에서 매개 변수를 사용 하지 않는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="4e117-109">제한이 호스트에서 만든 [IHostTask](ihosttask-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 태스크를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-109">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="4e117-110">작업은 [IHostTask:: Start](ihosttask-start-method.md)를 호출 하 여 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e117-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="4e117-111">Return Value</span></span>  
  
|<span data-ttu-id="4e117-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e117-112">HRESULT</span></span>|<span data-ttu-id="4e117-113">설명</span><span class="sxs-lookup"><span data-stu-id="4e117-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e117-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e117-114">S_OK</span></span>|<span data-ttu-id="4e117-115">`CreateTask`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="4e117-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e117-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e117-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e117-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e117-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e117-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-119">The call timed out.</span></span>|  
|<span data-ttu-id="4e117-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e117-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e117-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e117-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e117-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e117-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e117-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e117-124">E_FAIL</span></span>|<span data-ttu-id="4e117-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e117-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e117-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4e117-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4e117-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4e117-129">메모리가 부족 하 여 요청한 작업을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e117-130">설명</span><span class="sxs-lookup"><span data-stu-id="4e117-130">Remarks</span></span>  
 <span data-ttu-id="4e117-131">CLR에서 `CreateTask` 를 호출 하 여 호스트가 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="4e117-132">호스트는 인스턴스에 대 한 인터페이스 포인터를 반환 합니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="4e117-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="4e117-133">반환 된 작업은에 대 한 호출에 의해 명시적으로 시작 될 때까지 일시 중단 된 상태로 유지 되어야 합니다 `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="4e117-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e117-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e117-134">Requirements</span></span>  
 <span data-ttu-id="4e117-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e117-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e117-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4e117-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e117-137">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e117-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e117-138">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e117-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e117-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e117-139">See also</span></span>

- [<span data-ttu-id="4e117-140">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e117-140">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4e117-141">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e117-141">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4e117-142">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e117-142">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4e117-143">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e117-143">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
