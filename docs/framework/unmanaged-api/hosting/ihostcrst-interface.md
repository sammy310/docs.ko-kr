---
description: '자세히 알아보기: IHostCrst 인터페이스'
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
ms.openlocfilehash: 7945f0087667c1d610a1a2370528b055af74d579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708881"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="1eab9-103">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eab9-103">IHostCrst Interface</span></span>

<span data-ttu-id="1eab9-104">스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-104">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1eab9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-105">Methods</span></span>  
  
|<span data-ttu-id="1eab9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-106">Method</span></span>|<span data-ttu-id="1eab9-107">설명</span><span class="sxs-lookup"><span data-stu-id="1eab9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1eab9-108">Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-108">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="1eab9-109">임계 영역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-109">Enters the critical section.</span></span>|  
|[<span data-ttu-id="1eab9-110">Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-110">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="1eab9-111">임계 영역을 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-111">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="1eab9-112">SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-112">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="1eab9-113">임계 영역에 대 한 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-113">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="1eab9-114">TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="1eab9-114">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="1eab9-115">임계 영역에 대 한 시작을 시도 하 고 성공 또는 실패를 즉시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-115">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eab9-116">설명</span><span class="sxs-lookup"><span data-stu-id="1eab9-116">Remarks</span></span>  

 <span data-ttu-id="1eab9-117">`IHostCrst` CLR (공용 언어 런타임)이 또는와 같은 Win32 함수를 사용 하지 않고 중요 한 섹션의 호스트 표현과 직접 통신할 수 있도록 합니다 `EnterCriticalSection` `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="1eab9-117">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eab9-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eab9-118">Requirements</span></span>  

 <span data-ttu-id="1eab9-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eab9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eab9-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1eab9-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1eab9-121">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eab9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1eab9-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eab9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eab9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eab9-123">See also</span></span>

- [<span data-ttu-id="1eab9-124">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eab9-124">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="1eab9-125">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eab9-125">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="1eab9-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eab9-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
