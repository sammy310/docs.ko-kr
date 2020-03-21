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
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176307"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="7f1ef-102">IHostMAlloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="7f1ef-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="7f1ef-103">호스트가 힙에서 지정된 양의 메모리를 할당해 달라는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f1ef-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f1ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f1ef-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="7f1ef-106">【인】 현재 메모리 할당 요청의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="7f1ef-107">【인】 할당 실패의 영향을 나타내는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="7f1ef-108">【아웃】 할당된 메모리에 대한 포인터 또는 요청을 완료할 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f1ef-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="7f1ef-109">Return Value</span></span>  
  
|<span data-ttu-id="7f1ef-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f1ef-110">HRESULT</span></span>|<span data-ttu-id="7f1ef-111">Description</span><span class="sxs-lookup"><span data-stu-id="7f1ef-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f1ef-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f1ef-112">S_OK</span></span>|<span data-ttu-id="7f1ef-113">`Alloc`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="7f1ef-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f1ef-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f1ef-115">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f1ef-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f1ef-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f1ef-117">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-117">The call timed out.</span></span>|  
|<span data-ttu-id="7f1ef-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f1ef-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f1ef-119">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f1ef-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f1ef-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f1ef-121">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f1ef-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f1ef-122">E_FAIL</span></span>|<span data-ttu-id="7f1ef-123">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f1ef-124">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f1ef-125">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7f1ef-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7f1ef-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7f1ef-127">할당 요청을 완료하는 데 사용할 수 있는 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f1ef-128">설명</span><span class="sxs-lookup"><span data-stu-id="7f1ef-128">Remarks</span></span>  
 <span data-ttu-id="7f1ef-129">CLR은 `IHostMalloc` [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출하여 인스턴스에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f1ef-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f1ef-130">Requirements</span></span>  
 <span data-ttu-id="7f1ef-131">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f1ef-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f1ef-132">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="7f1ef-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f1ef-133">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7f1ef-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f1ef-134">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f1ef-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1ef-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f1ef-135">See also</span></span>

- [<span data-ttu-id="7f1ef-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f1ef-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="7f1ef-137">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f1ef-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
