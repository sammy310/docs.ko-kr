---
description: '자세히 알아보기: IHostIoCompletionManager:: Get Threads 메서드'
title: IHostIoCompletionManager::GetAvailableThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: d50f79716f72b902102a2a97a0bce5dfe645334f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708547"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="f6030-103">IHostIoCompletionManager::GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f6030-103">IHostIoCompletionManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="f6030-104">현재 요청을 처리 하 고 있지 않은 호스트에서 관리 하는 총 스레드 수에 대 한 i/o 완료 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-104">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6030-105">구문</span><span class="sxs-lookup"><span data-stu-id="f6030-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6030-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6030-106">Parameters</span></span>  

 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="f6030-107">제한이 현재 서비스 요청에 사용할 수 있는 호스트에서 관리 하는 i/o 완료 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-107">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6030-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="f6030-108">Return Value</span></span>  
  
|<span data-ttu-id="f6030-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6030-109">HRESULT</span></span>|<span data-ttu-id="f6030-110">설명</span><span class="sxs-lookup"><span data-stu-id="f6030-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6030-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6030-111">S_OK</span></span>|<span data-ttu-id="f6030-112">`GetAvailableThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-112">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f6030-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6030-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6030-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6030-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6030-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6030-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-116">The call timed out.</span></span>|  
|<span data-ttu-id="f6030-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6030-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6030-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6030-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6030-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6030-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6030-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6030-121">E_FAIL</span></span>|<span data-ttu-id="f6030-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6030-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6030-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6030-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f6030-125">E_NOTIMPL</span></span>|<span data-ttu-id="f6030-126">호스트는의 구현을 제공 하지 않습니다 `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="f6030-126">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6030-127">설명</span><span class="sxs-lookup"><span data-stu-id="f6030-127">Remarks</span></span>  

 <span data-ttu-id="f6030-128">호스트는 구현, 성능 또는 확장성과 같은 이유로 i/o 완료 스레드 풀의 크기에 대 한 배타적 제어를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-128">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="f6030-129">따라서 호스트는를 구현할 필요가 없습니다 `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="f6030-129">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="f6030-130">이 경우 호스트는이 메서드에서 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6030-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6030-131">Requirements</span></span>  

 <span data-ttu-id="f6030-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6030-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6030-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f6030-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6030-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6030-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6030-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6030-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6030-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6030-136">See also</span></span>

- [<span data-ttu-id="f6030-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6030-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="f6030-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6030-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
