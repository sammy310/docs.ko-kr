---
description: '자세히 알아보기: IHostSyncManager:: CreateManualEvent 메서드'
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
ms.openlocfilehash: 300d6cbf9555eb331a470767cdfb2745da300bb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784797"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="fc53b-103">IHostSyncManager::CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="fc53b-103">IHostSyncManager::CreateManualEvent Method</span></span>

<span data-ttu-id="fc53b-104">수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-104">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc53b-105">구문</span><span class="sxs-lookup"><span data-stu-id="fc53b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc53b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc53b-106">Parameters</span></span>  

 `bInitialState`  
 <span data-ttu-id="fc53b-107">[in] `true` 개체가 신호를 받으면이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-107">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="fc53b-108">제한이 [IHostManualEvent](ihostmanualevent-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 이벤트를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-108">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc53b-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="fc53b-109">Return Value</span></span>  
  
|<span data-ttu-id="fc53b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc53b-110">HRESULT</span></span>|<span data-ttu-id="fc53b-111">설명</span><span class="sxs-lookup"><span data-stu-id="fc53b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc53b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc53b-112">S_OK</span></span>|<span data-ttu-id="fc53b-113">`CreateManualEvent` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-113">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="fc53b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc53b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc53b-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc53b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc53b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc53b-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-117">The call timed out.</span></span>|  
|<span data-ttu-id="fc53b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc53b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc53b-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc53b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc53b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc53b-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc53b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc53b-122">E_FAIL</span></span>|<span data-ttu-id="fc53b-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc53b-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc53b-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fc53b-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fc53b-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fc53b-127">메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc53b-128">설명</span><span class="sxs-lookup"><span data-stu-id="fc53b-128">Remarks</span></span>  

 <span data-ttu-id="fc53b-129">`CreateManualEvent``IHostManualEvent` [IHostManualEvent:: reset](ihostmanualevent-reset-method.md) 메서드를 호출 하 여 신호를 받지 않는 상태로 설정 해야 하는 수동 다시 설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-129">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="fc53b-130">`CreateManualEvent``CreateEvent`매개 변수에 지정 된 값을 사용 하 여 Win32 함수를 미러링합니다 `true` `bManualReset` .</span><span class="sxs-lookup"><span data-stu-id="fc53b-130">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc53b-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc53b-131">Requirements</span></span>  

 <span data-ttu-id="fc53b-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc53b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc53b-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fc53b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc53b-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc53b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc53b-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc53b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc53b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc53b-136">See also</span></span>

- [<span data-ttu-id="fc53b-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc53b-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="fc53b-138">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc53b-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="fc53b-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc53b-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
