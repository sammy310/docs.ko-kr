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
ms.openlocfilehash: a8642235cda359b849c49a35ab565397402c37d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130511"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="0ad0f-102">IHostCrst::SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="0ad0f-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="0ad0f-103">현재 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스의 회전 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ad0f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ad0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ad0f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="0ad0f-106">진행 현재 `IHostCrst` 인스턴스의 새 스핀 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ad0f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ad0f-107">Return Value</span></span>  
  
|<span data-ttu-id="0ad0f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ad0f-108">HRESULT</span></span>|<span data-ttu-id="0ad0f-109">설명</span><span class="sxs-lookup"><span data-stu-id="0ad0f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ad0f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ad0f-110">S_OK</span></span>|<span data-ttu-id="0ad0f-111">`SetSpinCount` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="0ad0f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ad0f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ad0f-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ad0f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ad0f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ad0f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ad0f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ad0f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ad0f-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ad0f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ad0f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ad0f-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ad0f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ad0f-120">E_FAIL</span></span>|<span data-ttu-id="0ad0f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ad0f-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ad0f-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad0f-124">주의</span><span class="sxs-lookup"><span data-stu-id="0ad0f-124">Remarks</span></span>  
 <span data-ttu-id="0ad0f-125">다중 프로세서 시스템에서 현재 `IHostCrst` 인스턴스로 표시 되는 임계 영역을 사용할 수 없는 경우 호출 스레드는 임계 영역에 연결 된 세마포에 대해 [IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) 를 호출 하기 전에 `dwSpinCount` 번 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="0ad0f-126">Spin 작업 중에 임계 영역을 사용할 수 없게 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="0ad0f-127">`dwSpinCount` 사용은 Win32 `InitializeCriticalSectionAndSpinCount` 함수에서 이름이 같은 매개 변수를 사용 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad0f-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ad0f-128">Requirements</span></span>  
 <span data-ttu-id="0ad0f-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad0f-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0ad0f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ad0f-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad0f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad0f-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad0f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad0f-133">참조</span><span class="sxs-lookup"><span data-stu-id="0ad0f-133">See also</span></span>

- [<span data-ttu-id="0ad0f-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ad0f-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0ad0f-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ad0f-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="0ad0f-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ad0f-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
