---
title: ICLRTask::NeedsPriorityScheduling 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503e5aeeb1b59c8e62cab20736ea6ab7d5f629f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758925"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="3fee3-102">ICLRTask::NeedsPriorityScheduling 메서드</span><span class="sxs-lookup"><span data-stu-id="3fee3-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="3fee3-103">Out 전환 되 고는 현재 작업의 디스플레이 창에 대 한 우선 순위가 높은로 표시 되어야 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fee3-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fee3-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fee3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fee3-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="3fee3-106">[out] `true`호스트가 고, 그렇지 않으면 가능한 한 빨리 현재 작업 인스턴스를 다시 예약 하려고 해야 하는 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fee3-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fee3-107">Return Value</span></span>  
  
|<span data-ttu-id="3fee3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fee3-108">HRESULT</span></span>|<span data-ttu-id="3fee3-109">Description</span><span class="sxs-lookup"><span data-stu-id="3fee3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fee3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fee3-110">S_OK</span></span>|<span data-ttu-id="3fee3-111">`NeedsPriorityRescheduling` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="3fee3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fee3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fee3-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fee3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fee3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fee3-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-115">The call timed out.</span></span>|  
|<span data-ttu-id="3fee3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fee3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fee3-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fee3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fee3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fee3-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fee3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fee3-120">E_FAIL</span></span>|<span data-ttu-id="3fee3-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fee3-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fee3-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fee3-124">설명</span><span class="sxs-lookup"><span data-stu-id="3fee3-124">Remarks</span></span>  
 <span data-ttu-id="3fee3-125">CLR 가비지 수집기에서 수집 되 고 가까운 작업 인 경우의 값을 설정 `pbNeedsPriorityScheduling` 에 `true`, 우선 순위가 높은 디스플레이 창 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="3fee3-126">이 있으므로 가비지 수집의 지연 가능성을 최소화 하 고 호스트와 런타임이 메모리 리소스를 절약 상호 작용할 수 신속 하 게 작업을 다시 예약 하는 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fee3-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fee3-127">Requirements</span></span>  
 <span data-ttu-id="3fee3-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fee3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fee3-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fee3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fee3-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3fee3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fee3-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fee3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fee3-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fee3-132">See also</span></span>

- [<span data-ttu-id="3fee3-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fee3-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3fee3-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fee3-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3fee3-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fee3-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3fee3-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fee3-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
