---
title: IHostTaskManager::ReverseEnterRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6eefdaf5dee423b0a9ae054446224a3ea97e3c9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213781"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="5a6c2-102">IHostTaskManager::ReverseEnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="5a6c2-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="5a6c2-103">비관리 코드에서 공용 언어 런타임 (CLR)에 호출이 수행 되는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a6c2-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5a6c2-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="5a6c2-105">Return Value</span></span>  
  
|<span data-ttu-id="5a6c2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a6c2-106">HRESULT</span></span>|<span data-ttu-id="5a6c2-107">설명</span><span class="sxs-lookup"><span data-stu-id="5a6c2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a6c2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a6c2-108">S_OK</span></span>|<span data-ttu-id="5a6c2-109">`ReverseEnterRuntime` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="5a6c2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a6c2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a6c2-111">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a6c2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a6c2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a6c2-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-113">The call timed out.</span></span>|  
|<span data-ttu-id="5a6c2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a6c2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a6c2-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a6c2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a6c2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a6c2-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a6c2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a6c2-118">E_FAIL</span></span>|<span data-ttu-id="5a6c2-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a6c2-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a6c2-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5a6c2-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5a6c2-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5a6c2-123">메모리가 부족 하 여 요청 된 리소스 할당을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a6c2-124">설명</span><span class="sxs-lookup"><span data-stu-id="5a6c2-124">Remarks</span></span>  
 <span data-ttu-id="5a6c2-125">호출할 때마다 clr은 호출 된 시퀀스에서 관리 코드에서 `ReverseEnterRuntime` 에 대 한 호출에 해당 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a6c2-126">호출 중첩 되지 않은 상태로 비관리 코드에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="5a6c2-127">이 경우에 대 한 호출이 있습니다. [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), 또는 `ReverseLeaveRuntime`, 및에 대 한 호출 수가 `ReverseEnterRuntime` 에 대 한 호출의 수와 같지 않습니다 `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6c2-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a6c2-128">Requirements</span></span>  
 <span data-ttu-id="5a6c2-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a6c2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6c2-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a6c2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a6c2-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5a6c2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a6c2-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6c2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6c2-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a6c2-133">See also</span></span>

- [<span data-ttu-id="5a6c2-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a6c2-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5a6c2-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a6c2-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5a6c2-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a6c2-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5a6c2-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a6c2-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
