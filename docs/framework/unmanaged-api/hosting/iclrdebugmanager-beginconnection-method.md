---
title: ICLRDebugManager::BeginConnection 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
ms.openlocfilehash: 2ac2b0dde97b883313e1bca17c5e99855484e4aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126570"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="b73c3-102">ICLRDebugManager::BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="b73c3-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="b73c3-103">작업 목록과 식별자를 연결 하기 위해 호스트와 디버거 간에 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b73c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="b73c3-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b73c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b73c3-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="b73c3-106">진행 CLR (공용 언어 런타임) 작업 목록과 연결할 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="b73c3-107">진행 CLR 작업 목록과 연결할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b73c3-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b73c3-108">Return Value</span></span>  
  
|<span data-ttu-id="b73c3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b73c3-109">HRESULT</span></span>|<span data-ttu-id="b73c3-110">설명</span><span class="sxs-lookup"><span data-stu-id="b73c3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b73c3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b73c3-111">S_OK</span></span>|<span data-ttu-id="b73c3-112">`BeginConnection` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="b73c3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b73c3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b73c3-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b73c3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b73c3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b73c3-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-116">The call timed out.</span></span>|  
|<span data-ttu-id="b73c3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b73c3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b73c3-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b73c3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b73c3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b73c3-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b73c3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b73c3-121">E_FAIL</span></span>|<span data-ttu-id="b73c3-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b73c3-123">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b73c3-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b73c3-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b73c3-125">E_INVALIDARG</span></span>|<span data-ttu-id="b73c3-126">`dwConnectionId` 0 이거나 `BeginConnection`이 `dwConnectionId` 값을 사용 하 여 이미 호출 되었거나 `szConnectionName` null입니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="b73c3-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b73c3-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b73c3-128">메모리가 부족 하 여이 연결과 관련 된 작업 목록을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b73c3-129">주의</span><span class="sxs-lookup"><span data-stu-id="b73c3-129">Remarks</span></span>  
 <span data-ttu-id="b73c3-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드인 `BeginConnection`, [Setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)및 [endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b73c3-131">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="b73c3-132">`BeginConnection`를 먼저 호출 하 여 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="b73c3-133">해당 연결과 연관 될 태스크 집합을 제공 하기 위해 다음에 `SetConnectionTasks`가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="b73c3-134">작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 되는 `EndConnection`입니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b73c3-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b73c3-135">Requirements</span></span>  
 <span data-ttu-id="b73c3-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b73c3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b73c3-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b73c3-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b73c3-138">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73c3-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b73c3-139">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b73c3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73c3-140">참조</span><span class="sxs-lookup"><span data-stu-id="b73c3-140">See also</span></span>

- [<span data-ttu-id="b73c3-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b73c3-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b73c3-142">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b73c3-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="b73c3-143">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="b73c3-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="b73c3-144">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="b73c3-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="b73c3-145">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b73c3-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
