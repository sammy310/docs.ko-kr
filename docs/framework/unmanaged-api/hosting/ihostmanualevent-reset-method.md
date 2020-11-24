---
title: IHostManualEvent::Reset 메서드
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 5653f874ef7a681f6667b3508b82ac493234cc4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673152"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="f2a56-102">IHostManualEvent::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="f2a56-102">IHostManualEvent::Reset Method</span></span>

<span data-ttu-id="f2a56-103">현재 [IHostManualEvent](ihostmanualevent-interface.md) 인스턴스를 신호를 받지 않는 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a56-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2a56-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f2a56-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="f2a56-105">Return Value</span></span>  
  
|<span data-ttu-id="f2a56-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2a56-106">HRESULT</span></span>|<span data-ttu-id="f2a56-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2a56-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2a56-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2a56-108">S_OK</span></span>|<span data-ttu-id="f2a56-109">`Reset` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="f2a56-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2a56-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2a56-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2a56-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2a56-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2a56-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-113">The call timed out.</span></span>|  
|<span data-ttu-id="f2a56-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2a56-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2a56-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2a56-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2a56-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2a56-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2a56-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2a56-118">E_FAIL</span></span>|<span data-ttu-id="f2a56-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2a56-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2a56-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2a56-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2a56-122">Requirements</span></span>  

 <span data-ttu-id="f2a56-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2a56-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a56-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f2a56-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2a56-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2a56-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2a56-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a56-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a56-127">참조</span><span class="sxs-lookup"><span data-stu-id="f2a56-127">See also</span></span>

- [<span data-ttu-id="f2a56-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2a56-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f2a56-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2a56-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="f2a56-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2a56-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="f2a56-131">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2a56-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="f2a56-132">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2a56-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
