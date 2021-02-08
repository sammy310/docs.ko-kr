---
description: '자세한 정보: IHostTask:: SetPriority 메서드'
title: IHostTask::SetPriority 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
ms.openlocfilehash: c3e8fee954e5cbea2d084141a4b2d22d2fa5e95b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784641"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="16329-103">IHostTask::SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="16329-103">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="16329-104">호스트가 현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 되는 작업에 대 한 스레드 우선 순위 수준을 조정 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="16329-104">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16329-105">구문</span><span class="sxs-lookup"><span data-stu-id="16329-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16329-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16329-106">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="16329-107">진행 현재 인스턴스에서 나타내는 작업의 요청 된 스레드 우선 순위 값을 나타내는 정수입니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="16329-107">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16329-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="16329-108">Return Value</span></span>  
  
|<span data-ttu-id="16329-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16329-109">HRESULT</span></span>|<span data-ttu-id="16329-110">설명</span><span class="sxs-lookup"><span data-stu-id="16329-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16329-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="16329-111">S_OK</span></span>|<span data-ttu-id="16329-112">`SetPriority` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-112">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="16329-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16329-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16329-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16329-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16329-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16329-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-116">The call timed out.</span></span>|  
|<span data-ttu-id="16329-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16329-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16329-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16329-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16329-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16329-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16329-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16329-121">E_FAIL</span></span>|<span data-ttu-id="16329-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16329-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16329-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16329-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16329-125">설명</span><span class="sxs-lookup"><span data-stu-id="16329-125">Remarks</span></span>  

 <span data-ttu-id="16329-126">스레드에는 스레드 우선 순위 수준에 따라 부분적으로 사용 되는 라운드 로빈 시스템을 사용 하 여 처리 시간이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16329-126">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="16329-127">`SetPriority` CLR에서 현재 태스크에 대 한 스레드 우선 순위 수준을 설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="16329-127">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="16329-128">`newPriority`지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-128">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="16329-129">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="16329-129">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="16329-130">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="16329-130">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="16329-131">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="16329-131">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="16329-132">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="16329-132">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="16329-133">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="16329-133">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="16329-134">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="16329-134">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="16329-135">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="16329-135">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="16329-136">CLR은 `SetPriority` <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> 사용자 코드에 의해 값이 수정 될 때를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="16329-136">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="16329-137">호스트는 스레드 우선 순위 할당에 대 한 자체 알고리즘을 정의할 수 있으며이 요청을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-137">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16329-138">`SetPriority` 는 스레드 우선 순위 수준이 변경 되었는지 여부를 보고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16329-138">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="16329-139">작업의 스레드 우선 순위 수준 값을 확인 하려면 [IHostTask:: GetPriority](ihosttask-getpriority-method.md) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="16329-139">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="16329-140">스레드 우선 순위 수준 값은 Win32 함수에 의해 정의 됩니다 `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="16329-140">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="16329-141">스레드 우선 순위에 대 한 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="16329-141">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16329-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16329-142">Requirements</span></span>  

 <span data-ttu-id="16329-143">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16329-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16329-144">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16329-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16329-145">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16329-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16329-146">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16329-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16329-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16329-147">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="16329-148">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16329-148">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="16329-149">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16329-149">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="16329-150">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16329-150">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="16329-151">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="16329-151">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="16329-152">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16329-152">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
