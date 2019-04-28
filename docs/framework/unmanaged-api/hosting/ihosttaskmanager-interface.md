---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30e75bf4a58e66bb0dd8210368b162cf14c3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936476"
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="ca890-102">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca890-102">IHostTaskManager Interface</span></span>
<span data-ttu-id="ca890-103">CLR (공용 언어 런타임)에서 표준 운영 체제 스레드 또는 파이버 함수를 사용 하는 대신 호스트를 통해 작업을 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca890-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-104">Methods</span></span>  
  
|<span data-ttu-id="ca890-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-105">Method</span></span>|<span data-ttu-id="ca890-106">설명</span><span class="sxs-lookup"><span data-stu-id="ca890-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca890-107">BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-107">BeginDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="ca890-108">관리 코드는 호스트는 현재 작업 중단할 수 없는 기간이 시작 됨을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="ca890-109">BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-109">BeginThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="ca890-110">현재 작업 이동 하지 말아야 다른 운영 체제 스레드로 마침표를 입력 하는 관리 코드는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="ca890-111">CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-111">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="ca890-112">호스트를에서 공용 언어 런타임에서 관리 되지 않는 함수에 지정된 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="ca890-113">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-113">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|<span data-ttu-id="ca890-114">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="ca890-115">EndDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-115">EndDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="ca890-116">관리 코드는 호스트가 종료는 현재 작업을 중단 하지 말아야, 기간에 대 한 이전 호출을 다음 알립니다 `BeginDelayAbort`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="ca890-117">EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-117">EndThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="ca890-118">관리 코드는 호스트는 기간이 종료 됨는 현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 대 한 이전 호출 다음에 알립니다. `BeginThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="ca890-119">EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-119">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="ca890-120">관리 되지 않는 메서드를 호출 하는 플랫폼 호출 메서드를 같은 반환 되는지 실행 제어 clr 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="ca890-121">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-121">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="ca890-122">이 호출이 수행 된 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="ca890-123">GetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-123">GetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="ca890-124">프로세스의 닫기 전에 있지만 스택 작업이 완료 되 면 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="ca890-125">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-125">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="ca890-126">관리 코드는 호스트를 관리 되지 않는 함수를 호출 하려고에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="ca890-127">ReverseEnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-127">ReverseEnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="ca890-128">비관리 코드에서 공용 언어 런타임 (CLR)에 호출이 수행 되는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="ca890-129">ReverseLeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-129">ReverseLeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="ca890-130">컨트롤의 입력을 차례로 호출 된 관리 코드에서 관리 되지 않는 함수를 clr에서 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="ca890-131">SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-131">SetCLRTaskManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="ca890-132">호스트에 대 한 인터페이스 포인터에 제공을 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 인스턴스는 CLR에서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-132">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="ca890-133">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-133">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="ca890-134">CLR이 현재 작업에서 로캘을 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="ca890-135">SetStackGuarantee 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-135">SetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="ca890-136">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="ca890-137">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-137">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="ca890-138">현재 작업에서 사용자 인터페이스 로캘을 변경 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="ca890-139">Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-139">Sleep Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|<span data-ttu-id="ca890-140">현재 태스크 절전 모드로 전환 됨 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="ca890-141">SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="ca890-141">SwitchToTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="ca890-142">현재 작업 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca890-143">설명</span><span class="sxs-lookup"><span data-stu-id="ca890-143">Remarks</span></span>  
 <span data-ttu-id="ca890-144">`IHostTaskManager` CLR 작업, 만들기 및 관리에 후크 그 반대의 경우와 비관리 코드를 관리 되는 컨트롤에서 전송 하는 경우 작업을 수행 하 고 특정 작업을 지정할 수는 호스트를 제공 하 호스트 수 있으며 코드 실행 하는 동안 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca890-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca890-145">Requirements</span></span>  
 <span data-ttu-id="ca890-146">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca890-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca890-147">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca890-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca890-148">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ca890-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca890-149">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca890-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca890-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="ca890-150">See also</span></span>

- [<span data-ttu-id="ca890-151">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca890-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ca890-152">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca890-152">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ca890-153">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca890-153">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ca890-154">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca890-154">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
