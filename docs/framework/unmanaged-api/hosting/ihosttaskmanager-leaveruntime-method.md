---
title: IHostTaskManager::LeaveRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b2e8e636915b3921fcd727fc78a3fb18fc69104
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959036"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="c7851-102">IHostTaskManager::LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="c7851-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="c7851-103">현재 실행 중인 태스크가 CLR (공용 언어 런타임)을 유지 하 고 비관리 코드를 입력 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c7851-104">[IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) 에 대 한 해당 호출에서는 현재 실행 중인 작업에서 관리 코드를 현재 실행 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7851-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7851-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7851-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7851-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="c7851-107">진행 호출할 관리 되지 않는 함수의 매핑된 이식 가능한 실행 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7851-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7851-108">Return Value</span></span>  
  
|<span data-ttu-id="c7851-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7851-109">HRESULT</span></span>|<span data-ttu-id="c7851-110">Description</span><span class="sxs-lookup"><span data-stu-id="c7851-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7851-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7851-111">S_OK</span></span>|<span data-ttu-id="c7851-112">`LeaveRuntime`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="c7851-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7851-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7851-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7851-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7851-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7851-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-116">The call timed out.</span></span>|  
|<span data-ttu-id="c7851-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7851-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7851-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7851-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7851-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7851-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7851-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7851-121">E_FAIL</span></span>|<span data-ttu-id="c7851-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7851-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7851-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c7851-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c7851-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c7851-126">메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7851-127">설명</span><span class="sxs-lookup"><span data-stu-id="c7851-127">Remarks</span></span>  
 <span data-ttu-id="c7851-128">비관리 코드와의 호출 시퀀스는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="c7851-129">예를 들어 아래 `LeaveRuntime`목록에는, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)에 대 한 호출 시퀀스를 사용 하 고 `IHostTaskManager::EnterRuntime` 호스트에서 중첩 된 레이어를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="c7851-130">동작</span><span class="sxs-lookup"><span data-stu-id="c7851-130">Action</span></span>|<span data-ttu-id="c7851-131">해당 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="c7851-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="c7851-132">관리 되는 Visual Basic 실행 파일은 플랫폼 호출을 사용 하 여 C로 작성 된 관리 되지 않는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="c7851-133">관리 되지 않는 C 함수는로 C#작성 된 관리 DLL의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="c7851-134">관리 되 C# 는 함수는 C로 작성 된 다른 관리 되지 않는 함수를 호출 하 여 플랫폼 호출을 사용 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="c7851-135">두 번째 관리 되지 않는 함수는 C# 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="c7851-136">함수 C# 는 첫 번째 관리 되지 않는 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="c7851-137">첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램으로 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="c7851-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7851-138">Requirements</span></span>  
 <span data-ttu-id="c7851-139">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7851-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7851-140">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7851-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7851-141">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7851-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7851-142">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7851-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7851-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="c7851-143">See also</span></span>

- [<span data-ttu-id="c7851-144">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7851-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c7851-145">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7851-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c7851-146">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7851-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c7851-147">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7851-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
