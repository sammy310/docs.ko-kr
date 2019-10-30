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
ms.openlocfilehash: 2cf490bcd167b7a498ae21f479f616694ccb5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139474"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="3f6bf-102">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="3f6bf-103">스레딩을 위한 호스트의 세마포 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f6bf-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f6bf-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3f6bf-104">Methods</span></span>  
  
|<span data-ttu-id="3f6bf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3f6bf-105">Method</span></span>|<span data-ttu-id="3f6bf-106">설명</span><span class="sxs-lookup"><span data-stu-id="3f6bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f6bf-107">ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="3f6bf-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="3f6bf-108">지정 된 크기 만큼 현재 `IHostSemaphore` 인스턴스의 수를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="3f6bf-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="3f6bf-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="3f6bf-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="3f6bf-110">현재 `IHostSemaphore` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f6bf-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f6bf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f6bf-111">Requirements</span></span>  
 <span data-ttu-id="3f6bf-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f6bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f6bf-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3f6bf-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f6bf-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f6bf-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f6bf-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f6bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6bf-116">참조</span><span class="sxs-lookup"><span data-stu-id="3f6bf-116">See also</span></span>

- [<span data-ttu-id="3f6bf-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3f6bf-118">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="3f6bf-119">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="3f6bf-120">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="3f6bf-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f6bf-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
