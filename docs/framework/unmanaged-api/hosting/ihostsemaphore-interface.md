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
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803698"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="f96ee-102">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="f96ee-103">스레딩을 위한 호스트의 세마포 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f96ee-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f96ee-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f96ee-104">Methods</span></span>  
  
|<span data-ttu-id="f96ee-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f96ee-105">Method</span></span>|<span data-ttu-id="f96ee-106">Description</span><span class="sxs-lookup"><span data-stu-id="f96ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f96ee-107">ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="f96ee-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="f96ee-108">현재 인스턴스의 개수를 지정 된 `IHostSemaphore` 양만큼 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="f96ee-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="f96ee-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="f96ee-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="f96ee-110">현재 `IHostSemaphore` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96ee-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f96ee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f96ee-111">Requirements</span></span>  
 <span data-ttu-id="f96ee-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f96ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f96ee-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f96ee-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f96ee-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96ee-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f96ee-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f96ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96ee-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f96ee-116">See also</span></span>

- [<span data-ttu-id="f96ee-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f96ee-118">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="f96ee-119">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="f96ee-120">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="f96ee-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f96ee-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
