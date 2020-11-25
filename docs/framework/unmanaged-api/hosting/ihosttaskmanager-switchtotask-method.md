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
ms.openlocfilehash: bf3ddd91a58669540ef310e268162ec78408494f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702031"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="bd9dc-102">IHostTaskManager::SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="bd9dc-102">IHostTaskManager::SwitchToTask Method</span></span>

<span data-ttu-id="bd9dc-103">현재 작업을 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd9dc-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd9dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd9dc-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="bd9dc-106">진행 요청 된 작업이 차단 되는 경우 호스트에서 수행 해야 하는 작업을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 열거형 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd9dc-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="bd9dc-107">Return Value</span></span>  
  
|<span data-ttu-id="bd9dc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd9dc-108">HRESULT</span></span>|<span data-ttu-id="bd9dc-109">설명</span><span class="sxs-lookup"><span data-stu-id="bd9dc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd9dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd9dc-110">S_OK</span></span>|<span data-ttu-id="bd9dc-111">`SwitchToTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="bd9dc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd9dc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd9dc-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd9dc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd9dc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd9dc-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-115">The call timed out.</span></span>|  
|<span data-ttu-id="bd9dc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd9dc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd9dc-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd9dc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd9dc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd9dc-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd9dc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd9dc-120">E_FAIL</span></span>|<span data-ttu-id="bd9dc-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd9dc-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd9dc-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd9dc-124">설명</span><span class="sxs-lookup"><span data-stu-id="bd9dc-124">Remarks</span></span>  

 <span data-ttu-id="bd9dc-125">호스트는 다른 작업을 원하는 대로 또는 필요에 따라 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd9dc-126">`SwitchToTask` 는 호스트가 전환 해야 하는 작업을 지정 하지 않습니다. 전환 해야 하는 작업만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9dc-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd9dc-127">Requirements</span></span>  

 <span data-ttu-id="bd9dc-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9dc-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bd9dc-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd9dc-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd9dc-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9dc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9dc-132">참조</span><span class="sxs-lookup"><span data-stu-id="bd9dc-132">See also</span></span>

- [<span data-ttu-id="bd9dc-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd9dc-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="bd9dc-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd9dc-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bd9dc-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd9dc-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bd9dc-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd9dc-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
