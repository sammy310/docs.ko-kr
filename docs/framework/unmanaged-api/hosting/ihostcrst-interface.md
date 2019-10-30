---
title: IHostCrst 인터페이스
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130520"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="3b737-102">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b737-102">IHostCrst Interface</span></span>
<span data-ttu-id="3b737-103">스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b737-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-104">Methods</span></span>  
  
|<span data-ttu-id="3b737-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-105">Method</span></span>|<span data-ttu-id="3b737-106">설명</span><span class="sxs-lookup"><span data-stu-id="3b737-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b737-107">Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="3b737-108">임계 영역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="3b737-109">Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="3b737-110">임계 영역을 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="3b737-111">SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="3b737-112">임계 영역에 대 한 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="3b737-113">TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="3b737-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="3b737-114">임계 영역에 대 한 시작을 시도 하 고 성공 또는 실패를 즉시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b737-115">주의</span><span class="sxs-lookup"><span data-stu-id="3b737-115">Remarks</span></span>  
 <span data-ttu-id="3b737-116">`IHostCrst`를 사용 하면 CLR (공용 언어 런타임)이 `EnterCriticalSection` 또는 `LeaveCriticalSection`같은 Win32 함수를 사용 하는 대신 CLR (공용 언어 런타임)에서 중요 한 섹션의 호스트 표현과 직접 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b737-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b737-117">Requirements</span></span>  
 <span data-ttu-id="3b737-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b737-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b737-119">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3b737-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b737-120">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b737-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b737-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b737-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b737-122">참조</span><span class="sxs-lookup"><span data-stu-id="3b737-122">See also</span></span>

- [<span data-ttu-id="3b737-123">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b737-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3b737-124">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b737-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="3b737-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b737-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
