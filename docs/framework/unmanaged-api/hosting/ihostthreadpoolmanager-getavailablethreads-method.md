---
title: IHostThreadPoolManager::GetAvailableThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 64d5ba9ad5557f99b175c277d48003529d77861c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730801"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="f66df-102">IHostThreadPoolManager::GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="f66df-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="f66df-103">현재 작업 항목을 처리 하 고 있지 않은 스레드 풀의 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f66df-104">구문</span><span class="sxs-lookup"><span data-stu-id="f66df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f66df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f66df-105">Parameters</span></span>  

 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="f66df-106">제한이 현재 작업 항목을 처리 하 고 있지 않은 스레드 풀의 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f66df-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f66df-107">Return Value</span></span>  
  
|<span data-ttu-id="f66df-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f66df-108">HRESULT</span></span>|<span data-ttu-id="f66df-109">설명</span><span class="sxs-lookup"><span data-stu-id="f66df-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f66df-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f66df-110">S_OK</span></span>|<span data-ttu-id="f66df-111">`GetAvailableThreads` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f66df-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f66df-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f66df-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f66df-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f66df-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f66df-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-115">The call timed out.</span></span>|  
|<span data-ttu-id="f66df-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f66df-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f66df-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f66df-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f66df-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f66df-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f66df-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f66df-120">E_FAIL</span></span>|<span data-ttu-id="f66df-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f66df-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f66df-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f66df-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f66df-124">E_NOTIMPL</span></span>|<span data-ttu-id="f66df-125">호스트는의 구현을 제공 하지 않습니다 `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="f66df-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f66df-126">설명</span><span class="sxs-lookup"><span data-stu-id="f66df-126">Remarks</span></span>  

 <span data-ttu-id="f66df-127">호스트에서의 구현을 제공 하지 않는 경우 `GetAvailableThreads` E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f66df-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f66df-128">Requirements</span></span>  

 <span data-ttu-id="f66df-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f66df-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f66df-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f66df-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f66df-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f66df-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f66df-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f66df-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66df-133">참조</span><span class="sxs-lookup"><span data-stu-id="f66df-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="f66df-134">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f66df-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
