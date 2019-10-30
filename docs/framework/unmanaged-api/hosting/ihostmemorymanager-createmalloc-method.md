---
title: IHostMemoryManager::CreateMAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 8bcb01f4a19e6043bd59fe6f1565cdf35ed1f77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136720"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="c6bd6-102">IHostMemoryManager::CreateMAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="c6bd6-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="c6bd6-103">호스트에서 만든 힙의 할당 요청을 수행 하는 데 사용 되는 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6bd6-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6bd6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6bd6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6bd6-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="c6bd6-106">진행 할당 되는 메모리의 특성을 지정 하는 [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="c6bd6-107">제한이 호스트에서 제공 하는 `IHostMAlloc` 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6bd6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6bd6-108">Return Value</span></span>  
  
|<span data-ttu-id="c6bd6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6bd6-109">HRESULT</span></span>|<span data-ttu-id="c6bd6-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6bd6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6bd6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6bd6-111">S_OK</span></span>|<span data-ttu-id="c6bd6-112">`CreateMAlloc` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="c6bd6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6bd6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6bd6-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6bd6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6bd6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6bd6-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-116">The call timed out.</span></span>|  
|<span data-ttu-id="c6bd6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6bd6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6bd6-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6bd6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6bd6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6bd6-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6bd6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6bd6-121">E_FAIL</span></span>|<span data-ttu-id="c6bd6-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6bd6-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6bd6-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6bd6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c6bd6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c6bd6-126">할당 요청을 완료 하는 데 사용할 수 있는 실제 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6bd6-127">주의</span><span class="sxs-lookup"><span data-stu-id="c6bd6-127">Remarks</span></span>  
 <span data-ttu-id="c6bd6-128">`CreateMAlloc`는 CLR이 표준 Win32 함수를 사용 하는 대신 호스트를 통해 할당 요청을 수행할 수 있도록 하는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6bd6-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6bd6-129">Requirements</span></span>  
 <span data-ttu-id="c6bd6-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6bd6-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6bd6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6bd6-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6bd6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6bd6-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6bd6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bd6-134">참조</span><span class="sxs-lookup"><span data-stu-id="c6bd6-134">See also</span></span>

- [<span data-ttu-id="c6bd6-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6bd6-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="c6bd6-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6bd6-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
