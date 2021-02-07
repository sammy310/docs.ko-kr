---
description: '자세히 알아보기: IHostThreadPoolManager:: SetMaxThreads 메서드'
title: IHostThreadPoolManager::SetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
ms.openlocfilehash: 83266b05f639c0aa63e492bca525cbbf09a30775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671245"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="35266-103">IHostThreadPoolManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="35266-103">IHostThreadPoolManager::SetMaxThreads Method</span></span>

<span data-ttu-id="35266-104">호스트가 스레드 풀에서 유지 관리할 수 있는 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35266-104">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35266-105">구문</span><span class="sxs-lookup"><span data-stu-id="35266-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35266-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35266-106">Parameters</span></span>  

 `MaxThreads`  
 <span data-ttu-id="35266-107">스레드 풀에 있는 최대 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35266-107">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35266-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="35266-108">Return Value</span></span>  
  
|<span data-ttu-id="35266-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35266-109">HRESULT</span></span>|<span data-ttu-id="35266-110">설명</span><span class="sxs-lookup"><span data-stu-id="35266-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35266-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="35266-111">S_OK</span></span>|<span data-ttu-id="35266-112">`SetMaxThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-112">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="35266-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35266-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35266-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35266-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35266-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35266-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-116">The call timed out.</span></span>|  
|<span data-ttu-id="35266-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35266-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35266-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35266-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35266-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35266-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35266-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35266-121">E_FAIL</span></span>|<span data-ttu-id="35266-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="35266-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35266-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35266-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="35266-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="35266-125">E_NOTIMPL</span></span>|<span data-ttu-id="35266-126">호스트는의 구현을 제공 하지 않습니다 `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="35266-126">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35266-127">설명</span><span class="sxs-lookup"><span data-stu-id="35266-127">Remarks</span></span>  

 <span data-ttu-id="35266-128">CLR에서 스레드 풀의 크기를 구성할 수 있도록 하려면 호스트가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-128">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="35266-129">일부 호스트는 구현, 성능 또는 확장성과 같은 이유로 스레드 풀을 독점적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35266-129">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="35266-130">이 경우 호스트는 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35266-130">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35266-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35266-131">Requirements</span></span>  

 <span data-ttu-id="35266-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35266-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35266-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="35266-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35266-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35266-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35266-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35266-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35266-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35266-136">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="35266-137">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="35266-137">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="35266-138">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="35266-138">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="35266-139">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35266-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
