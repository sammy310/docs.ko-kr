---
title: IHostTask::Join 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e88b7bd647fe46ba98e4396d1836293647f2faa4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764415"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="f73fb-102">IHostTask::Join 메서드</span><span class="sxs-lookup"><span data-stu-id="f73fb-102">IHostTask::Join Method</span></span>
<span data-ttu-id="f73fb-103">현재 작업까지 호출 작업을 차단 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스가 완료 되 면 지정 된 시간 간격이 경과 하면 또는 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="f73fb-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f73fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f73fb-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="f73fb-106">[in] 시간 간격을 밀리초 작업이 종료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="f73fb-107">이 간격이 경과할 때까지 태스크를 종료 하는 경우에 호출 작업 차단 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="f73fb-108">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="f73fb-109">Wait_alertable을 호스트 하는 경우 작업에 지시 `Alert` 하기 전에 호출 됩니다 `milliseconds` 경과 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f73fb-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="f73fb-110">Return Value</span></span>  
  
|<span data-ttu-id="f73fb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f73fb-111">HRESULT</span></span>|<span data-ttu-id="f73fb-112">설명</span><span class="sxs-lookup"><span data-stu-id="f73fb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f73fb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f73fb-113">S_OK</span></span>|<span data-ttu-id="f73fb-114">`Join` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="f73fb-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f73fb-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f73fb-116">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f73fb-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f73fb-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f73fb-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-118">The call timed out.</span></span>|  
|<span data-ttu-id="f73fb-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f73fb-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f73fb-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f73fb-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f73fb-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f73fb-122">이벤트가 차단 된 스레드가 취소 된 또는 파이버가 또는 현재 기다리던 `IHostTask` 인스턴스가 작업과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="f73fb-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f73fb-123">E_FAIL</span></span>|<span data-ttu-id="f73fb-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f73fb-125">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f73fb-126">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f73fb-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f73fb-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f73fb-127">Requirements</span></span>  
 <span data-ttu-id="f73fb-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f73fb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f73fb-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f73fb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f73fb-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f73fb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f73fb-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f73fb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73fb-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="f73fb-132">See also</span></span>

- [<span data-ttu-id="f73fb-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f73fb-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f73fb-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f73fb-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f73fb-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f73fb-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f73fb-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f73fb-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f73fb-137">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="f73fb-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
