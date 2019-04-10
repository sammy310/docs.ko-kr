---
title: IHostGCManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 238b054d240437df64a83a9c4daad34d4bd5d36a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228886"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="0edcd-102">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-102">IHostGCManager Interface</span></span>
<span data-ttu-id="0edcd-103">가비지 수집 메커니즘을 CLR (공용 언어 런타임)에 의해 구현에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edcd-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="0edcd-104">멤버</span><span class="sxs-lookup"><span data-stu-id="0edcd-104">Members</span></span>  
  
|<span data-ttu-id="0edcd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0edcd-105">Member</span></span>|<span data-ttu-id="0edcd-106">설명</span><span class="sxs-lookup"><span data-stu-id="0edcd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0edcd-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="0edcd-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="0edcd-108">CLR 가비지 수집을 위해 중단 된 스레드의 작업을 다시 시작 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0edcd-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="0edcd-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="0edcd-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="0edcd-110">CLR 가비지 수집을 수행 하기 위해 작업 실행을 중단 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0edcd-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="0edcd-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="0edcd-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="0edcd-112">메서드 호출이 만들어진 스레드는 호스트에 알리는 가비지 수집을 차단 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edcd-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0edcd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0edcd-113">Requirements</span></span>  
 <span data-ttu-id="0edcd-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0edcd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0edcd-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0edcd-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0edcd-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0edcd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0edcd-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0edcd-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0edcd-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0edcd-118">See also</span></span>

- [<span data-ttu-id="0edcd-119">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0edcd-120">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0edcd-121">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0edcd-122">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="0edcd-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0edcd-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
