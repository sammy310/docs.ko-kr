---
description: '자세히 알아보기: IHostCrst:: SetSpinCount 메서드'
title: IHostCrst::SetSpinCount 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: f04281d2649f210e64fc4c0585eb7d52be3e8ec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721231"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="41a7f-103">IHostCrst::SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="41a7f-103">IHostCrst::SetSpinCount Method</span></span>

<span data-ttu-id="41a7f-104">현재 [IHostCrst](ihostcrst-interface.md) 인스턴스의 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-104">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a7f-105">구문</span><span class="sxs-lookup"><span data-stu-id="41a7f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41a7f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41a7f-106">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="41a7f-107">진행 현재 인스턴스의 새 스핀 개수 `IHostCrst` 입니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-107">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41a7f-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="41a7f-108">Return Value</span></span>  
  
|<span data-ttu-id="41a7f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41a7f-109">HRESULT</span></span>|<span data-ttu-id="41a7f-110">설명</span><span class="sxs-lookup"><span data-stu-id="41a7f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="41a7f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="41a7f-111">S_OK</span></span>|<span data-ttu-id="41a7f-112">`SetSpinCount` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-112">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="41a7f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="41a7f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="41a7f-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="41a7f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="41a7f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="41a7f-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-116">The call timed out.</span></span>|  
|<span data-ttu-id="41a7f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="41a7f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="41a7f-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="41a7f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="41a7f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="41a7f-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="41a7f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41a7f-121">E_FAIL</span></span>|<span data-ttu-id="41a7f-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="41a7f-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="41a7f-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41a7f-125">설명</span><span class="sxs-lookup"><span data-stu-id="41a7f-125">Remarks</span></span>  

 <span data-ttu-id="41a7f-126">다중 프로세서 시스템에서 현재 인스턴스로 표시 되는 임계 영역을 `IHostCrst` 사용할 수 없는 경우 호출 스레드는 `dwSpinCount` 임계 영역에 연결 된 세마포에 대해 [IHostSemaphore:: Wait](ihostsemaphore-wait-method.md) 를 호출 하기 전에 시간을 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-126">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="41a7f-127">Spin 작업 중에 임계 영역을 사용할 수 없게 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-127">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="41a7f-128">를 사용 `dwSpinCount` 하는 것은 Win32 함수에서 동일한 이름의 매개 변수를 사용 하는 것과 동일 합니다 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="41a7f-128">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a7f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41a7f-129">Requirements</span></span>  

 <span data-ttu-id="41a7f-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41a7f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41a7f-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="41a7f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="41a7f-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41a7f-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41a7f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a7f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41a7f-134">See also</span></span>

- [<span data-ttu-id="41a7f-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41a7f-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="41a7f-136">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41a7f-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="41a7f-137">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41a7f-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
