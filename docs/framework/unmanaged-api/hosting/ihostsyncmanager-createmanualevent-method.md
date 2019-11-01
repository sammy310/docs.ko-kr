---
title: IHostSyncManager::CreateManualEvent 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195862"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="5e860-102">IHostSyncManager::CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="5e860-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="5e860-103">수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e860-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e860-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e860-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5e860-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="5e860-106">[in] `true`개체가 신호를 받으면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="5e860-107">제한이 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e860-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5e860-108">Return Value</span></span>  
  
|<span data-ttu-id="5e860-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e860-109">HRESULT</span></span>|<span data-ttu-id="5e860-110">설명</span><span class="sxs-lookup"><span data-stu-id="5e860-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e860-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e860-111">S_OK</span></span>|<span data-ttu-id="5e860-112">`CreateManualEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="5e860-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e860-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e860-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e860-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e860-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e860-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-116">The call timed out.</span></span>|  
|<span data-ttu-id="5e860-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e860-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e860-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e860-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e860-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e860-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e860-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e860-121">E_FAIL</span></span>|<span data-ttu-id="5e860-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e860-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e860-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e860-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5e860-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5e860-126">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e860-127">주의</span><span class="sxs-lookup"><span data-stu-id="5e860-127">Remarks</span></span>  
 <span data-ttu-id="5e860-128">`CreateManualEvent` [IHostManualEvent:: reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) 메서드를 호출 하 여 신호를 받지 않는 상태로 설정 해야 하는 수동 재설정 이벤트 개체인 `IHostManualEvent`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="5e860-129">`CreateManualEvent`는 `bManualReset` 매개 변수에 지정 된 `true` 값을 사용 하 여 Win32 `CreateEvent` 함수를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e860-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e860-130">Requirements</span></span>  
 <span data-ttu-id="5e860-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e860-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e860-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5e860-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e860-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e860-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e860-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e860-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e860-135">참조</span><span class="sxs-lookup"><span data-stu-id="5e860-135">See also</span></span>

- [<span data-ttu-id="5e860-136">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e860-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5e860-137">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e860-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5e860-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5e860-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
