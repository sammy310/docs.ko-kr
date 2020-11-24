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
ms.openlocfilehash: 855f8a5d3582bbad59301a344d8a51198c40a051
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673048"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="02d55-102">IHostTaskManager::LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="02d55-102">IHostTaskManager::LeaveRuntime Method</span></span>

<span data-ttu-id="02d55-103">현재 실행 중인 태스크가 CLR (공용 언어 런타임)을 유지 하 고 비관리 코드를 입력 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="02d55-104">[IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) 에 대 한 해당 호출에서는 현재 실행 중인 작업에서 관리 코드를 현재 실행 하 고 있음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d55-105">구문</span><span class="sxs-lookup"><span data-stu-id="02d55-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d55-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02d55-106">Parameters</span></span>  

 `target`  
 <span data-ttu-id="02d55-107">진행 호출할 관리 되지 않는 함수의 매핑된 이식 가능한 실행 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d55-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="02d55-108">Return Value</span></span>  
  
|<span data-ttu-id="02d55-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02d55-109">HRESULT</span></span>|<span data-ttu-id="02d55-110">설명</span><span class="sxs-lookup"><span data-stu-id="02d55-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02d55-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="02d55-111">S_OK</span></span>|<span data-ttu-id="02d55-112">`LeaveRuntime` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="02d55-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02d55-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02d55-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02d55-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02d55-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02d55-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-116">The call timed out.</span></span>|  
|<span data-ttu-id="02d55-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02d55-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02d55-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02d55-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02d55-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02d55-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02d55-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02d55-121">E_FAIL</span></span>|<span data-ttu-id="02d55-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02d55-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02d55-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="02d55-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="02d55-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="02d55-126">메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02d55-127">설명</span><span class="sxs-lookup"><span data-stu-id="02d55-127">Remarks</span></span>  

 <span data-ttu-id="02d55-128">비관리 코드와의 호출 시퀀스는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="02d55-129">예를 들어 아래 목록은 `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)에 대 한 호출 시퀀스를 사용 하 여 `IHostTaskManager::EnterRuntime` 호스트에서 중첩 된 레이어를 식별할 수 있도록 하는 가상의 상황을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="02d55-130">작업</span><span class="sxs-lookup"><span data-stu-id="02d55-130">Action</span></span>|<span data-ttu-id="02d55-131">해당 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="02d55-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="02d55-132">관리 되는 Visual Basic 실행 파일은 플랫폼 호출을 사용 하 여 C로 작성 된 관리 되지 않는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="02d55-133">관리 되지 않는 C 함수는 c #으로 작성 된 관리 DLL의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="02d55-134">관리 되는 c # 함수는 C로 작성 된 다른 관리 되지 않는 함수를 호출 하 여 플랫폼 호출을 사용 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="02d55-135">두 번째 관리 되지 않는 함수는 c # 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="02d55-136">C # 함수는 첫 번째 관리 되지 않는 함수에 대 한 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="02d55-137">첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램으로 실행을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="02d55-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02d55-138">Requirements</span></span>  

 <span data-ttu-id="02d55-139">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d55-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d55-140">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02d55-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02d55-141">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d55-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02d55-142">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d55-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d55-143">참조</span><span class="sxs-lookup"><span data-stu-id="02d55-143">See also</span></span>

- [<span data-ttu-id="02d55-144">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02d55-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="02d55-145">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02d55-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="02d55-146">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02d55-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="02d55-147">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02d55-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
