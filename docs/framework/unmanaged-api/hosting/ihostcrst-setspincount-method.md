---
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
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804876"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="76feb-102">IHostCrst::SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="76feb-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="76feb-103">현재 [IHostCrst](ihostcrst-interface.md) 인스턴스의 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76feb-104">구문</span><span class="sxs-lookup"><span data-stu-id="76feb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76feb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76feb-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="76feb-106">진행 현재 인스턴스의 새 스핀 개수 `IHostCrst` 입니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76feb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="76feb-107">Return Value</span></span>  
  
|<span data-ttu-id="76feb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76feb-108">HRESULT</span></span>|<span data-ttu-id="76feb-109">Description</span><span class="sxs-lookup"><span data-stu-id="76feb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76feb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76feb-110">S_OK</span></span>|<span data-ttu-id="76feb-111">`SetSpinCount`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="76feb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76feb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76feb-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76feb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76feb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76feb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-115">The call timed out.</span></span>|  
|<span data-ttu-id="76feb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76feb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76feb-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76feb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76feb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76feb-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76feb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76feb-120">E_FAIL</span></span>|<span data-ttu-id="76feb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76feb-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76feb-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76feb-124">설명</span><span class="sxs-lookup"><span data-stu-id="76feb-124">Remarks</span></span>  
 <span data-ttu-id="76feb-125">다중 프로세서 시스템에서 현재 인스턴스로 표시 되는 임계 영역을 `IHostCrst` 사용할 수 없는 경우 호출 스레드는 `dwSpinCount` 임계 영역에 연결 된 세마포에 대해 [IHostSemaphore:: Wait](ihostsemaphore-wait-method.md) 를 호출 하기 전에 시간을 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="76feb-126">Spin 작업 중에 임계 영역을 사용할 수 없게 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="76feb-127">를 사용 `dwSpinCount` 하는 것은 Win32 함수에서 동일한 이름의 매개 변수를 사용 하는 것과 동일 합니다 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="76feb-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76feb-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76feb-128">Requirements</span></span>  
 <span data-ttu-id="76feb-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76feb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76feb-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="76feb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76feb-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76feb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76feb-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76feb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76feb-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76feb-133">See also</span></span>

- [<span data-ttu-id="76feb-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76feb-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="76feb-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76feb-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="76feb-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76feb-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
