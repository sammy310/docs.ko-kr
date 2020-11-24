---
title: IHostIoCompletionManager::GetMaxThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
ms.openlocfilehash: 0b16305bc88854f1ab2ab89ab6b0d4d3e6881cf1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689473"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="03c2a-102">IHostIoCompletionManager::GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="03c2a-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>

<span data-ttu-id="03c2a-103">호스트가 i/o 요청을 처리 하기 위해 할당할 수 있는 최대 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03c2a-104">구문</span><span class="sxs-lookup"><span data-stu-id="03c2a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03c2a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03c2a-105">Parameters</span></span>  

 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="03c2a-106">제한이 호스트에서 i/o 요청을 처리 하기 위해 할당할 수 있는 스레드 풀의 최대 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03c2a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="03c2a-107">Return Value</span></span>  
  
|<span data-ttu-id="03c2a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03c2a-108">HRESULT</span></span>|<span data-ttu-id="03c2a-109">설명</span><span class="sxs-lookup"><span data-stu-id="03c2a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03c2a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="03c2a-110">S_OK</span></span>|<span data-ttu-id="03c2a-111">`GetMaxThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="03c2a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03c2a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03c2a-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03c2a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03c2a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03c2a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-115">The call timed out.</span></span>|  
|<span data-ttu-id="03c2a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03c2a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03c2a-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03c2a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03c2a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03c2a-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03c2a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03c2a-120">E_FAIL</span></span>|<span data-ttu-id="03c2a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03c2a-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03c2a-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="03c2a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="03c2a-124">E_NOTIMPL</span></span>|<span data-ttu-id="03c2a-125">호스트는의 구현을 제공 하지 않습니다 `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="03c2a-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03c2a-126">설명</span><span class="sxs-lookup"><span data-stu-id="03c2a-126">Remarks</span></span>  

 <span data-ttu-id="03c2a-127">호스트는 구현, 성능 또는 확장성과 같은 이유로 i/o 요청을 처리 하기 위해 할당할 수 있는 스레드 수에 대 한 배타적 제어를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="03c2a-128">따라서 호스트는를 구현할 필요가 없습니다 `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="03c2a-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="03c2a-129">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03c2a-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03c2a-130">Requirements</span></span>  

 <span data-ttu-id="03c2a-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03c2a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03c2a-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="03c2a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03c2a-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03c2a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03c2a-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03c2a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c2a-135">참조</span><span class="sxs-lookup"><span data-stu-id="03c2a-135">See also</span></span>

- [<span data-ttu-id="03c2a-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03c2a-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="03c2a-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03c2a-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
