---
description: '자세히 알아보기: IHostCrst:: Leave 메서드'
title: IHostCrst::Leave 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: b00e62c7b2683ab6024a7c9b8de4645ceb59fb02
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708842"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="885e6-103">IHostCrst::Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="885e6-103">IHostCrst::Leave Method</span></span>

<span data-ttu-id="885e6-104">[IHostCrst](ihostcrst-interface.md)의 현재 인스턴스가 나타내는 임계 영역을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-104">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885e6-105">구문</span><span class="sxs-lookup"><span data-stu-id="885e6-105">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="885e6-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="885e6-106">Return Value</span></span>  
  
|<span data-ttu-id="885e6-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="885e6-107">HRESULT</span></span>|<span data-ttu-id="885e6-108">설명</span><span class="sxs-lookup"><span data-stu-id="885e6-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="885e6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="885e6-109">S_OK</span></span>|<span data-ttu-id="885e6-110">`Leave` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-110">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="885e6-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="885e6-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="885e6-112">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="885e6-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="885e6-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="885e6-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-114">The call timed out.</span></span>|  
|<span data-ttu-id="885e6-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="885e6-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="885e6-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="885e6-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="885e6-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="885e6-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="885e6-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="885e6-119">E_FAIL</span></span>|<span data-ttu-id="885e6-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="885e6-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="885e6-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="885e6-123">설명</span><span class="sxs-lookup"><span data-stu-id="885e6-123">Remarks</span></span>  

 <span data-ttu-id="885e6-124">`Leave` CLR이 해당 하는 Win32 함수를 사용 하는 대신 호스트의 스레딩 구현과 직접 통신할 수 있도록 합니다 `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="885e6-124">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="885e6-125">현재 인스턴스가 나타내는 임계 영역에 대 한 소유권을 가져오는 스레드는 `IHostCrst` `Leave` 해당 임계 영역에 진입할 때마다 한 번씩 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-125">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885e6-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="885e6-126">Requirements</span></span>  

 <span data-ttu-id="885e6-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="885e6-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885e6-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="885e6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="885e6-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="885e6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="885e6-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885e6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885e6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="885e6-131">See also</span></span>

- [<span data-ttu-id="885e6-132">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="885e6-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="885e6-133">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="885e6-133">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="885e6-134">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="885e6-134">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
