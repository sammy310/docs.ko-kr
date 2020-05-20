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
ms.openlocfilehash: f524cadf77caec0823411784c68f339207433601
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615792"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="ed89d-102">ICLRDebugManager::EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="ed89d-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="ed89d-103">작업 목록과 식별자 및 이름 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed89d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed89d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed89d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed89d-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="ed89d-106">진행 연결에 대 한 호스트 관련 식별자와 관련 된 CLR (공용 언어 런타임) 작업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed89d-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="ed89d-107">Return Value</span></span>  
  
|<span data-ttu-id="ed89d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed89d-108">HRESULT</span></span>|<span data-ttu-id="ed89d-109">설명</span><span class="sxs-lookup"><span data-stu-id="ed89d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed89d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed89d-110">S_OK</span></span>|<span data-ttu-id="ed89d-111">`EndConnection`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="ed89d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed89d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed89d-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed89d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed89d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed89d-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-115">The call timed out.</span></span>|  
|<span data-ttu-id="ed89d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed89d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed89d-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed89d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed89d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed89d-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed89d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed89d-120">E_FAIL</span></span>|<span data-ttu-id="ed89d-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed89d-122">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed89d-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed89d-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ed89d-124">E_INVALIDARG</span></span>|<span data-ttu-id="ed89d-125">[Beginconnection](iclrdebugmanager-beginconnection-method.md) 이를 사용 하 여 호출 되지 `dwConnectionId` 않았거나 `dwConnectionId` 가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed89d-126">설명</span><span class="sxs-lookup"><span data-stu-id="ed89d-126">Remarks</span></span>  
 <span data-ttu-id="ed89d-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드인, `BeginConnection` [setconnectiontasks](iclrdebugmanager-setconnectiontasks-method.md)및 `EndConnection` 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ed89d-128">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="ed89d-129">`BeginConnection`새 연결을 설정 하기 위해가 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="ed89d-130">`SetConnectionTasks`는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="ed89d-131">`EndConnection`작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed89d-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed89d-132">Requirements</span></span>  
 <span data-ttu-id="ed89d-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed89d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed89d-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ed89d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed89d-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed89d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed89d-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed89d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed89d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed89d-137">See also</span></span>

- [<span data-ttu-id="ed89d-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed89d-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ed89d-139">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed89d-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="ed89d-140">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="ed89d-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="ed89d-141">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="ed89d-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="ed89d-142">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed89d-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
