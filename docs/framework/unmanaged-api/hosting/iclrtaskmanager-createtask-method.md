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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8833daa9cd385a1a76c5b706f15a76bb15139b84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763440"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="2db44-102">ICLRTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="2db44-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="2db44-103">CLR (공용 언어 런타임)에서 새 작업을 만들도록 명시적으로 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db44-104">구문</span><span class="sxs-lookup"><span data-stu-id="2db44-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db44-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2db44-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="2db44-106">[out] 새로 만든 주소에 대 한 포인터 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), 또는 작업을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2db44-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="2db44-107">Return Value</span></span>  
  
|<span data-ttu-id="2db44-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2db44-108">HRESULT</span></span>|<span data-ttu-id="2db44-109">설명</span><span class="sxs-lookup"><span data-stu-id="2db44-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2db44-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2db44-110">S_OK</span></span>|<span data-ttu-id="2db44-111">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="2db44-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2db44-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2db44-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2db44-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2db44-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2db44-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-115">The call timed out.</span></span>|  
|<span data-ttu-id="2db44-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2db44-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2db44-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2db44-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2db44-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2db44-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2db44-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2db44-120">E_FAIL</span></span>|<span data-ttu-id="2db44-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2db44-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2db44-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2db44-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2db44-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2db44-125">요청된 된 리소스를 할당할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2db44-126">설명</span><span class="sxs-lookup"><span data-stu-id="2db44-126">Remarks</span></span>  
 <span data-ttu-id="2db44-127">CLR에서 초기화 시 자동으로 새 작업 사용자 코드의 형식을 사용 하 여 스레드를 만들 때의 <xref:System.Threading> 네임 스페이스 또는 스레드 풀의 크기는 증가 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2db44-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="2db44-128">또한 비관리 코드에서 관리 되는 함수를 호출할 때 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="2db44-129">`CreateTask` CLR에서 새 작업을 만들도록 명시적으로 요청할 수 있도록 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="2db44-130">예를 들어 호스트 preinitialize 데이터 구조에이 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2db44-131">새 작업을 일시 중단 된 상태로 반환 되 고 호스트를 명시적으로 호출할 때까지 일시 중단 된 상태로 유지 됩니다 [ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2db44-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db44-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2db44-132">Requirements</span></span>  
 <span data-ttu-id="2db44-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2db44-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db44-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2db44-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2db44-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2db44-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2db44-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db44-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db44-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="2db44-137">See also</span></span>

- [<span data-ttu-id="2db44-138">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2db44-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2db44-139">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2db44-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2db44-140">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2db44-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2db44-141">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2db44-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
