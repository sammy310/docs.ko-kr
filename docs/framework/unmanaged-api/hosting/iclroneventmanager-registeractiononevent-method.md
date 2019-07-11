---
title: ICLROnEventManager::RegisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b259efb4148c10c7546cb95608145bde0597e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756259"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="48ef9-102">ICLROnEventManager::RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="48ef9-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="48ef9-103">지정된 된 이벤트에 대 한 콜백 포인터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ef9-104">구문</span><span class="sxs-lookup"><span data-stu-id="48ef9-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48ef9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48ef9-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="48ef9-106">[in] 중 하나는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 에 설명 된 콜백 포인터를 등록 하는 이벤트를 나타내는 값을 `pAction`입니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="48ef9-107">[in] 에 대 한 포인터를 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 등록된 이벤트가 발생할 때 호출 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48ef9-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="48ef9-108">Return Value</span></span>  
  
|<span data-ttu-id="48ef9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48ef9-109">HRESULT</span></span>|<span data-ttu-id="48ef9-110">설명</span><span class="sxs-lookup"><span data-stu-id="48ef9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48ef9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48ef9-111">S_OK</span></span>|<span data-ttu-id="48ef9-112">`RegisterActionOnEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="48ef9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48ef9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48ef9-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48ef9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48ef9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48ef9-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-116">The call timed out.</span></span>|  
|<span data-ttu-id="48ef9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48ef9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48ef9-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48ef9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48ef9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48ef9-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48ef9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48ef9-121">E_FAIL</span></span>|<span data-ttu-id="48ef9-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48ef9-123">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48ef9-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ef9-125">설명</span><span class="sxs-lookup"><span data-stu-id="48ef9-125">Remarks</span></span>  
 <span data-ttu-id="48ef9-126">호스트에 설명 된 두 이벤트 형식 중 하나 또는 모두에 대 한 콜백을 등록할 수 `EClrEvent`입니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="48ef9-127">호스트 가져옵니다 합니다 `ICLROnEventManager` 호출 하 여 인터페이스를 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="48ef9-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ef9-128">이벤트는 `RegisterActionOnEvent` 두 번 이상 및는 언로드 또는 CLR의 비활성화를 알리기 위해 서로 다른 여러 스레드에서 레지스터를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48ef9-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ef9-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48ef9-129">Requirements</span></span>  
 <span data-ttu-id="48ef9-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="48ef9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ef9-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48ef9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48ef9-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="48ef9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48ef9-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ef9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ef9-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="48ef9-134">See also</span></span>

- [<span data-ttu-id="48ef9-135">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="48ef9-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="48ef9-136">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48ef9-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="48ef9-137">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48ef9-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="48ef9-138">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48ef9-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
