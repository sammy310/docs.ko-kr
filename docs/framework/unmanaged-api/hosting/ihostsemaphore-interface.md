---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182288"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="767de-102">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="767de-103">세마포 스레딩에 대 한 호스트의 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="767de-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="767de-104">메서드</span><span class="sxs-lookup"><span data-stu-id="767de-104">Methods</span></span>  
  
|<span data-ttu-id="767de-105">메서드</span><span class="sxs-lookup"><span data-stu-id="767de-105">Method</span></span>|<span data-ttu-id="767de-106">설명</span><span class="sxs-lookup"><span data-stu-id="767de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="767de-107">ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="767de-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="767de-108">현재 개수를 증가 `IHostSemaphore` 인스턴스에 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="767de-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="767de-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="767de-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="767de-110">현재 `IHostSemaphore` 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 양의 시간 간격이 경과 합니다.</span><span class="sxs-lookup"><span data-stu-id="767de-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="767de-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="767de-111">Requirements</span></span>  
 <span data-ttu-id="767de-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="767de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767de-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="767de-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="767de-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="767de-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="767de-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="767de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767de-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="767de-116">See also</span></span>

- [<span data-ttu-id="767de-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="767de-118">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="767de-119">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="767de-120">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="767de-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="767de-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
