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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cd3012d966c777749eb800b8986974a4e8d401f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154169"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="bc723-102">IHostTaskManager::ReverseLeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="bc723-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="bc723-103">컨트롤을 차례로 호출 된 관리 코드에서 관리 되지 않는 함수를 입력의 CLR (공용 언어 런타임)을 유지 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc723-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc723-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bc723-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="bc723-105">Return Value</span></span>  
  
|<span data-ttu-id="bc723-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc723-106">HRESULT</span></span>|<span data-ttu-id="bc723-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc723-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc723-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc723-108">S_OK</span></span>|<span data-ttu-id="bc723-109">`ReverseLeaveRuntime` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="bc723-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc723-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc723-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc723-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc723-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc723-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-113">The call timed out.</span></span>|  
|<span data-ttu-id="bc723-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc723-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc723-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc723-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc723-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc723-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc723-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc723-118">E_FAIL</span></span>|<span data-ttu-id="bc723-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc723-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc723-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bc723-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bc723-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bc723-123">메모리가 부족 하 여 요청 된 리소스 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc723-124">설명</span><span class="sxs-lookup"><span data-stu-id="bc723-124">Remarks</span></span>  
 <span data-ttu-id="bc723-125">CLR에서는 `ReverseLeaveRuntime` 를 차례로 호출 된 플랫폼을 통해 관리 되는 코드에서 관리 되지 않는 함수에는 컨트롤에서 현재 실행 중인 작업을 반환 하는 호스트에 알리기 위해 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="bc723-126">호출할 때마다 `ReverseLeaveRuntime` 해당 호출을 일치 [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc723-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc723-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc723-127">Requirements</span></span>  
 <span data-ttu-id="bc723-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc723-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc723-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc723-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc723-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bc723-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc723-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc723-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc723-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="bc723-132">See also</span></span>

- [<span data-ttu-id="bc723-133">CallNeedsHostHook 메서드</span><span class="sxs-lookup"><span data-stu-id="bc723-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="bc723-134">EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="bc723-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="bc723-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc723-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="bc723-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc723-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="bc723-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc723-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="bc723-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc723-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="bc723-139">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="bc723-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="bc723-140">[플랫폼 호출 자세히 보기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bc723-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
