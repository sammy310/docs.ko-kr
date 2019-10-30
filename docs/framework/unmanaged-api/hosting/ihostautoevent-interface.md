---
title: IHostAutoEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: 2b191243ea03adcfecaadbd3a5871e1773b28bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124460"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="a2236-102">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2236-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="a2236-103">자동 재설정 이벤트의 호스트 구현에 대 한 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2236-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2236-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a2236-104">Methods</span></span>  
  
|<span data-ttu-id="a2236-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a2236-105">Method</span></span>|<span data-ttu-id="a2236-106">설명</span><span class="sxs-lookup"><span data-stu-id="a2236-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2236-107">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="a2236-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="a2236-108">현재 `IHostAutoEvent` 인스턴스를 신호를 받은 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2236-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a2236-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="a2236-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="a2236-110">이벤트가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 현재 `IHostAutoEvent` 인스턴스가 대기 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2236-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2236-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2236-111">Requirements</span></span>  
 <span data-ttu-id="a2236-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2236-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2236-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a2236-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2236-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2236-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2236-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2236-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2236-116">참조</span><span class="sxs-lookup"><span data-stu-id="a2236-116">See also</span></span>

- [<span data-ttu-id="a2236-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2236-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a2236-118">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2236-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="a2236-119">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2236-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="a2236-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2236-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
