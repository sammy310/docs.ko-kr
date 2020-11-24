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
ms.openlocfilehash: 86e0899b883f09f2e7b27c0f957e943deb73bb66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690800"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="af775-102">ICLRTask::NeedsPriorityScheduling 메서드</span><span class="sxs-lookup"><span data-stu-id="af775-102">ICLRTask::NeedsPriorityScheduling Method</span></span>

<span data-ttu-id="af775-103">전환 중인 현재 작업을 다시 예약 하기 위해 높은 우선 순위로 표시 해야 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af775-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af775-104">구문</span><span class="sxs-lookup"><span data-stu-id="af775-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af775-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af775-105">Parameters</span></span>  

 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="af775-106">[out] `true` 호스트에서 가능한 한 빨리 현재 작업 인스턴스를 다시 예약 하려고 하면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="af775-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af775-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="af775-107">Return Value</span></span>  
  
|<span data-ttu-id="af775-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af775-108">HRESULT</span></span>|<span data-ttu-id="af775-109">설명</span><span class="sxs-lookup"><span data-stu-id="af775-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af775-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="af775-110">S_OK</span></span>|<span data-ttu-id="af775-111">`NeedsPriorityRescheduling` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="af775-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af775-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af775-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af775-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af775-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af775-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-115">The call timed out.</span></span>|  
|<span data-ttu-id="af775-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af775-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af775-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af775-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af775-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af775-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af775-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af775-120">E_FAIL</span></span>|<span data-ttu-id="af775-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af775-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af775-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af775-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af775-124">설명</span><span class="sxs-lookup"><span data-stu-id="af775-124">Remarks</span></span>  

 <span data-ttu-id="af775-125">태스크가 가비지 수집기에 의해 수집 되는 것에 근접 한 경우 CLR은의 값을로 설정 하 `pbNeedsPriorityScheduling` 여 `true` 높은 우선 순위 조정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af775-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="af775-126">이렇게 하면 호스트가 작업을 신속 하 게 다시 예약 하 여 가비지 수집의 지연 가능성을 최소화 하 고 호스트 및 런타임이 메모리 리소스를 절약 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af775-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af775-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af775-127">Requirements</span></span>  

 <span data-ttu-id="af775-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af775-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af775-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="af775-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af775-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af775-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af775-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af775-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af775-132">참조</span><span class="sxs-lookup"><span data-stu-id="af775-132">See also</span></span>

- [<span data-ttu-id="af775-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af775-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="af775-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af775-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="af775-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af775-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="af775-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af775-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
