---
title: IActionOnCLREvent::OnEvent 메서드
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126928"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="2c2da-102">IActionOnCLREvent::OnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="2c2da-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="2c2da-103">[ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 메서드를 호출 하 여 등록 된 이벤트에 대해 콜백을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2da-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c2da-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c2da-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="2c2da-106">진행 이벤트 유형을 나타내는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="2c2da-107">진행 `event`에 대 한 세부 정보를 포함 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c2da-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2c2da-108">Return Value</span></span>  
  
|<span data-ttu-id="2c2da-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c2da-109">HRESULT</span></span>|<span data-ttu-id="2c2da-110">설명</span><span class="sxs-lookup"><span data-stu-id="2c2da-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c2da-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c2da-111">S_OK</span></span>|<span data-ttu-id="2c2da-112">`OnEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="2c2da-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c2da-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c2da-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c2da-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c2da-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c2da-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-116">The call timed out.</span></span>|  
|<span data-ttu-id="2c2da-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c2da-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c2da-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c2da-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c2da-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c2da-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c2da-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c2da-121">E_FAIL</span></span>|<span data-ttu-id="2c2da-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c2da-123">메서드가 E_FAIL을 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c2da-124">모든 호스팅 메서드에 대 한 후속 호출에서는 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c2da-125">주의</span><span class="sxs-lookup"><span data-stu-id="2c2da-125">Remarks</span></span>  
 <span data-ttu-id="2c2da-126">`data` 매개 변수는 지정 되지 않은 형식의 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="2c2da-127">`event` 매개 변수가 `Event_DomainUnload`이면 언로드된 <xref:System.AppDomain>에 대 한 숫자 식별자 `data`입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="2c2da-128">호스트는이 식별자를 키로 사용 하 여 적절 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="2c2da-129">`event` `Event_MDAFired`경우 `data` MDA (관리 디버깅 도우미)의 메시지 출력을 포함 하는 [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="2c2da-130">Mda는 이벤트에 대 한 XML 메시지를 생성 하 여 개발자가 디버깅 하는 데 도움이 되는 CLR의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="2c2da-131">이러한 메시지는 관리 코드와 비관리 코드 간의 전환을 디버깅 하는 데 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="2c2da-132">자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c2da-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2da-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c2da-133">Requirements</span></span>  
 <span data-ttu-id="2c2da-134">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c2da-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2da-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2c2da-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c2da-136">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c2da-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2da-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2da-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2da-138">참조</span><span class="sxs-lookup"><span data-stu-id="2c2da-138">See also</span></span>

- [<span data-ttu-id="2c2da-139">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="2c2da-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="2c2da-140">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="2c2da-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="2c2da-141">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c2da-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="2c2da-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c2da-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2c2da-143">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c2da-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="2c2da-144">MDAInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="2c2da-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
