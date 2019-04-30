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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad580f7cab81323e09a24dc12db39f223be3aeb4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973071"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="5fc90-102">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="5fc90-103">호스트에서 구현 하는 수동 재설정 이벤트의 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc90-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fc90-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5fc90-104">Methods</span></span>  
  
|<span data-ttu-id="5fc90-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5fc90-105">Method</span></span>|<span data-ttu-id="5fc90-106">설명</span><span class="sxs-lookup"><span data-stu-id="5fc90-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fc90-107">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="5fc90-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="5fc90-108">현재 다시 설정 `IHostManualEvent` 신호 되지 않은 상태로 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5fc90-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="5fc90-109">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="5fc90-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="5fc90-110">에서는 현재 `IHostManualEvent` 신호를 받은 상태 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5fc90-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="5fc90-111">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="5fc90-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="5fc90-112">현재 `IHostManualEvent` 을 소유 하는 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5fc90-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fc90-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fc90-113">Requirements</span></span>  
 <span data-ttu-id="5fc90-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fc90-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc90-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5fc90-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5fc90-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5fc90-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fc90-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc90-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc90-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fc90-118">See also</span></span>

- [<span data-ttu-id="5fc90-119">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5fc90-120">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5fc90-121">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="5fc90-122">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="5fc90-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fc90-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
