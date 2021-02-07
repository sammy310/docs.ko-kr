---
description: '자세히 알아보기: ICLRDebugManager:: BeginConnection 메서드'
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
ms.openlocfilehash: 9b4ee64ad96bddfd5d7d650b657c6691b27d8c69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746141"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="bfdf9-103">ICLRDebugManager::BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="bfdf9-103">ICLRDebugManager::BeginConnection Method</span></span>

<span data-ttu-id="bfdf9-104">작업 목록과 식별자를 연결 하기 위해 호스트와 디버거 간에 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-104">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfdf9-105">구문</span><span class="sxs-lookup"><span data-stu-id="bfdf9-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfdf9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfdf9-106">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="bfdf9-107">진행 CLR (공용 언어 런타임) 작업 목록과 연결할 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-107">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="bfdf9-108">진행 CLR 작업 목록과 연결할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-108">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfdf9-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="bfdf9-109">Return Value</span></span>  
  
|<span data-ttu-id="bfdf9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfdf9-110">HRESULT</span></span>|<span data-ttu-id="bfdf9-111">설명</span><span class="sxs-lookup"><span data-stu-id="bfdf9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfdf9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfdf9-112">S_OK</span></span>|<span data-ttu-id="bfdf9-113">`BeginConnection` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-113">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="bfdf9-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfdf9-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfdf9-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfdf9-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfdf9-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfdf9-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-117">The call timed out.</span></span>|  
|<span data-ttu-id="bfdf9-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfdf9-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfdf9-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfdf9-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfdf9-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfdf9-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfdf9-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfdf9-122">E_FAIL</span></span>|<span data-ttu-id="bfdf9-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bfdf9-124">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfdf9-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bfdf9-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bfdf9-126">E_INVALIDARG</span></span>|<span data-ttu-id="bfdf9-127">`dwConnectionId` 가 0 이거나 `BeginConnection` 이 값을 사용 하 여 이미 호출 `dwConnectionId` 되었거나 `szConnectionName` 가 null 인 경우</span><span class="sxs-lookup"><span data-stu-id="bfdf9-127">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="bfdf9-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bfdf9-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bfdf9-129">메모리가 부족 하 여이 연결과 관련 된 작업 목록을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-129">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfdf9-130">설명</span><span class="sxs-lookup"><span data-stu-id="bfdf9-130">Remarks</span></span>  

 <span data-ttu-id="bfdf9-131">[ICLRDebugManager](iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드인 `BeginConnection` , [Setconnectiontasks](iclrdebugmanager-setconnectiontasks-method.md)및 [endconnection](iclrdebugmanager-endconnection-method.md)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-131">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bfdf9-132">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="bfdf9-133">`BeginConnection` 새 연결을 설정 하기 위해가 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="bfdf9-134">`SetConnectionTasks` 는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="bfdf9-135">`EndConnection` 작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfdf9-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfdf9-136">Requirements</span></span>  

 <span data-ttu-id="bfdf9-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfdf9-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bfdf9-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfdf9-139">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfdf9-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfdf9-140">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfdf9-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfdf9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfdf9-141">See also</span></span>

- [<span data-ttu-id="bfdf9-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfdf9-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="bfdf9-143">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfdf9-143">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="bfdf9-144">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="bfdf9-144">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="bfdf9-145">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="bfdf9-145">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="bfdf9-146">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfdf9-146">IHostControl Interface</span></span>](ihostcontrol-interface.md)
