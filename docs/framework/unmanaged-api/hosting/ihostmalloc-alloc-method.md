---
title: IHostMAlloc::Alloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e38d1f3cfe78b7f47a37c12c84282196f4385fbb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780742"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="3eda4-102">IHostMAlloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="3eda4-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="3eda4-103">호스트 힙에서 지정된 된 양의 메모리를 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eda4-104">구문</span><span class="sxs-lookup"><span data-stu-id="3eda4-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eda4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3eda4-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="3eda4-106">[in] 현재 메모리 할당 요청 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="3eda4-107">[in] 중 하나는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 할당 오류가의 영향을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="3eda4-108">[out] 할당 된 메모리 또는 요청을 완료할 수 없습니다 경우에 null 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eda4-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="3eda4-109">Return Value</span></span>  
  
|<span data-ttu-id="3eda4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eda4-110">HRESULT</span></span>|<span data-ttu-id="3eda4-111">설명</span><span class="sxs-lookup"><span data-stu-id="3eda4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eda4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eda4-112">S_OK</span></span>|<span data-ttu-id="3eda4-113">`Alloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="3eda4-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3eda4-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3eda4-115">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3eda4-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3eda4-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3eda4-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-117">The call timed out.</span></span>|  
|<span data-ttu-id="3eda4-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3eda4-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3eda4-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3eda4-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3eda4-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3eda4-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3eda4-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3eda4-122">E_FAIL</span></span>|<span data-ttu-id="3eda4-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3eda4-124">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3eda4-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3eda4-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3eda4-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3eda4-127">할당 요청을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eda4-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eda4-128">설명</span><span class="sxs-lookup"><span data-stu-id="3eda4-128">Remarks</span></span>  
 <span data-ttu-id="3eda4-129">CLR에 대 한 인터페이스 포인터를 가져옵니다는 `IHostMalloc` 를 호출 하 여 인스턴스를 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3eda4-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eda4-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3eda4-130">Requirements</span></span>  
 <span data-ttu-id="3eda4-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3eda4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eda4-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3eda4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3eda4-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3eda4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eda4-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eda4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eda4-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="3eda4-135">See also</span></span>

- [<span data-ttu-id="3eda4-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eda4-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="3eda4-137">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eda4-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
