---
title: IHostSyncManager::CreateCrst 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
ms.openlocfilehash: 27861a9258916f4c188d981c44833e5be4c507f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682883"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="67c33-102">IHostSyncManager::CreateCrst 메서드</span><span class="sxs-lookup"><span data-stu-id="67c33-102">IHostSyncManager::CreateCrst Method</span></span>

<span data-ttu-id="67c33-103">동기화에 대 한 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c33-104">구문</span><span class="sxs-lookup"><span data-stu-id="67c33-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67c33-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67c33-105">Parameters</span></span>  

 `ppCrst`  
 <span data-ttu-id="67c33-106">제한이 호스트에서 구현 하는 [IHostCrst](ihostcrst-interface.md) 인스턴스의 주소에 대 한 포인터 이거나, 임계 영역을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c33-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="67c33-107">Return Value</span></span>  
  
|<span data-ttu-id="67c33-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67c33-108">HRESULT</span></span>|<span data-ttu-id="67c33-109">설명</span><span class="sxs-lookup"><span data-stu-id="67c33-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67c33-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67c33-110">S_OK</span></span>|<span data-ttu-id="67c33-111">`CreateCrst` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="67c33-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67c33-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67c33-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67c33-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67c33-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67c33-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-115">The call timed out.</span></span>|  
|<span data-ttu-id="67c33-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67c33-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67c33-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67c33-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67c33-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67c33-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67c33-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67c33-120">E_FAIL</span></span>|<span data-ttu-id="67c33-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67c33-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67c33-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67c33-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="67c33-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="67c33-125">요청한 임계 영역을 만드는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c33-126">설명</span><span class="sxs-lookup"><span data-stu-id="67c33-126">Remarks</span></span>  

 <span data-ttu-id="67c33-127">임계 영역 개체는 단일 프로세스의 스레드에서만 임계 영역을 사용할 수 있다는 점을 제외 하 고 뮤텍스 개체에서 제공 하는 것과 유사한 동기화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="67c33-128">`CreateCrst` Win32 함수를 미러링합니다 `InitializeCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="67c33-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c33-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67c33-129">Requirements</span></span>  

 <span data-ttu-id="67c33-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67c33-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c33-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67c33-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67c33-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67c33-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67c33-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c33-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c33-134">참조</span><span class="sxs-lookup"><span data-stu-id="67c33-134">See also</span></span>

- [<span data-ttu-id="67c33-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c33-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="67c33-136">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c33-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="67c33-137">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c33-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="67c33-138">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c33-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="67c33-139">뮤텍스</span><span class="sxs-lookup"><span data-stu-id="67c33-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="67c33-140">세마포 및 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="67c33-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
