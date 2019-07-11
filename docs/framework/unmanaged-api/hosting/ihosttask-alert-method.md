---
title: IHostTask::Alert 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a5e3b82645456ffa574f63931abbf60a2194540
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764540"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="55e60-102">IHostTask::Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="55e60-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="55e60-103">현재 작업의 시작을 호스트 하는 요청 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스 작업을 중단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e60-104">구문</span><span class="sxs-lookup"><span data-stu-id="55e60-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="55e60-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="55e60-105">Return Value</span></span>  
  
|<span data-ttu-id="55e60-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55e60-106">HRESULT</span></span>|<span data-ttu-id="55e60-107">설명</span><span class="sxs-lookup"><span data-stu-id="55e60-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55e60-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="55e60-108">S_OK</span></span>|<span data-ttu-id="55e60-109">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="55e60-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55e60-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55e60-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55e60-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55e60-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55e60-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-113">The call timed out.</span></span>|  
|<span data-ttu-id="55e60-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55e60-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55e60-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55e60-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55e60-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55e60-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55e60-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55e60-118">E_FAIL</span></span>|<span data-ttu-id="55e60-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55e60-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55e60-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e60-122">설명</span><span class="sxs-lookup"><span data-stu-id="55e60-122">Remarks</span></span>  
 <span data-ttu-id="55e60-123">CLR 호출을 `Alert` 메서드 때 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 사용자 코드에서 호출 되 때나를 <xref:System.AppDomain> 현재 연관 <xref:System.Threading.Thread> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="55e60-124">호스트는 호출이 비동기적 이므로 때문에 즉시 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="55e60-125">호스트 작업을 즉시 경고 수 없는 경우는 경고를 받을 수 상태가 될 다음 시간 절전 모드 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55e60-126">`Alert` 런타임이 경과 하는 작업에만 적용을 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 와 같은 메서드와 wait_alertable 값 [조인](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55e60-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e60-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55e60-127">Requirements</span></span>  
 <span data-ttu-id="55e60-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55e60-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e60-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55e60-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55e60-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="55e60-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e60-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e60-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e60-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="55e60-132">See also</span></span>

- [<span data-ttu-id="55e60-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e60-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="55e60-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e60-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="55e60-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e60-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="55e60-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55e60-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
