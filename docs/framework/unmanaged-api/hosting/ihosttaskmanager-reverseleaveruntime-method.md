---
title: IHostTaskManager::ReverseLeaveRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: 362239c584f469c9bd88f9f937bb3cdae7235429
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132951"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="d8437-102">IHostTaskManager::ReverseLeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="d8437-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="d8437-103">컨트롤이 CLR (공용 언어 런타임)을 유지 하 고 관리 코드에서 호출 된 관리 되지 않는 함수를 시작 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8437-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8437-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d8437-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="d8437-105">Return Value</span></span>  
  
|<span data-ttu-id="d8437-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8437-106">HRESULT</span></span>|<span data-ttu-id="d8437-107">설명</span><span class="sxs-lookup"><span data-stu-id="d8437-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8437-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8437-108">S_OK</span></span>|<span data-ttu-id="d8437-109">`ReverseLeaveRuntime` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="d8437-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8437-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8437-111">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8437-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8437-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8437-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-113">The call timed out.</span></span>|  
|<span data-ttu-id="d8437-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8437-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8437-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8437-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8437-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8437-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8437-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8437-118">E_FAIL</span></span>|<span data-ttu-id="d8437-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8437-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8437-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8437-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d8437-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d8437-123">메모리가 부족 하 여 요청 된 리소스 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8437-124">주의</span><span class="sxs-lookup"><span data-stu-id="d8437-124">Remarks</span></span>  
 <span data-ttu-id="d8437-125">CLR은 현재 실행 중인 작업에서 플랫폼 호출을 통해 관리 코드에서 호출 된 관리 되지 않는 함수로 제어를 반환 하 고 있음을 호스트에 알리기 위해 `ReverseLeaveRuntime`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="d8437-126">`ReverseLeaveRuntime`에 대 한 각 호출은 [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)에 대 한 해당 호출과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8437-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8437-127">Requirements</span></span>  
 <span data-ttu-id="d8437-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8437-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8437-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d8437-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8437-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8437-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8437-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8437-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8437-132">참조</span><span class="sxs-lookup"><span data-stu-id="d8437-132">See also</span></span>

- [<span data-ttu-id="d8437-133">CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="d8437-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="d8437-134">EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="d8437-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="d8437-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8437-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d8437-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8437-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d8437-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8437-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d8437-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8437-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d8437-139">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="d8437-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="d8437-140">[플랫폼 호출 자세히 보기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d8437-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
