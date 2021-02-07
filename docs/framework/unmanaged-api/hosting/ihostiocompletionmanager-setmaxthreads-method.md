---
description: '자세히 알아보기: IHostIoCompletionManager:: SetMaxThreads 메서드'
title: IHostIoCompletionManager::SetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 6b36523b0b0d6cefba383d324eb23debefd7c41b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708283"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="0a6af-103">IHostIoCompletionManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="0a6af-103">IHostIoCompletionManager::SetMaxThreads Method</span></span>

<span data-ttu-id="0a6af-104">호스트에서 i/o 요청을 처리 하는 데 많은 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-104">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a6af-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a6af-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a6af-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a6af-106">Parameters</span></span>  

 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="0a6af-107">진행 I/o 요청에 대해 할당할 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-107">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a6af-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0a6af-108">Return Value</span></span>  
  
|<span data-ttu-id="0a6af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a6af-109">HRESULT</span></span>|<span data-ttu-id="0a6af-110">설명</span><span class="sxs-lookup"><span data-stu-id="0a6af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a6af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a6af-111">S_OK</span></span>|<span data-ttu-id="0a6af-112">`SetMaxThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-112">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="0a6af-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a6af-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a6af-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a6af-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a6af-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a6af-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-116">The call timed out.</span></span>|  
|<span data-ttu-id="0a6af-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a6af-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a6af-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a6af-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a6af-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a6af-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a6af-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a6af-121">E_FAIL</span></span>|<span data-ttu-id="0a6af-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a6af-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a6af-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0a6af-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0a6af-125">E_NOTIMPL</span></span>|<span data-ttu-id="0a6af-126">호스트는의 구현을 제공 하지 않습니다 `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="0a6af-126">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a6af-127">설명</span><span class="sxs-lookup"><span data-stu-id="0a6af-127">Remarks</span></span>  

 <span data-ttu-id="0a6af-128">`SetMaxThreads` CLR에 i/o 포트에서 서비스 요청에 사용할 수 있는 최대 스레드 수를 설정할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-128">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="0a6af-129">호스트는 구현, 성능 또는 확장성과 같은 이유로 스레드 풀의 크기를 독점적으로 제어 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-129">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="0a6af-130">따라서 호스트는를 구현할 필요가 없습니다 `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="0a6af-130">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="0a6af-131">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-131">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a6af-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a6af-132">Requirements</span></span>  

 <span data-ttu-id="0a6af-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a6af-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a6af-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0a6af-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a6af-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a6af-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a6af-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6af-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6af-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a6af-137">See also</span></span>

- [<span data-ttu-id="0a6af-138">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a6af-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0a6af-139">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a6af-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
