---
title: ICLRDebugManager::SetConnectionTasks 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129380"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="0ba3a-102">ICLRDebugManager::SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="0ba3a-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="0ba3a-103">[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스 목록을 식별자 및 이름과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ba3a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ba3a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ba3a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="0ba3a-106">진행 `ppCLRTask` 배열을 연결할 연결의 호스트 관련 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="0ba3a-107">진행 `ppCLRTask`의 멤버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="0ba3a-108">이 숫자는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="0ba3a-109">진행 `id`에 의해 식별 되는 연결과 연결할 `ICLRTask` 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="0ba3a-110">이 배열은 멤버를 하나 이상 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ba3a-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ba3a-111">Return Value</span></span>  
  
|<span data-ttu-id="0ba3a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ba3a-112">HRESULT</span></span>|<span data-ttu-id="0ba3a-113">설명</span><span class="sxs-lookup"><span data-stu-id="0ba3a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ba3a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ba3a-114">S_OK</span></span>|<span data-ttu-id="0ba3a-115">`SetConnectionTasks` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="0ba3a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ba3a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ba3a-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ba3a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ba3a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ba3a-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-119">The call timed out.</span></span>|  
|<span data-ttu-id="0ba3a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ba3a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ba3a-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ba3a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ba3a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ba3a-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ba3a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ba3a-124">E_FAIL</span></span>|<span data-ttu-id="0ba3a-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ba3a-126">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ba3a-127">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0ba3a-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0ba3a-128">E_INVALIDARG</span></span>|<span data-ttu-id="0ba3a-129">이 `id`값을 사용 하 여 [Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) 을 호출 하지 않았거나 `dwCount` 또는 `id` 0 이거나 `ppCLRTask`의 요소 중 하나가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ba3a-130">주의</span><span class="sxs-lookup"><span data-stu-id="0ba3a-130">Remarks</span></span>  
 <span data-ttu-id="0ba3a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 는 `BeginConnection`, `SetConnectionTasks`및 [endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)이라는 세 가지 메서드를 제공 하 여 작업 목록을 식별자와 이름에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0ba3a-132">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="0ba3a-133">`BeginConnection`를 먼저 호출 하 여 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="0ba3a-134">해당 연결과 연관 될 태스크 집합을 제공 하기 위해 다음에 `SetConnectionTasks`가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="0ba3a-135">작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 되는 `EndConnection`입니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba3a-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ba3a-136">Requirements</span></span>  
 <span data-ttu-id="0ba3a-137">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba3a-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0ba3a-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ba3a-139">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ba3a-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ba3a-140">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba3a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba3a-141">참조</span><span class="sxs-lookup"><span data-stu-id="0ba3a-141">See also</span></span>

- [<span data-ttu-id="0ba3a-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ba3a-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0ba3a-143">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ba3a-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="0ba3a-144">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="0ba3a-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="0ba3a-145">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="0ba3a-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="0ba3a-146">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ba3a-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
