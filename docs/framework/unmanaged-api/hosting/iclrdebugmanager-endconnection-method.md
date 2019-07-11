---
title: ICLRDebugManager::EndConnection 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc9d32f83b4b6384e28f012b9329ea18913a1218
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773157"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="70ef9-102">ICLRDebugManager::EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="70ef9-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="70ef9-103">작업 목록 및 식별자 및 이름을 간의 연결을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ef9-104">구문</span><span class="sxs-lookup"><span data-stu-id="70ef9-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70ef9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70ef9-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="70ef9-106">[in] 연결 및 연결 된 공용 언어 런타임 (CLR) 작업 목록에 대 한 호스트 관련 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70ef9-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="70ef9-107">Return Value</span></span>  
  
|<span data-ttu-id="70ef9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70ef9-108">HRESULT</span></span>|<span data-ttu-id="70ef9-109">설명</span><span class="sxs-lookup"><span data-stu-id="70ef9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70ef9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="70ef9-110">S_OK</span></span>|<span data-ttu-id="70ef9-111">`EndConnection` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="70ef9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70ef9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70ef9-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70ef9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70ef9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70ef9-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-115">The call timed out.</span></span>|  
|<span data-ttu-id="70ef9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70ef9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70ef9-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70ef9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70ef9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70ef9-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70ef9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70ef9-120">E_FAIL</span></span>|<span data-ttu-id="70ef9-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70ef9-122">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70ef9-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="70ef9-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="70ef9-124">E_INVALIDARG</span></span>|<span data-ttu-id="70ef9-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) 되지를 사용 하 여 호출한 `dwConnectionId`, 또는 `dwConnectionId` 이 0입니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70ef9-126">설명</span><span class="sxs-lookup"><span data-stu-id="70ef9-126">Remarks</span></span>  
 <span data-ttu-id="70ef9-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 세 가지 방법을 제공 `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), 및 `EndConnection`, 식별자 및 이름을 사용 하 여 작업 목록을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="70ef9-128">이러한 세 가지 메서드는 작업의 각 집합에 대 한 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="70ef9-129">`BeginConnection` 새 연결을 설정 하려면 먼저이 하 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="70ef9-130">`SetConnectionTasks` 해당 연결과 연결 되도록 원하는 태스크 집합을 제공 하려면 다음이 하 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="70ef9-131">`EndConnection` 작업 목록 및 식별자, 이름 간의 연결을 제거 하려면 마지막으로 하 라고 합니다. 그러나 서로 다른 연결에 대 한 호출을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ef9-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70ef9-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70ef9-132">Requirements</span></span>  
 <span data-ttu-id="70ef9-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70ef9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70ef9-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70ef9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70ef9-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="70ef9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70ef9-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70ef9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ef9-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="70ef9-137">See also</span></span>

- [<span data-ttu-id="70ef9-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70ef9-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="70ef9-139">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70ef9-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="70ef9-140">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="70ef9-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="70ef9-141">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="70ef9-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="70ef9-142">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70ef9-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
