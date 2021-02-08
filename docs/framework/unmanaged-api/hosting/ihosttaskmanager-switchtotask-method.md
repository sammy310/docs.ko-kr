---
description: '자세히 알아보기: IHostTaskManager:: SwitchToTask 메서드'
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
ms.openlocfilehash: 6333dcdf7e1bbe6bde575f53f4743a1300c770f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789361"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="0a3c3-103">IHostTaskManager::SwitchToTask 메서드</span><span class="sxs-lookup"><span data-stu-id="0a3c3-103">IHostTaskManager::SwitchToTask Method</span></span>

<span data-ttu-id="0a3c3-104">현재 작업을 전환 해야 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-104">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a3c3-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a3c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a3c3-106">Parameters</span></span>  

 `option`  
 <span data-ttu-id="0a3c3-107">진행 요청 된 작업이 차단 되는 경우 호스트에서 수행 해야 하는 작업을 나타내는 [WAIT_OPTION](wait-option-enumeration.md) 열거형 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a3c3-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0a3c3-108">Return Value</span></span>  
  
|<span data-ttu-id="0a3c3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a3c3-109">HRESULT</span></span>|<span data-ttu-id="0a3c3-110">설명</span><span class="sxs-lookup"><span data-stu-id="0a3c3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a3c3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a3c3-111">S_OK</span></span>|<span data-ttu-id="0a3c3-112">`SwitchToTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-112">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="0a3c3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a3c3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a3c3-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a3c3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a3c3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a3c3-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-116">The call timed out.</span></span>|  
|<span data-ttu-id="0a3c3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a3c3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a3c3-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a3c3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a3c3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a3c3-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a3c3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a3c3-121">E_FAIL</span></span>|<span data-ttu-id="0a3c3-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a3c3-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a3c3-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a3c3-125">설명</span><span class="sxs-lookup"><span data-stu-id="0a3c3-125">Remarks</span></span>  

 <span data-ttu-id="0a3c3-126">호스트는 다른 작업을 원하는 대로 또는 필요에 따라 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-126">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a3c3-127">`SwitchToTask` 는 호스트가 전환 해야 하는 작업을 지정 하지 않습니다. 전환 해야 하는 작업만 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-127">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a3c3-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a3c3-128">Requirements</span></span>  

 <span data-ttu-id="0a3c3-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a3c3-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0a3c3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a3c3-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a3c3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a3c3-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a3c3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3c3-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a3c3-133">See also</span></span>

- [<span data-ttu-id="0a3c3-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a3c3-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0a3c3-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a3c3-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0a3c3-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a3c3-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0a3c3-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a3c3-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
