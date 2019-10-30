---
title: ICLRTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: fcb78dd5374ff97f23d7dfea63fe33fa96836958
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124543"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="c3465-102">ICLRTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="c3465-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="c3465-103">CLR (공용 언어 런타임)이 새 작업을 만들도록 명시적으로 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3465-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3465-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3465-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3465-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="c3465-106">제한이 새로 만든 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)의 주소에 대 한 포인터 이거나, 태스크를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3465-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3465-107">Return Value</span></span>  
  
|<span data-ttu-id="c3465-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3465-108">HRESULT</span></span>|<span data-ttu-id="c3465-109">설명</span><span class="sxs-lookup"><span data-stu-id="c3465-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3465-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3465-110">S_OK</span></span>|<span data-ttu-id="c3465-111">메서드가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="c3465-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3465-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3465-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3465-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3465-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3465-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-115">The call timed out.</span></span>|  
|<span data-ttu-id="c3465-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3465-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3465-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3465-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3465-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3465-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3465-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3465-120">E_FAIL</span></span>|<span data-ttu-id="c3465-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3465-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3465-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c3465-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c3465-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c3465-125">메모리가 부족 하 여 요청 된 리소스를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3465-126">주의</span><span class="sxs-lookup"><span data-stu-id="c3465-126">Remarks</span></span>  
 <span data-ttu-id="c3465-127">사용자 코드에서 <xref:System.Threading> 네임 스페이스의 형식을 사용 하 여 스레드를 만들거나 스레드 풀의 크기가 증가할 때 CLR은 초기화 시 자동으로 새 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="c3465-128">또한 비관리 코드에서 관리 되는 함수를 호출할 때 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="c3465-129">`CreateTask`를 사용 하면 호스트가 CLR에서 새 작업을 만들도록 명시적 요청을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="c3465-130">예를 들어 호스트는이 메서드를 호출 하 여 데이터 구조를 미리 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c3465-131">새 작업은 일시 중단 된 상태로 반환 되 고 호스트가 명시적으로 [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)를 호출할 때까지 일시 중단 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3465-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3465-132">Requirements</span></span>  
 <span data-ttu-id="c3465-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3465-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3465-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c3465-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3465-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3465-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3465-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3465-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3465-137">참조</span><span class="sxs-lookup"><span data-stu-id="c3465-137">See also</span></span>

- [<span data-ttu-id="c3465-138">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3465-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c3465-139">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3465-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c3465-140">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3465-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c3465-141">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3465-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
