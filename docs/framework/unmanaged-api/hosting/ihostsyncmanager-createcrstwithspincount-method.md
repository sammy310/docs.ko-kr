---
description: '자세히 알아보기: IHostSyncManager:: CreateCrstWithSpinCount 메서드'
title: IHostSyncManager::CreateCrstWithSpinCount 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
ms.openlocfilehash: 3c43f1a3d52eb7174844ecb4079cf54413f20853
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784823"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="fb975-103">IHostSyncManager::CreateCrstWithSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="fb975-103">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>

<span data-ttu-id="fb975-104">동기화에 대 한 회전 수를 사용 하 여 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-104">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb975-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb975-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb975-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb975-106">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="fb975-107">진행 임계 영역 개체의 회전 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-107">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="fb975-108">제한이 [IHostCrst](ihostcrst-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 임계 영역을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-108">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb975-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="fb975-109">Return Value</span></span>  
  
|<span data-ttu-id="fb975-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb975-110">HRESULT</span></span>|<span data-ttu-id="fb975-111">설명</span><span class="sxs-lookup"><span data-stu-id="fb975-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb975-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb975-112">S_OK</span></span>|<span data-ttu-id="fb975-113">`CreateCrstWithSpinCount` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-113">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="fb975-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb975-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb975-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb975-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb975-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb975-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-117">The call timed out.</span></span>|  
|<span data-ttu-id="fb975-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb975-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb975-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb975-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb975-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb975-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fb975-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb975-122">E_FAIL</span></span>|<span data-ttu-id="fb975-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb975-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb975-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fb975-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fb975-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fb975-127">요청한 임계 영역을 만드는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-127">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb975-128">설명</span><span class="sxs-lookup"><span data-stu-id="fb975-128">Remarks</span></span>  

 <span data-ttu-id="fb975-129">스핀 수는 다중 프로세서 시스템 에서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-129">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="fb975-130">스핀 카운트는 사용할 수 없는 임계 영역에 연결 된 세마포에서 대기 작업을 수행 하기 전에 호출 스레드를 회전 해야 하는 횟수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-130">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="fb975-131">Spin 작업 중에 임계 영역을 사용할 수 없게 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-131">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="fb975-132">`CreateCrstWithSpinCount` Win32 함수를 미러링합니다 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="fb975-132">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb975-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb975-133">Requirements</span></span>  

 <span data-ttu-id="fb975-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb975-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb975-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb975-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb975-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb975-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb975-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb975-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb975-138">See also</span></span>

- [<span data-ttu-id="fb975-139">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb975-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="fb975-140">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb975-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="fb975-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb975-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
