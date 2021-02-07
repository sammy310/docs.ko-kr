---
description: '자세히 알아보기: IHostSemaphore 인터페이스'
title: IHostSemaphore 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 682f1f70925310e93f88f1dc314052e801a5e87b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671349"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="a1139-103">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-103">IHostSemaphore Interface</span></span>

<span data-ttu-id="a1139-104">스레딩을 위한 호스트의 세마포 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1139-104">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1139-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a1139-105">Methods</span></span>  
  
|<span data-ttu-id="a1139-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a1139-106">Method</span></span>|<span data-ttu-id="a1139-107">설명</span><span class="sxs-lookup"><span data-stu-id="a1139-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1139-108">ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="a1139-108">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="a1139-109">현재 인스턴스의 개수를 지정 된 `IHostSemaphore` 양만큼 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="a1139-109">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="a1139-110">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="a1139-110">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="a1139-111">현재 `IHostSemaphore` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1139-111">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1139-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1139-112">Requirements</span></span>  

 <span data-ttu-id="a1139-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1139-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1139-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a1139-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1139-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1139-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1139-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1139-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1139-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1139-117">See also</span></span>

- [<span data-ttu-id="a1139-118">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-118">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a1139-119">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-119">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="a1139-120">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-120">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="a1139-121">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="a1139-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1139-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
