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
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841934"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="39c55-102">IHostThreadPoolManager::GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="39c55-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="39c55-103">호스트에서 요청을 예측 하 여 스레드 풀에 유지 관리 하는 최소 유휴 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c55-104">구문</span><span class="sxs-lookup"><span data-stu-id="39c55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39c55-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39c55-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="39c55-106">제한이 호스트가 현재 유지 관리 하는 최소 유휴 작업자 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39c55-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="39c55-107">Return Value</span></span>  
  
|<span data-ttu-id="39c55-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39c55-108">HRESULT</span></span>|<span data-ttu-id="39c55-109">Description</span><span class="sxs-lookup"><span data-stu-id="39c55-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39c55-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="39c55-110">S_OK</span></span>|<span data-ttu-id="39c55-111">`GetMinThreads`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="39c55-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39c55-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39c55-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39c55-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39c55-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39c55-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-115">The call timed out.</span></span>|  
|<span data-ttu-id="39c55-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39c55-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39c55-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39c55-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39c55-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39c55-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39c55-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39c55-120">E_FAIL</span></span>|<span data-ttu-id="39c55-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39c55-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39c55-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="39c55-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="39c55-124">E_NOTIMPL</span></span>|<span data-ttu-id="39c55-125">호스트는의 구현을 제공 하지 않습니다 `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="39c55-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c55-126">설명</span><span class="sxs-lookup"><span data-stu-id="39c55-126">Remarks</span></span>  
 <span data-ttu-id="39c55-127">호스트는의 구현을 제공 하는 데 필요 하지 않습니다 `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="39c55-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="39c55-128">이 경우 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c55-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39c55-129">Requirements</span></span>  
 <span data-ttu-id="39c55-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39c55-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c55-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39c55-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39c55-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c55-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39c55-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c55-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c55-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39c55-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="39c55-135">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="39c55-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="39c55-136">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="39c55-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="39c55-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39c55-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
