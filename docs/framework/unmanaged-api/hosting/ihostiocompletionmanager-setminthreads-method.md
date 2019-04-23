---
title: IHostIoCompletionManager::SetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fd37546c63ef5e5f25686e105247555dfeb132a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222785"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="ba0a8-102">IHostIoCompletionManager::SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ba0a8-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="ba0a8-103">I/O 완료 될 때까지 호스트를 할당 해야 하는 스레드의 최소 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba0a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba0a8-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba0a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba0a8-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="ba0a8-106">[in] 호스트를 만들어야 하는 I/O 완료 스레드의 최소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba0a8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ba0a8-107">Return Value</span></span>  
  
|<span data-ttu-id="ba0a8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba0a8-108">HRESULT</span></span>|<span data-ttu-id="ba0a8-109">설명</span><span class="sxs-lookup"><span data-stu-id="ba0a8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba0a8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba0a8-110">S_OK</span></span>|<span data-ttu-id="ba0a8-111">`SetMinThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ba0a8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba0a8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba0a8-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba0a8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba0a8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba0a8-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-115">The call timed out.</span></span>|  
|<span data-ttu-id="ba0a8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba0a8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba0a8-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba0a8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba0a8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba0a8-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba0a8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba0a8-120">E_FAIL</span></span>|<span data-ttu-id="ba0a8-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba0a8-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba0a8-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ba0a8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ba0a8-124">E_NOTIMPL</span></span>|<span data-ttu-id="ba0a8-125">호스트의 구현을 제공 하지 않습니다 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba0a8-126">설명</span><span class="sxs-lookup"><span data-stu-id="ba0a8-126">Remarks</span></span>  
 <span data-ttu-id="ba0a8-127">호스트 구현, 성능, 확장성 등의 이유로 I/O 요청을 처리 하는 데 할당 될 스레드의 수에 대 한 독점적인 제어권이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ba0a8-128">이러한 이유로 호스트는 구현할 필요가 없습니다 `SetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="ba0a8-129">이 경우 호스트는이 메서드의 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba0a8-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba0a8-130">Requirements</span></span>  
 <span data-ttu-id="ba0a8-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba0a8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba0a8-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba0a8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba0a8-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ba0a8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba0a8-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba0a8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0a8-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba0a8-135">See also</span></span>

- [<span data-ttu-id="ba0a8-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba0a8-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ba0a8-137">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ba0a8-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="ba0a8-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba0a8-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
