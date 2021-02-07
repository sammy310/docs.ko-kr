---
description: '자세히 알아보기: IHostTaskManager 인터페이스'
title: IHostTaskManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 67574550ba26970189ea53b8e6bdb867fea8549b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707483"
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="39c59-103">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c59-103">IHostTaskManager Interface</span></span>

<span data-ttu-id="39c59-104">표준 운영 체제 스레딩 또는 파이버 함수를 사용 하는 대신 CLR (공용 언어 런타임)이 호스트를 통해 작업을 수행할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-104">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39c59-105">메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-105">Methods</span></span>  
  
|<span data-ttu-id="39c59-106">메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-106">Method</span></span>|<span data-ttu-id="39c59-107">설명</span><span class="sxs-lookup"><span data-stu-id="39c59-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39c59-108">BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-108">BeginDelayAbort Method</span></span>](ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="39c59-109">관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 입력 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-109">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="39c59-110">BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-110">BeginThreadAffinity Method</span></span>](ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="39c59-111">관리 코드에서 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간이 입력 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-111">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="39c59-112">CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-112">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="39c59-113">호스트에서 공용 언어 런타임이 관리 되지 않는 함수에 대 한 지정 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-113">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="39c59-114">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-114">CreateTask Method</span></span>](ihosttaskmanager-createtask-method.md)|<span data-ttu-id="39c59-115">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-115">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="39c59-116">EndDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-116">EndDelayAbort Method</span></span>](ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="39c59-117">에 대 한 이전 호출에 따라 관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 종료 하 고 있음을 호스트에 알립니다 `BeginDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="39c59-117">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="39c59-118">EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-118">EndThreadAffinity Method</span></span>](ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="39c59-119">이전에를 호출 하 여 관리 코드가 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간을 호스트에 알립니다 `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="39c59-119">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="39c59-120">EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-120">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="39c59-121">플랫폼 호출 메서드와 같은 관리 되지 않는 메서드에 대 한 호출이 CLR에 실행 제어를 반환 한다는 것을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-121">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="39c59-122">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-122">GetCurrentTask Method</span></span>](ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="39c59-123">이 호출이 수행 되는 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-123">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="39c59-124">GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-124">GetStackGuarantee Method</span></span>](ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="39c59-125">스택 작업이 완료 된 후 프로세스가 종료 되기 전에 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-125">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="39c59-126">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-126">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="39c59-127">관리 코드에서 관리 되지 않는 함수에 대 한 호출을 수행 하려고 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-127">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="39c59-128">ReverseEnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-128">ReverseEnterRuntime Method</span></span>](ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="39c59-129">비관리 코드에서 CLR (공용 언어 런타임)에 대 한 호출이 수행 되 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-129">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="39c59-130">ReverseLeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-130">ReverseLeaveRuntime Method</span></span>](ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="39c59-131">관리 코드에서 호출 된 관리 되지 않는 함수를 제어 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-131">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="39c59-132">SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-132">SetCLRTaskManager Method</span></span>](ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="39c59-133">호스트에 CLR에서 구현 하는 [ICLRTaskManager](iclrtaskmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-133">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="39c59-134">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-134">SetLocale Method</span></span>](ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="39c59-135">CLR이 현재 작업에 대 한 로캘을 변경 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-135">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="39c59-136">SetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-136">SetStackGuarantee Method</span></span>](ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="39c59-137">이 속성은 내부 전용으로 예약되어 있으므로</span><span class="sxs-lookup"><span data-stu-id="39c59-137">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="39c59-138">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-138">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="39c59-139">현재 작업에서 사용자 인터페이스 로캘이 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-139">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="39c59-140">Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-140">Sleep Method</span></span>](ihosttaskmanager-sleep-method.md)|<span data-ttu-id="39c59-141">현재 태스크가 절전 모드로 전환 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-141">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="39c59-142">SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="39c59-142">SwitchToTask Method</span></span>](ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="39c59-143">현재 작업을 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-143">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c59-144">설명</span><span class="sxs-lookup"><span data-stu-id="39c59-144">Remarks</span></span>  

 <span data-ttu-id="39c59-145">`IHostTaskManager` CLR에서 작업을 생성 및 관리 하 고, 관리 코드에서 비관리 코드로의 제어가 전송 될 때 호스트에 대 한 후크를 제공 하 고, 해당 호스트에서 코드 실행 중에 수행할 수 있는 특정 작업을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-145">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c59-146">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39c59-146">Requirements</span></span>  

 <span data-ttu-id="39c59-147">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39c59-147">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c59-148">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39c59-148">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39c59-149">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c59-149">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39c59-150">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c59-150">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c59-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39c59-151">See also</span></span>

- [<span data-ttu-id="39c59-152">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c59-152">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="39c59-153">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c59-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="39c59-154">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c59-154">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="39c59-155">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c59-155">Hosting Interfaces</span></span>](hosting-interfaces.md)
