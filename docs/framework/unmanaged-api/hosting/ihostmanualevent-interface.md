---
title: IHostManualEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136788"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="aa9d9-102">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="aa9d9-103">수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa9d9-104">메서드</span><span class="sxs-lookup"><span data-stu-id="aa9d9-104">Methods</span></span>  
  
|<span data-ttu-id="aa9d9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="aa9d9-105">Method</span></span>|<span data-ttu-id="aa9d9-106">설명</span><span class="sxs-lookup"><span data-stu-id="aa9d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa9d9-107">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="aa9d9-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="aa9d9-108">현재 `IHostManualEvent` 인스턴스를 신호를 받지 않는 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="aa9d9-109">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="aa9d9-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="aa9d9-110">현재 `IHostManualEvent` 인스턴스를 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="aa9d9-111">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="aa9d9-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="aa9d9-112">현재 `IHostManualEvent` 인스턴스가 소유 될 때까지 기다리거나 지정 된 시간이 경과할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa9d9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa9d9-113">Requirements</span></span>  
 <span data-ttu-id="aa9d9-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa9d9-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aa9d9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa9d9-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa9d9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa9d9-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa9d9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa9d9-118">참조</span><span class="sxs-lookup"><span data-stu-id="aa9d9-118">See also</span></span>

- [<span data-ttu-id="aa9d9-119">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="aa9d9-120">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="aa9d9-121">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="aa9d9-122">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="aa9d9-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa9d9-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
