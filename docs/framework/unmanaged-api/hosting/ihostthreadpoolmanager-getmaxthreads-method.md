---
title: IHostThreadPoolManager::GetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842285"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="52d6c-102">IHostThreadPoolManager::GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="52d6c-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="52d6c-103">호스트가 스레드 풀에서 동시에 유지 관리 하는 최대 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d6c-104">구문</span><span class="sxs-lookup"><span data-stu-id="52d6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d6c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52d6c-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="52d6c-106">제한이 호스트가 스레드 풀에서 유지 관리 하는 최대 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52d6c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="52d6c-107">Return Value</span></span>  
  
|<span data-ttu-id="52d6c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52d6c-108">HRESULT</span></span>|<span data-ttu-id="52d6c-109">Description</span><span class="sxs-lookup"><span data-stu-id="52d6c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52d6c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52d6c-110">S_OK</span></span>|<span data-ttu-id="52d6c-111">`GetMaxThreads`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="52d6c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52d6c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52d6c-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52d6c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52d6c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52d6c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-115">The call timed out.</span></span>|  
|<span data-ttu-id="52d6c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52d6c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52d6c-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52d6c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52d6c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52d6c-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52d6c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52d6c-120">E_FAIL</span></span>|<span data-ttu-id="52d6c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52d6c-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52d6c-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52d6c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="52d6c-124">E_NOTIMPL</span></span>|<span data-ttu-id="52d6c-125">호스트는의 구현을 제공 하지 않습니다 `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="52d6c-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52d6c-126">설명</span><span class="sxs-lookup"><span data-stu-id="52d6c-126">Remarks</span></span>  
 <span data-ttu-id="52d6c-127">CLR은 `GetMaxThreads` 를 호출 하 여 스레드 풀의 총 스레드 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="52d6c-128">[Get사용할](ihostthreadpoolmanager-getavailablethreads-method.md) 수 있는 threads 메서드는 현재 작업 항목을 처리 하 고 있지 않은 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-128">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="52d6c-129">반환 된 매개 변수의 값을 초과 하는 모든 요청은 `pdwMaxWorkerThreads` 스레드를 사용할 수 있을 때까지 큐에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="52d6c-130">호스트에서의 구현을 제공 하지 않는 경우 `GetMaxThreads` E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d6c-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52d6c-131">Requirements</span></span>  
 <span data-ttu-id="52d6c-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52d6c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d6c-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="52d6c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52d6c-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52d6c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52d6c-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d6c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d6c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52d6c-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="52d6c-137">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="52d6c-137">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="52d6c-138">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="52d6c-138">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="52d6c-139">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52d6c-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
