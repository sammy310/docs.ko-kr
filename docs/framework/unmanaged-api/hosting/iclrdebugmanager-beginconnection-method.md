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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970016"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="cc283-102">ICLRDebugManager::BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="cc283-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="cc283-103">식별자 및 이름을 사용 하 여 작업 목록을 연결 하려면 호스트와 디버거 간의 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc283-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc283-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc283-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc283-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="cc283-106">[in] 공용 언어 런타임 (CLR) 작업 목록을 사용 하 여 연결 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="cc283-107">[in] CLR 태스크 목록을 연결할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc283-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="cc283-108">Return Value</span></span>  
  
|<span data-ttu-id="cc283-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc283-109">HRESULT</span></span>|<span data-ttu-id="cc283-110">설명</span><span class="sxs-lookup"><span data-stu-id="cc283-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc283-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc283-111">S_OK</span></span>|<span data-ttu-id="cc283-112">`BeginConnection` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="cc283-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc283-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc283-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc283-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc283-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc283-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-116">The call timed out.</span></span>|  
|<span data-ttu-id="cc283-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc283-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc283-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc283-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc283-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc283-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc283-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc283-121">E_FAIL</span></span>|<span data-ttu-id="cc283-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc283-123">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc283-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cc283-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cc283-125">E_INVALIDARG</span></span>|<span data-ttu-id="cc283-126">`dwConnectionId` 0 또는 `BeginConnection` 이 사용 하 여 이미 호출 된 `dwConnectionId` 값 또는 `szConnectionName` null입니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="cc283-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cc283-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cc283-128">메모리가 부족이 연결과 관련 된 작업 목록을 유지에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc283-129">설명</span><span class="sxs-lookup"><span data-stu-id="cc283-129">Remarks</span></span>  
 <span data-ttu-id="cc283-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 세 가지 방법을 제공 `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), 및 [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), 식별자 및 이름을 사용 하 여 작업 목록을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc283-131">이러한 세 가지 메서드는 작업의 각 집합에 대 한 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="cc283-132">`BeginConnection` 새 연결을 설정 하려면 먼저이 하 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="cc283-133">`SetConnectionTasks` 해당 연결과 연결 되도록 원하는 태스크 집합을 제공 하려면 다음이 하 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="cc283-134">`EndConnection` 작업 목록 및 식별자, 이름 간의 연결을 제거 하려면 마지막으로 하 라고 합니다. 그러나 서로 다른 연결에 대 한 호출을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc283-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc283-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc283-135">Requirements</span></span>  
 <span data-ttu-id="cc283-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc283-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc283-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cc283-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc283-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cc283-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc283-139">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc283-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc283-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="cc283-140">See also</span></span>

- [<span data-ttu-id="cc283-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc283-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cc283-142">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc283-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="cc283-143">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="cc283-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="cc283-144">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="cc283-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="cc283-145">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc283-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
