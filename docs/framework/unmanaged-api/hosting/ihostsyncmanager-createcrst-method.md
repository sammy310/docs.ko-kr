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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b63b283a28ed27a70698c45bdc87d63fef0daf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117951"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="328f4-102">IHostSyncManager::CreateCrst 메서드</span><span class="sxs-lookup"><span data-stu-id="328f4-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="328f4-103">동기화에 대 한 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="328f4-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="328f4-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="328f4-106">[out] 주소에 대 한 포인터를 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스 호스트에 의해 구현 되거나 중요 섹션을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="328f4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="328f4-107">Return Value</span></span>  
  
|<span data-ttu-id="328f4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="328f4-108">HRESULT</span></span>|<span data-ttu-id="328f4-109">설명</span><span class="sxs-lookup"><span data-stu-id="328f4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="328f4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="328f4-110">S_OK</span></span>|`CreateCrst` <span data-ttu-id="328f4-111">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-111">returned successfully.</span></span>|  
|<span data-ttu-id="328f4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="328f4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="328f4-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="328f4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="328f4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="328f4-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-115">The call timed out.</span></span>|  
|<span data-ttu-id="328f4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="328f4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="328f4-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="328f4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="328f4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="328f4-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="328f4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="328f4-120">E_FAIL</span></span>|<span data-ttu-id="328f4-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="328f4-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="328f4-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="328f4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="328f4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="328f4-125">메모리가 부족 하 여 요청된 된 중요 한 섹션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="328f4-126">설명</span><span class="sxs-lookup"><span data-stu-id="328f4-126">Remarks</span></span>  
 <span data-ttu-id="328f4-127">임계 영역 개체 제외 하 고 중요 한 섹션 에서도 사용할 수 있습니다만 단일 프로세스의 스레드가 뮤텍스 개체를 제공 하는 유사한 동기화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> `CreateCrst` <span data-ttu-id="328f4-128">Win32의 미러링 `InitializeCriticalSection` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="328f4-128">mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328f4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="328f4-129">Requirements</span></span>  
 <span data-ttu-id="328f4-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="328f4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="328f4-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="328f4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="328f4-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="328f4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="328f4-133">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="328f4-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="328f4-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="328f4-134">See also</span></span>

- [<span data-ttu-id="328f4-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="328f4-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="328f4-136">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="328f4-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="328f4-137">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="328f4-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="328f4-138">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="328f4-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="328f4-139">뮤텍스</span><span class="sxs-lookup"><span data-stu-id="328f4-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="328f4-140">세마포 및 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="328f4-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
