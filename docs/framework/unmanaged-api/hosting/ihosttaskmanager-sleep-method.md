---
title: IHostTaskManager::Sleep 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4618f7ea08aa304ff5e77800cf3c0a90dd88fdbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110919"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="8069e-102">IHostTaskManager::Sleep 메서드</span><span class="sxs-lookup"><span data-stu-id="8069e-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="8069e-103">현재 태스크 절전 모드로 전환 됨 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8069e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8069e-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8069e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8069e-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="8069e-106">[in] 스레드가 대기 하는 밀리초 단위의 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="8069e-107">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 이 호스트가 수행할 동작을 나타내는 열거형 값 작업 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8069e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="8069e-108">Return Value</span></span>  
  
|<span data-ttu-id="8069e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8069e-109">HRESULT</span></span>|<span data-ttu-id="8069e-110">설명</span><span class="sxs-lookup"><span data-stu-id="8069e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8069e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8069e-111">S_OK</span></span>|<span data-ttu-id="8069e-112">`Sleep` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="8069e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8069e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8069e-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8069e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8069e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8069e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-116">The call timed out.</span></span>|  
|<span data-ttu-id="8069e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8069e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8069e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8069e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8069e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8069e-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8069e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8069e-121">E_FAIL</span></span>|<span data-ttu-id="8069e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8069e-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8069e-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8069e-125">설명</span><span class="sxs-lookup"><span data-stu-id="8069e-125">Remarks</span></span>  
 <span data-ttu-id="8069e-126">일반적으로 CLR에서 호출한 `IHostTaskManager::Sleep` 때 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 사용자 코드에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8069e-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8069e-127">Requirements</span></span>  
 <span data-ttu-id="8069e-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8069e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8069e-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8069e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8069e-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8069e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8069e-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8069e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8069e-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="8069e-132">See also</span></span>

- [<span data-ttu-id="8069e-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8069e-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8069e-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8069e-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8069e-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8069e-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8069e-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8069e-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
