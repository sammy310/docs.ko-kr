---
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
ms.openlocfilehash: 55727903a7f3c798e7472de6de5249de98af7ae7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804668"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="eec9b-102">IHostIoCompletionManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="eec9b-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="eec9b-103">호스트에서 i/o 요청을 처리 하는 데 많은 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="eec9b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eec9b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eec9b-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="eec9b-106">진행 I/o 요청에 대해 할당할 최대 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eec9b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="eec9b-107">Return Value</span></span>  
  
|<span data-ttu-id="eec9b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eec9b-108">HRESULT</span></span>|<span data-ttu-id="eec9b-109">Description</span><span class="sxs-lookup"><span data-stu-id="eec9b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eec9b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eec9b-110">S_OK</span></span>|<span data-ttu-id="eec9b-111">`SetMaxThreads`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="eec9b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eec9b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eec9b-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eec9b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eec9b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eec9b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-115">The call timed out.</span></span>|  
|<span data-ttu-id="eec9b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eec9b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eec9b-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eec9b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eec9b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eec9b-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eec9b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eec9b-120">E_FAIL</span></span>|<span data-ttu-id="eec9b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eec9b-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eec9b-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eec9b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="eec9b-124">E_NOTIMPL</span></span>|<span data-ttu-id="eec9b-125">호스트는의 구현을 제공 하지 않습니다 `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="eec9b-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eec9b-126">설명</span><span class="sxs-lookup"><span data-stu-id="eec9b-126">Remarks</span></span>  
 <span data-ttu-id="eec9b-127">`SetMaxThreads`CLR에 i/o 포트에서 서비스 요청에 사용할 수 있는 최대 스레드 수를 설정할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="eec9b-128">호스트는 구현, 성능 또는 확장성과 같은 이유로 스레드 풀의 크기를 독점적으로 제어 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="eec9b-129">따라서 호스트는를 구현할 필요가 없습니다 `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="eec9b-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="eec9b-130">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eec9b-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eec9b-131">Requirements</span></span>  
 <span data-ttu-id="eec9b-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eec9b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eec9b-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eec9b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eec9b-134">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eec9b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eec9b-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eec9b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec9b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eec9b-136">See also</span></span>

- [<span data-ttu-id="eec9b-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eec9b-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="eec9b-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eec9b-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
