---
title: IHostThreadPoolManager::GetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f4c2ea6deadeb0e9e1869a4ab064f2a948a74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749211"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="898e2-102">IHostThreadPoolManager::GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="898e2-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="898e2-103">요청에 대비 하 여에서 스레드 풀에서 호스트를 유지 관리 하는 유휴 상태 스레드의 최소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="898e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="898e2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="898e2-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="898e2-106">[out] 호스트에서 현재 유지 관리 하는 유휴 작업자 스레드의 최소 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="898e2-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="898e2-107">Return Value</span></span>  
  
|<span data-ttu-id="898e2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="898e2-108">HRESULT</span></span>|<span data-ttu-id="898e2-109">Description</span><span class="sxs-lookup"><span data-stu-id="898e2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="898e2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="898e2-110">S_OK</span></span>|<span data-ttu-id="898e2-111">`GetMinThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="898e2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="898e2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="898e2-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="898e2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="898e2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="898e2-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-115">The call timed out.</span></span>|  
|<span data-ttu-id="898e2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="898e2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="898e2-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="898e2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="898e2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="898e2-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="898e2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="898e2-120">E_FAIL</span></span>|<span data-ttu-id="898e2-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="898e2-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="898e2-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="898e2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="898e2-124">E_NOTIMPL</span></span>|<span data-ttu-id="898e2-125">호스트의 구현을 제공 하지 않습니다 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="898e2-126">설명</span><span class="sxs-lookup"><span data-stu-id="898e2-126">Remarks</span></span>  
 <span data-ttu-id="898e2-127">호스트의 구현을 제공 하지 않아도 됩니다 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="898e2-128">이 경우 E_NOTIMPL의 HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="898e2-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898e2-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="898e2-129">Requirements</span></span>  
 <span data-ttu-id="898e2-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="898e2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898e2-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="898e2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="898e2-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="898e2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="898e2-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898e2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898e2-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="898e2-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="898e2-135">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="898e2-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="898e2-136">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="898e2-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="898e2-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="898e2-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
