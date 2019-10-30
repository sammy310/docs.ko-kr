---
title: IHostManualEvent::Set 메서드
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136767"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="9a113-102">IHostManualEvent::Set 메서드</span><span class="sxs-lookup"><span data-stu-id="9a113-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="9a113-103">현재 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스를 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a113-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a113-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a113-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="9a113-105">Return Value</span></span>  
  
|<span data-ttu-id="9a113-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a113-106">HRESULT</span></span>|<span data-ttu-id="9a113-107">설명</span><span class="sxs-lookup"><span data-stu-id="9a113-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a113-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a113-108">S_OK</span></span>|<span data-ttu-id="9a113-109">`Set` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="9a113-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a113-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a113-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a113-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a113-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a113-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-113">The call timed out.</span></span>|  
|<span data-ttu-id="9a113-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a113-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a113-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a113-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a113-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a113-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a113-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a113-118">E_FAIL</span></span>|<span data-ttu-id="9a113-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a113-120">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a113-121">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a113-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a113-122">Requirements</span></span>  
 <span data-ttu-id="9a113-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a113-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a113-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9a113-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a113-125">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a113-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a113-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a113-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a113-127">참조</span><span class="sxs-lookup"><span data-stu-id="9a113-127">See also</span></span>

- [<span data-ttu-id="9a113-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a113-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9a113-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a113-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="9a113-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a113-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="9a113-131">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a113-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9a113-132">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a113-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
