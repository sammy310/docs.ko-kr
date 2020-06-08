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
ms.openlocfilehash: f63b761497b3e9a19a9b939b45acf60d5a7d37b0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504240"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="98d77-102">ICLRDebugManager::SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="98d77-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="98d77-103">[ICLRTask](iclrtask-interface.md) 인스턴스 목록을 식별자 및 이름과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-103">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d77-104">구문</span><span class="sxs-lookup"><span data-stu-id="98d77-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98d77-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98d77-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="98d77-106">진행 배열과 연결할 연결의 호스트 관련 식별자 `ppCLRTask` 입니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="98d77-107">진행 의 멤버 수입니다 `ppCLRTask` .</span><span class="sxs-lookup"><span data-stu-id="98d77-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="98d77-108">이 숫자는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="98d77-109">진행 `ICLRTask`로 식별 되는 연결과 연결할 포인터의 배열입니다 `id` .</span><span class="sxs-lookup"><span data-stu-id="98d77-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="98d77-110">이 배열은 멤버를 하나 이상 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98d77-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="98d77-111">Return Value</span></span>  
  
|<span data-ttu-id="98d77-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98d77-112">HRESULT</span></span>|<span data-ttu-id="98d77-113">설명</span><span class="sxs-lookup"><span data-stu-id="98d77-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98d77-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="98d77-114">S_OK</span></span>|<span data-ttu-id="98d77-115">`SetConnectionTasks`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="98d77-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98d77-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98d77-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98d77-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98d77-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98d77-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-119">The call timed out.</span></span>|  
|<span data-ttu-id="98d77-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98d77-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98d77-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98d77-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98d77-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98d77-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98d77-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98d77-124">E_FAIL</span></span>|<span data-ttu-id="98d77-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98d77-126">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98d77-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="98d77-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="98d77-128">E_INVALIDARG</span></span>|<span data-ttu-id="98d77-129">[Beginconnection](iclrdebugmanager-beginconnection-method.md) 이이 값을 사용 하 여 호출 되지 않았거나 `id` `dwCount` 또는 `id` 가 0 이거나의 요소 중 하나가 `ppCLRTask` null입니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-129">[BeginConnection](iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98d77-130">설명</span><span class="sxs-lookup"><span data-stu-id="98d77-130">Remarks</span></span>  
 <span data-ttu-id="98d77-131">[ICLRDebugManager](iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드,, `BeginConnection` `SetConnectionTasks` 및 [endconnection](iclrdebugmanager-endconnection-method.md)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-131">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="98d77-132">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="98d77-133">`BeginConnection`새 연결을 설정 하기 위해가 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="98d77-134">`SetConnectionTasks`는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="98d77-135">`EndConnection`작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98d77-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98d77-136">Requirements</span></span>  
 <span data-ttu-id="98d77-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98d77-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d77-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="98d77-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98d77-139">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d77-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98d77-140">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d77-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d77-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98d77-141">See also</span></span>

- [<span data-ttu-id="98d77-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98d77-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="98d77-143">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98d77-143">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="98d77-144">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="98d77-144">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="98d77-145">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="98d77-145">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="98d77-146">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98d77-146">IHostControl Interface</span></span>](ihostcontrol-interface.md)
