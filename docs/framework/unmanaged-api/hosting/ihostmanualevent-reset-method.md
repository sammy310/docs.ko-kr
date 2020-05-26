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
ms.openlocfilehash: 049a0ae6d860c7c431d08af8ba4539656b8e5592
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804578"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="8aeac-102">IHostManualEvent::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="8aeac-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="8aeac-103">현재 [IHostManualEvent](ihostmanualevent-interface.md) 인스턴스를 신호를 받지 않는 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aeac-104">구문</span><span class="sxs-lookup"><span data-stu-id="8aeac-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8aeac-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="8aeac-105">Return Value</span></span>  
  
|<span data-ttu-id="8aeac-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8aeac-106">HRESULT</span></span>|<span data-ttu-id="8aeac-107">Description</span><span class="sxs-lookup"><span data-stu-id="8aeac-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8aeac-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8aeac-108">S_OK</span></span>|<span data-ttu-id="8aeac-109">`Reset`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="8aeac-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8aeac-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8aeac-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8aeac-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8aeac-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8aeac-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-113">The call timed out.</span></span>|  
|<span data-ttu-id="8aeac-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8aeac-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8aeac-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8aeac-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8aeac-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8aeac-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8aeac-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8aeac-118">E_FAIL</span></span>|<span data-ttu-id="8aeac-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8aeac-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8aeac-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8aeac-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8aeac-122">Requirements</span></span>  
 <span data-ttu-id="8aeac-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aeac-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aeac-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8aeac-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8aeac-125">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aeac-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8aeac-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aeac-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeac-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aeac-127">See also</span></span>

- [<span data-ttu-id="8aeac-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aeac-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8aeac-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aeac-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="8aeac-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aeac-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="8aeac-131">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aeac-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="8aeac-132">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aeac-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
