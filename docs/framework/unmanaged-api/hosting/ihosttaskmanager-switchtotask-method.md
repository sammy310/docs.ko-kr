---
title: IHostTaskManager::SwitchToTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9074201cb56ad9e6c4ddadc8468d2ceadbafcb75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749317"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="5e7ba-102">IHostTaskManager::SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="5e7ba-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="5e7ba-103">현재 작업 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e7ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e7ba-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e7ba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5e7ba-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="5e7ba-106">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 호스트 하는 경우 수행 해야 하는 작업을 나타내는 열거형 값을 요청 된 작업이 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e7ba-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5e7ba-107">Return Value</span></span>  
  
|<span data-ttu-id="5e7ba-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e7ba-108">HRESULT</span></span>|<span data-ttu-id="5e7ba-109">설명</span><span class="sxs-lookup"><span data-stu-id="5e7ba-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e7ba-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e7ba-110">S_OK</span></span>|<span data-ttu-id="5e7ba-111">`SwitchToTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="5e7ba-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e7ba-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e7ba-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e7ba-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e7ba-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e7ba-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-115">The call timed out.</span></span>|  
|<span data-ttu-id="5e7ba-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e7ba-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e7ba-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e7ba-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e7ba-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e7ba-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e7ba-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e7ba-120">E_FAIL</span></span>|<span data-ttu-id="5e7ba-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e7ba-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e7ba-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e7ba-124">설명</span><span class="sxs-lookup"><span data-stu-id="5e7ba-124">Remarks</span></span>  
 <span data-ttu-id="5e7ba-125">호스트에서 다른 작업으로 필요한 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e7ba-126">`SwitchToTask` 호스트;으로 전환 해야 하는 작업을 지정 하지 않습니다. 전환 해야 하는 작업만을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e7ba-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e7ba-127">Requirements</span></span>  
 <span data-ttu-id="5e7ba-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e7ba-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e7ba-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e7ba-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e7ba-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5e7ba-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e7ba-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e7ba-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7ba-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e7ba-132">See also</span></span>

- [<span data-ttu-id="5e7ba-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7ba-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5e7ba-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7ba-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5e7ba-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7ba-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5e7ba-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e7ba-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
