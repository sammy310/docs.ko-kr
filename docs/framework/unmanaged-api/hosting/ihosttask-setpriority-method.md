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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05960eac85140a1539877eccf2d0ccdf053e76b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64657926"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="80bfb-102">IHostTask::SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="80bfb-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="80bfb-103">현재 태스크에 대 한 호스트에서 스레드 우선 순위를 조정 하도록 요청 수준 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="80bfb-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80bfb-104">구문</span><span class="sxs-lookup"><span data-stu-id="80bfb-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80bfb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="80bfb-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="80bfb-106">[in] 현재 태스크에 대 한 요청 된 스레드 우선 순위 값을 나타내는 정수 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="80bfb-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80bfb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="80bfb-107">Return Value</span></span>  
  
|<span data-ttu-id="80bfb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80bfb-108">HRESULT</span></span>|<span data-ttu-id="80bfb-109">설명</span><span class="sxs-lookup"><span data-stu-id="80bfb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80bfb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="80bfb-110">S_OK</span></span>|<span data-ttu-id="80bfb-111">`SetPriority` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="80bfb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80bfb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80bfb-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80bfb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80bfb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80bfb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-115">The call timed out.</span></span>|  
|<span data-ttu-id="80bfb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80bfb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80bfb-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80bfb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80bfb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80bfb-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80bfb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80bfb-120">E_FAIL</span></span>|<span data-ttu-id="80bfb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80bfb-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80bfb-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80bfb-124">설명</span><span class="sxs-lookup"><span data-stu-id="80bfb-124">Remarks</span></span>  
 <span data-ttu-id="80bfb-125">스레드는 스레드 우선 순위 수준에 따라 부분적으로 라운드 로빈 시스템을 사용 하는 시간을 처리 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="80bfb-126">`SetPriority` CLR에서를 현재 작업에 대 한 스레드 우선 순위 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="80bfb-127">다음 `newPriority` 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="80bfb-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="80bfb-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="80bfb-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="80bfb-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="80bfb-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="80bfb-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="80bfb-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="80bfb-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="80bfb-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="80bfb-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="80bfb-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="80bfb-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="80bfb-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="80bfb-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="80bfb-135">CLR 호출 `SetPriority` 때 변수의 <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> 사용자 코드에서 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="80bfb-136">호스트는 자체 스레드 우선 순위 할당 알고리즘을 정의할 수 있으며이 요청을 무시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80bfb-137">`SetPriority` 스레드 우선 순위 수준을 변경 되었는지 여부를 보고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="80bfb-138">호출 [ihosttask:: Getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) 태스크의 스레드 우선 순위 수준의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="80bfb-139">Win32 스레드 우선 순위 수준 값이 정의 된 `SetThreadPriority` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="80bfb-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="80bfb-140">스레드 우선 순위에 대 한 자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80bfb-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80bfb-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80bfb-141">Requirements</span></span>  
 <span data-ttu-id="80bfb-142">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="80bfb-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80bfb-143">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80bfb-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80bfb-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="80bfb-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80bfb-145">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80bfb-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bfb-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="80bfb-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="80bfb-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80bfb-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="80bfb-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80bfb-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="80bfb-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80bfb-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="80bfb-150">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="80bfb-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="80bfb-151">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80bfb-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
