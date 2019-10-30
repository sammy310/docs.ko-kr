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
ms.openlocfilehash: a55b43f3629cebb0ba1d3a7ac1802126874418d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122124"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="678c6-102">IHostTaskManager::SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="678c6-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="678c6-103">현재 작업을 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="678c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="678c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="678c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="678c6-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="678c6-106">진행 요청 된 작업이 차단 되는 경우 호스트에서 수행 해야 하는 작업을 나타내는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 열거형 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="678c6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="678c6-107">Return Value</span></span>  
  
|<span data-ttu-id="678c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="678c6-108">HRESULT</span></span>|<span data-ttu-id="678c6-109">설명</span><span class="sxs-lookup"><span data-stu-id="678c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="678c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="678c6-110">S_OK</span></span>|<span data-ttu-id="678c6-111">`SwitchToTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="678c6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="678c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="678c6-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="678c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="678c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="678c6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="678c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="678c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="678c6-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="678c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="678c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="678c6-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="678c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="678c6-120">E_FAIL</span></span>|<span data-ttu-id="678c6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="678c6-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="678c6-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="678c6-124">주의</span><span class="sxs-lookup"><span data-stu-id="678c6-124">Remarks</span></span>  
 <span data-ttu-id="678c6-125">호스트는 다른 작업을 원하는 대로 또는 필요에 따라 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="678c6-126">`SwitchToTask` 호스트가 전환 해야 하는 작업을 지정 하지 않습니다. 전환 해야 하는 작업만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="678c6-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="678c6-127">Requirements</span></span>  
 <span data-ttu-id="678c6-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="678c6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="678c6-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="678c6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="678c6-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="678c6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="678c6-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="678c6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678c6-132">참조</span><span class="sxs-lookup"><span data-stu-id="678c6-132">See also</span></span>

- [<span data-ttu-id="678c6-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678c6-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="678c6-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678c6-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="678c6-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678c6-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="678c6-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="678c6-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
