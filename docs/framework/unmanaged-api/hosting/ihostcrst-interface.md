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
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804911"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="c0179-102">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0179-102">IHostCrst Interface</span></span>
<span data-ttu-id="c0179-103">스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0179-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-104">Methods</span></span>  
  
|<span data-ttu-id="c0179-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-105">Method</span></span>|<span data-ttu-id="c0179-106">Description</span><span class="sxs-lookup"><span data-stu-id="c0179-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0179-107">Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="c0179-108">임계 영역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="c0179-109">Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="c0179-110">임계 영역을 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="c0179-111">SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="c0179-112">임계 영역에 대 한 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="c0179-113">TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="c0179-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="c0179-114">임계 영역에 대 한 시작을 시도 하 고 성공 또는 실패를 즉시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0179-115">설명</span><span class="sxs-lookup"><span data-stu-id="c0179-115">Remarks</span></span>  
 <span data-ttu-id="c0179-116">`IHostCrst`CLR (공용 언어 런타임)이 또는와 같은 Win32 함수를 사용 하지 않고 중요 한 섹션의 호스트 표현과 직접 통신할 수 있도록 합니다 `EnterCriticalSection` `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="c0179-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0179-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0179-117">Requirements</span></span>  
 <span data-ttu-id="c0179-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0179-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0179-119">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c0179-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0179-120">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0179-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0179-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0179-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0179-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0179-122">See also</span></span>

- [<span data-ttu-id="c0179-123">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0179-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c0179-124">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0179-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="c0179-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0179-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
