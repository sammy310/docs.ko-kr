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
ms.openlocfilehash: c153e6ae8558eeab2efa99765405fb7c84632b01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110034"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="b878d-102">IHostTask::Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="b878d-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="b878d-103">현재 작업의 시작을 호스트 하는 요청 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스 작업을 중단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b878d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b878d-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b878d-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="b878d-105">Return Value</span></span>  
  
|<span data-ttu-id="b878d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b878d-106">HRESULT</span></span>|<span data-ttu-id="b878d-107">설명</span><span class="sxs-lookup"><span data-stu-id="b878d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b878d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b878d-108">S_OK</span></span>|<span data-ttu-id="b878d-109">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="b878d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b878d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b878d-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b878d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b878d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b878d-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-113">The call timed out.</span></span>|  
|<span data-ttu-id="b878d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b878d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b878d-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b878d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b878d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b878d-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b878d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b878d-118">E_FAIL</span></span>|<span data-ttu-id="b878d-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b878d-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b878d-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b878d-122">설명</span><span class="sxs-lookup"><span data-stu-id="b878d-122">Remarks</span></span>  
 <span data-ttu-id="b878d-123">CLR 호출을 `Alert` 메서드 때 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 사용자 코드에서 호출 되 때나를 <xref:System.AppDomain> 현재 연관 <xref:System.Threading.Thread> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="b878d-124">호스트는 호출이 비동기적 이므로 때문에 즉시 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="b878d-125">호스트 작업을 즉시 경고 수 없는 경우는 경고를 받을 수 상태가 될 다음 시간 절전 모드 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  `Alert` <span data-ttu-id="b878d-126">런타임이 경과 하는 작업에만 적용을 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 와 같은 메서드와 wait_alertable 값 [조인](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b878d-126">affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b878d-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b878d-127">Requirements</span></span>  
 <span data-ttu-id="b878d-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b878d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b878d-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b878d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b878d-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b878d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b878d-131">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b878d-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b878d-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="b878d-132">See also</span></span>

- [<span data-ttu-id="b878d-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b878d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b878d-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b878d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b878d-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b878d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b878d-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b878d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
