---
description: '자세히 알아보기: IHostIoCompletionManager:: GetMinThreads 메서드'
title: IHostIoCompletionManager::GetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: 73b8d8cbff3777fe6aa956f282d3da5d4ac1b5c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708520"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="b8773-103">IHostIoCompletionManager::GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="b8773-103">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="b8773-104">호스트에서 i/o 요청을 처리 하기 위해 제공 하는 최소 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-104">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8773-105">구문</span><span class="sxs-lookup"><span data-stu-id="b8773-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8773-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8773-106">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="b8773-107">제한이 호스트에서 i/o 요청을 처리 하기 위해 제공 하는 최소 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-107">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8773-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="b8773-108">Return Value</span></span>  
  
|<span data-ttu-id="b8773-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8773-109">HRESULT</span></span>|<span data-ttu-id="b8773-110">설명</span><span class="sxs-lookup"><span data-stu-id="b8773-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8773-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8773-111">S_OK</span></span>|<span data-ttu-id="b8773-112">`GetMinThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-112">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b8773-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8773-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8773-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8773-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b8773-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b8773-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-116">The call timed out.</span></span>|  
|<span data-ttu-id="b8773-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8773-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b8773-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b8773-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b8773-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b8773-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b8773-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8773-121">E_FAIL</span></span>|<span data-ttu-id="b8773-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8773-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8773-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b8773-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b8773-125">E_NOTIMPL</span></span>|<span data-ttu-id="b8773-126">호스트는의 구현을 제공 하지 않습니다 `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b8773-126">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8773-127">설명</span><span class="sxs-lookup"><span data-stu-id="b8773-127">Remarks</span></span>  

 <span data-ttu-id="b8773-128">호스트는 구현, 성능 또는 확장성과 같은 이유로 서비스 i/o 요청에 할당 된 스레드 수에 대 한 배타적 제어를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-128">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b8773-129">따라서 호스트는를 구현할 필요가 없습니다 `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b8773-129">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="b8773-130">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8773-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8773-131">Requirements</span></span>  

 <span data-ttu-id="b8773-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8773-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8773-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b8773-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8773-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8773-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8773-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8773-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8773-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8773-136">See also</span></span>

- [<span data-ttu-id="b8773-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8773-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b8773-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8773-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
