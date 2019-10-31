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
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192074"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="3a3c3-102">IHostMAlloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="3a3c3-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="3a3c3-103">호스트가 힙에서 지정 된 양의 메모리를 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a3c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a3c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a3c3-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="3a3c3-106">진행 현재 메모리 할당 요청의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="3a3c3-107">진행 할당 오류의 영향을 나타내는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="3a3c3-108">제한이 할당 된 메모리에 대 한 포인터 이거나, 요청을 완료할 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a3c3-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="3a3c3-109">Return Value</span></span>  
  
|<span data-ttu-id="3a3c3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a3c3-110">HRESULT</span></span>|<span data-ttu-id="3a3c3-111">설명</span><span class="sxs-lookup"><span data-stu-id="3a3c3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a3c3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a3c3-112">S_OK</span></span>|<span data-ttu-id="3a3c3-113">`Alloc` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="3a3c3-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a3c3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a3c3-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a3c3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a3c3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a3c3-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-117">The call timed out.</span></span>|  
|<span data-ttu-id="3a3c3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a3c3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a3c3-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a3c3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a3c3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a3c3-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a3c3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a3c3-122">E_FAIL</span></span>|<span data-ttu-id="3a3c3-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a3c3-124">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a3c3-125">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3a3c3-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3a3c3-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3a3c3-127">할당 요청을 완료 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a3c3-128">주의</span><span class="sxs-lookup"><span data-stu-id="3a3c3-128">Remarks</span></span>  
 <span data-ttu-id="3a3c3-129">CLR은 [IHostMemoryManager:: CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 `IHostMalloc` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a3c3-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a3c3-130">Requirements</span></span>  
 <span data-ttu-id="3a3c3-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3c3-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3a3c3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a3c3-133">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a3c3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a3c3-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a3c3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3c3-135">참조</span><span class="sxs-lookup"><span data-stu-id="3a3c3-135">See also</span></span>

- [<span data-ttu-id="3a3c3-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a3c3-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="3a3c3-137">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a3c3-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
