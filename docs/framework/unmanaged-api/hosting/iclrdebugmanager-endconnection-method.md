---
description: '자세히 알아보기: ICLRDebugManager:: EndConnection 메서드'
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
ms.openlocfilehash: 06dc9e20ec02c3e3040090babcc443a2ae59848b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746054"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="f14e2-103">ICLRDebugManager::EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="f14e2-103">ICLRDebugManager::EndConnection Method</span></span>

<span data-ttu-id="f14e2-104">작업 목록과 식별자 및 이름 간의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-104">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14e2-105">구문</span><span class="sxs-lookup"><span data-stu-id="f14e2-105">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f14e2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f14e2-106">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="f14e2-107">진행 연결에 대 한 호스트 관련 식별자와 관련 된 CLR (공용 언어 런타임) 작업 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-107">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f14e2-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="f14e2-108">Return Value</span></span>  
  
|<span data-ttu-id="f14e2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f14e2-109">HRESULT</span></span>|<span data-ttu-id="f14e2-110">설명</span><span class="sxs-lookup"><span data-stu-id="f14e2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f14e2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f14e2-111">S_OK</span></span>|<span data-ttu-id="f14e2-112">`EndConnection` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-112">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="f14e2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f14e2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f14e2-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f14e2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f14e2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f14e2-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-116">The call timed out.</span></span>|  
|<span data-ttu-id="f14e2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f14e2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f14e2-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f14e2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f14e2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f14e2-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f14e2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f14e2-121">E_FAIL</span></span>|<span data-ttu-id="f14e2-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f14e2-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f14e2-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f14e2-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f14e2-125">E_INVALIDARG</span></span>|<span data-ttu-id="f14e2-126">[Beginconnection](iclrdebugmanager-beginconnection-method.md) 이를 사용 하 여 호출 되지 `dwConnectionId` 않았거나 `dwConnectionId` 가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-126">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f14e2-127">설명</span><span class="sxs-lookup"><span data-stu-id="f14e2-127">Remarks</span></span>  

 <span data-ttu-id="f14e2-128">[ICLRDebugManager](iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드인, `BeginConnection` [setconnectiontasks](iclrdebugmanager-setconnectiontasks-method.md)및 `EndConnection` 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-128">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f14e2-129">이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-129">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="f14e2-130">`BeginConnection` 새 연결을 설정 하기 위해가 먼저 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-130">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="f14e2-131">`SetConnectionTasks` 는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-131">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="f14e2-132">`EndConnection` 작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-132">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14e2-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f14e2-133">Requirements</span></span>  

 <span data-ttu-id="f14e2-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f14e2-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14e2-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f14e2-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f14e2-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14e2-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f14e2-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14e2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14e2-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f14e2-138">See also</span></span>

- [<span data-ttu-id="f14e2-139">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f14e2-139">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f14e2-140">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f14e2-140">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="f14e2-141">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="f14e2-141">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="f14e2-142">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="f14e2-142">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="f14e2-143">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f14e2-143">IHostControl Interface</span></span>](ihostcontrol-interface.md)
