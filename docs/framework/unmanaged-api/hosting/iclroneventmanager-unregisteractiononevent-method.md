---
title: ICLROnEventManager::UnregisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: ca3c7fe813f22d3beab3087414100b3d8e5814ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725601"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="7c95e-102">ICLROnEventManager::UnregisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="7c95e-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>

<span data-ttu-id="7c95e-103">지정 된 이벤트에 대해 이전에 등록 된 콜백 포인터의 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c95e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c95e-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c95e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c95e-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="7c95e-106">진행 에 설명 된 콜백 포인터의 등록을 취소할 이벤트를 나타내는 [EClrEvent](eclrevent-enumeration.md) 값 중 하나 `pAction` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="7c95e-107">진행 [Registeractiononevent](iclroneventmanager-registeractiononevent-method.md) 메서드에 매개 변수로 전달 된 [IActionOnCLREvent](iactiononclrevent-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c95e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c95e-108">Return Value</span></span>  
  
|<span data-ttu-id="7c95e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c95e-109">HRESULT</span></span>|<span data-ttu-id="7c95e-110">설명</span><span class="sxs-lookup"><span data-stu-id="7c95e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c95e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c95e-111">S_OK</span></span>|<span data-ttu-id="7c95e-112">`UnregisterActionOnEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c95e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c95e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c95e-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c95e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c95e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c95e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c95e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c95e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c95e-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c95e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c95e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c95e-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c95e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c95e-121">E_FAIL</span></span>|<span data-ttu-id="7c95e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c95e-123">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c95e-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c95e-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c95e-125">Requirements</span></span>  

 <span data-ttu-id="7c95e-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c95e-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c95e-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7c95e-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c95e-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c95e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c95e-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c95e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c95e-130">참조</span><span class="sxs-lookup"><span data-stu-id="7c95e-130">See also</span></span>

- [<span data-ttu-id="7c95e-131">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="7c95e-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="7c95e-132">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c95e-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="7c95e-133">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c95e-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="7c95e-134">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c95e-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
