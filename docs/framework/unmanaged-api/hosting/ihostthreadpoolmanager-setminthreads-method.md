---
title: IHostThreadPoolManager::SetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed172ca9f10e941938ae43bd730a3fc6d658aca2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484643"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="1974a-102">IHostThreadPoolManager::SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="1974a-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="1974a-103">요청에 대비 하 여에서 호스트를 유지 해야 하는 유휴 상태 스레드의 최소 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1974a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1974a-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1974a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1974a-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="1974a-106">[in] 호스트를 유지 해야 하는 스레드의 새 최소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1974a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1974a-107">Return Value</span></span>  
  
|<span data-ttu-id="1974a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1974a-108">HRESULT</span></span>|<span data-ttu-id="1974a-109">설명</span><span class="sxs-lookup"><span data-stu-id="1974a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1974a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1974a-110">S_OK</span></span>|<span data-ttu-id="1974a-111">`SetMinThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1974a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1974a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1974a-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1974a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1974a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1974a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-115">The call timed out.</span></span>|  
|<span data-ttu-id="1974a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1974a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1974a-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1974a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1974a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1974a-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1974a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1974a-120">E_FAIL</span></span>|<span data-ttu-id="1974a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1974a-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1974a-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1974a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1974a-124">E_NOTIMPL</span></span>|<span data-ttu-id="1974a-125">호스트의 구현을 제공 하지 않습니다 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1974a-126">설명</span><span class="sxs-lookup"><span data-stu-id="1974a-126">Remarks</span></span>  
 <span data-ttu-id="1974a-127">호스트의 구현을 제공 하지 않아도 됩니다 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="1974a-128">이 경우 E_NOTIMPL의 HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1974a-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1974a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1974a-129">Requirements</span></span>  
 <span data-ttu-id="1974a-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1974a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1974a-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1974a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1974a-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1974a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1974a-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1974a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1974a-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="1974a-134">See also</span></span>
- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1974a-135">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="1974a-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="1974a-136">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="1974a-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="1974a-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1974a-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
