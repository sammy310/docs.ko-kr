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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d5b865906f797c25783c4d8a306dc91769ef9a9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749283"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="417ef-102">IHostThreadPoolManager::GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="417ef-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="417ef-103">스레드 풀에 동시에 호스트를 유지 하는 스레드의 최대 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="417ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="417ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="417ef-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="417ef-106">[out] 스레드 풀에서 호스트를 유지 하는 스레드의 최대 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="417ef-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="417ef-107">Return Value</span></span>  
  
|<span data-ttu-id="417ef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="417ef-108">HRESULT</span></span>|<span data-ttu-id="417ef-109">Description</span><span class="sxs-lookup"><span data-stu-id="417ef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="417ef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="417ef-110">S_OK</span></span>|<span data-ttu-id="417ef-111">`GetMaxThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="417ef-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="417ef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="417ef-113">공용 언어 런타임 (CLR (프로세스에 로드 되지 않은 또는 CLR 상태에서는 실행할 수 없습니다 관리 코드 또는 프로세스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="417ef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="417ef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="417ef-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-115">The call timed out.</span></span>|  
|<span data-ttu-id="417ef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="417ef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="417ef-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="417ef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="417ef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="417ef-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="417ef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="417ef-120">E_FAIL</span></span>|<span data-ttu-id="417ef-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="417ef-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="417ef-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="417ef-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="417ef-124">E_NOTIMPL</span></span>|<span data-ttu-id="417ef-125">호스트의 구현을 제공 하지 않습니다 `GetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="417ef-126">설명</span><span class="sxs-lookup"><span data-stu-id="417ef-126">Remarks</span></span>  
 <span data-ttu-id="417ef-127">CLR에서는 `GetMaxThreads` 스레드 풀의 스레드의 총 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="417ef-128">합니다 [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) 메서드는 작업 항목을 현재 처리 되지 않습니다. 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="417ef-129">반환 된 값 보다 큰 모든 요청은 `pdwMaxWorkerThreads` 매개 변수 중인 스레드가 사용 가능 해질 때까지 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="417ef-130">호스트의 구현을 제공 하지 않는 경우 `GetMaxThreads`, e_notimpl HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="417ef-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="417ef-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="417ef-131">Requirements</span></span>  
 <span data-ttu-id="417ef-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="417ef-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="417ef-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="417ef-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="417ef-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="417ef-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="417ef-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="417ef-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417ef-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="417ef-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="417ef-137">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="417ef-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="417ef-138">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="417ef-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="417ef-139">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="417ef-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
