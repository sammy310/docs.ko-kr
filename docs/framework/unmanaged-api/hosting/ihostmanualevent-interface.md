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
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673204"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="01def-102">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-102">IHostManualEvent Interface</span></span>

<span data-ttu-id="01def-103">수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01def-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01def-104">메서드</span><span class="sxs-lookup"><span data-stu-id="01def-104">Methods</span></span>  
  
|<span data-ttu-id="01def-105">메서드</span><span class="sxs-lookup"><span data-stu-id="01def-105">Method</span></span>|<span data-ttu-id="01def-106">설명</span><span class="sxs-lookup"><span data-stu-id="01def-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01def-107">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="01def-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="01def-108">현재 인스턴스를 `IHostManualEvent` 신호를 받지 않는 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01def-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="01def-109">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="01def-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="01def-110">현재 인스턴스를 `IHostManualEvent` 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01def-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="01def-111">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="01def-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="01def-112">현재 `IHostManualEvent` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01def-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01def-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01def-113">Requirements</span></span>  

 <span data-ttu-id="01def-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01def-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01def-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01def-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01def-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01def-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01def-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01def-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01def-118">참조</span><span class="sxs-lookup"><span data-stu-id="01def-118">See also</span></span>

- [<span data-ttu-id="01def-119">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="01def-120">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="01def-121">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="01def-122">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="01def-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01def-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
