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
ms.openlocfilehash: 8ac1c18d094deca50d461ef9ff0933a4f87176e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132988"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="7d360-102">IHostTaskManager::LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="7d360-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="7d360-103">현재 실행 중인 태스크가 CLR (공용 언어 런타임)을 유지 하 고 비관리 코드를 입력 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d360-104">[IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) 에 대 한 해당 호출에서는 현재 실행 중인 작업에서 관리 코드를 현재 실행 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d360-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d360-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d360-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d360-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="7d360-107">진행 호출할 관리 되지 않는 함수의 매핑된 이식 가능한 실행 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d360-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d360-108">Return Value</span></span>  
  
|<span data-ttu-id="7d360-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d360-109">HRESULT</span></span>|<span data-ttu-id="7d360-110">설명</span><span class="sxs-lookup"><span data-stu-id="7d360-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d360-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d360-111">S_OK</span></span>|<span data-ttu-id="7d360-112">`LeaveRuntime` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7d360-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d360-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d360-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d360-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d360-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d360-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-116">The call timed out.</span></span>|  
|<span data-ttu-id="7d360-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d360-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d360-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d360-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d360-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d360-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d360-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d360-121">E_FAIL</span></span>|<span data-ttu-id="7d360-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d360-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d360-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d360-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7d360-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7d360-126">메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d360-127">주의</span><span class="sxs-lookup"><span data-stu-id="7d360-127">Remarks</span></span>  
 <span data-ttu-id="7d360-128">비관리 코드와의 호출 시퀀스는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="7d360-129">예를 들어, 아래 목록에서는 `LeaveRuntime`에 대 한 호출 시퀀스, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)및 `IHostTaskManager::EnterRuntime`를 사용 하 여 호스트에서 중첩 계층.</span><span class="sxs-lookup"><span data-stu-id="7d360-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="7d360-130">작업</span><span class="sxs-lookup"><span data-stu-id="7d360-130">Action</span></span>|<span data-ttu-id="7d360-131">해당 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="7d360-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="7d360-132">관리 되는 Visual Basic 실행 파일은 플랫폼 호출을 사용 하 여 C로 작성 된 관리 되지 않는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="7d360-133">관리 되지 않는 C 함수는로 C#작성 된 관리 DLL의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="7d360-134">관리 되 C# 는 함수는 C로 작성 된 다른 관리 되지 않는 함수를 호출 하 여 플랫폼 호출을 사용 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="7d360-135">두 번째 관리 되지 않는 함수는 C# 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="7d360-136">함수 C# 는 첫 번째 관리 되지 않는 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="7d360-137">첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램으로 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="7d360-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d360-138">Requirements</span></span>  
 <span data-ttu-id="7d360-139">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d360-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d360-140">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7d360-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d360-141">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d360-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d360-142">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d360-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d360-143">참조</span><span class="sxs-lookup"><span data-stu-id="7d360-143">See also</span></span>

- [<span data-ttu-id="7d360-144">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d360-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7d360-145">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d360-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d360-146">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d360-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7d360-147">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d360-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
