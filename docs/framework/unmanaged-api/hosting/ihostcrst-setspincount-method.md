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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca17a6814b56c0fe781cfb28a35a576f02f1943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090578"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="a7784-102">IHostCrst::SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="a7784-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="a7784-103">현재 회전 수를 설정 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a7784-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7784-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7784-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7784-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7784-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="a7784-106">[in] 현재 새 스핀 수 `IHostCrst` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a7784-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7784-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7784-107">Return Value</span></span>  
  
|<span data-ttu-id="a7784-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7784-108">HRESULT</span></span>|<span data-ttu-id="a7784-109">설명</span><span class="sxs-lookup"><span data-stu-id="a7784-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7784-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7784-110">S_OK</span></span>|<span data-ttu-id="a7784-111">`SetSpinCount` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="a7784-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a7784-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a7784-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a7784-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a7784-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a7784-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-115">The call timed out.</span></span>|  
|<span data-ttu-id="a7784-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a7784-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a7784-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a7784-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a7784-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a7784-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a7784-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7784-120">E_FAIL</span></span>|<span data-ttu-id="a7784-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a7784-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a7784-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7784-124">설명</span><span class="sxs-lookup"><span data-stu-id="a7784-124">Remarks</span></span>  
 <span data-ttu-id="a7784-125">다중 프로세서 시스템에서는 현재 표시 되는 중요 섹션 `IHostCrst` 인스턴스를 사용할 수 있는 호출 스레드에서 회전 `dwSpinCount` 호출 하기 전에 번 [ihostsemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) 연결 세마포에서 중요 한 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="a7784-126">중요 섹션 회전 작업 중에 무료 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="a7784-127">사용법 `dwSpinCount` Win32에 같은 이름의 매개 변수 사용에 동일 `InitializeCriticalSectionAndSpinCount` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7784-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7784-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7784-128">Requirements</span></span>  
 <span data-ttu-id="a7784-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a7784-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7784-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7784-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7784-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a7784-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7784-132">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7784-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7784-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7784-133">See also</span></span>

- [<span data-ttu-id="a7784-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7784-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a7784-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7784-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="a7784-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7784-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
