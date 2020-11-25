---
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
ms.openlocfilehash: 80b4bb2f6a547250acbc16a89e7396c60cc50d87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720453"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="db251-102">IHostTask::SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="db251-102">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="db251-103">호스트가 현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 되는 작업에 대 한 스레드 우선 순위 수준을 조정 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="db251-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db251-104">구문</span><span class="sxs-lookup"><span data-stu-id="db251-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db251-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db251-105">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="db251-106">진행 현재 인스턴스에서 나타내는 작업의 요청 된 스레드 우선 순위 값을 나타내는 정수입니다 `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="db251-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db251-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="db251-107">Return Value</span></span>  
  
|<span data-ttu-id="db251-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db251-108">HRESULT</span></span>|<span data-ttu-id="db251-109">설명</span><span class="sxs-lookup"><span data-stu-id="db251-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db251-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="db251-110">S_OK</span></span>|<span data-ttu-id="db251-111">`SetPriority` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="db251-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db251-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db251-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db251-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db251-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db251-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-115">The call timed out.</span></span>|  
|<span data-ttu-id="db251-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db251-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db251-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db251-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db251-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db251-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db251-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db251-120">E_FAIL</span></span>|<span data-ttu-id="db251-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db251-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db251-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db251-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db251-124">설명</span><span class="sxs-lookup"><span data-stu-id="db251-124">Remarks</span></span>  

 <span data-ttu-id="db251-125">스레드에는 스레드 우선 순위 수준에 따라 부분적으로 사용 되는 라운드 로빈 시스템을 사용 하 여 처리 시간이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db251-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="db251-126">`SetPriority` CLR에서 현재 태스크에 대 한 스레드 우선 순위 수준을 설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="db251-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="db251-127">`newPriority`지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="db251-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="db251-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="db251-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="db251-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="db251-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="db251-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="db251-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="db251-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="db251-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="db251-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="db251-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="db251-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="db251-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="db251-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="db251-135">CLR은 `SetPriority` <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> 사용자 코드에 의해 값이 수정 될 때를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="db251-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="db251-136">호스트는 스레드 우선 순위 할당에 대 한 자체 알고리즘을 정의할 수 있으며이 요청을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db251-137">`SetPriority` 는 스레드 우선 순위 수준이 변경 되었는지 여부를 보고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db251-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="db251-138">작업의 스레드 우선 순위 수준 값을 확인 하려면 [IHostTask:: GetPriority](ihosttask-getpriority-method.md) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="db251-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="db251-139">스레드 우선 순위 수준 값은 Win32 함수에 의해 정의 됩니다 `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="db251-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="db251-140">스레드 우선 순위에 대 한 자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db251-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db251-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db251-141">Requirements</span></span>  

 <span data-ttu-id="db251-142">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db251-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db251-143">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="db251-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db251-144">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db251-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db251-145">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db251-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db251-146">참조</span><span class="sxs-lookup"><span data-stu-id="db251-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="db251-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db251-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="db251-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db251-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="db251-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db251-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="db251-150">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="db251-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="db251-151">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db251-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
