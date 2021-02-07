---
description: '자세히 알아보기: IHostManualEvent 인터페이스'
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
ms.openlocfilehash: 1c70935568b9ff4080fd5bcdc372c02d354aa06f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708166"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="00cb5-103">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-103">IHostManualEvent Interface</span></span>

<span data-ttu-id="00cb5-104">수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cb5-104">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00cb5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="00cb5-105">Methods</span></span>  
  
|<span data-ttu-id="00cb5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="00cb5-106">Method</span></span>|<span data-ttu-id="00cb5-107">설명</span><span class="sxs-lookup"><span data-stu-id="00cb5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00cb5-108">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="00cb5-108">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="00cb5-109">현재 인스턴스를 `IHostManualEvent` 신호를 받지 않는 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cb5-109">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="00cb5-110">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="00cb5-110">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="00cb5-111">현재 인스턴스를 `IHostManualEvent` 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cb5-111">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="00cb5-112">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="00cb5-112">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="00cb5-113">현재 `IHostManualEvent` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cb5-113">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00cb5-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00cb5-114">Requirements</span></span>  

 <span data-ttu-id="00cb5-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00cb5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00cb5-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="00cb5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00cb5-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cb5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00cb5-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00cb5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cb5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00cb5-119">See also</span></span>

- [<span data-ttu-id="00cb5-120">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-120">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="00cb5-121">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-121">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="00cb5-122">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-122">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="00cb5-123">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-123">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="00cb5-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00cb5-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
