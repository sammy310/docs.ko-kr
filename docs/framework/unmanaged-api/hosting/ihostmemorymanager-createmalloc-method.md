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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194e9b73610ccb7282babf266eea2968a4f035ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179129"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="19286-102">IHostMemoryManager::CreateMAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="19286-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="19286-103">한 인터페이스 포인터를 가져옵니다는 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 호스트에서 만든 힙에서 할당을 요청 하는 데 사용 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="19286-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19286-104">구문</span><span class="sxs-lookup"><span data-stu-id="19286-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19286-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19286-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="19286-106">[in] 조합을 [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) 할당 되는 메모리의 특성을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="19286-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="19286-107">[out] 주소에 대 한 포인터는 `IHostMAlloc` 인스턴스가 호스트에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19286-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19286-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="19286-108">Return Value</span></span>  
  
|<span data-ttu-id="19286-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19286-109">HRESULT</span></span>|<span data-ttu-id="19286-110">설명</span><span class="sxs-lookup"><span data-stu-id="19286-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19286-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="19286-111">S_OK</span></span>|<span data-ttu-id="19286-112">`CreateMAlloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="19286-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="19286-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19286-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19286-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19286-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19286-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19286-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-116">The call timed out.</span></span>|  
|<span data-ttu-id="19286-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19286-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19286-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19286-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19286-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19286-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19286-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19286-121">E_FAIL</span></span>|<span data-ttu-id="19286-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19286-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19286-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19286-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="19286-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="19286-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="19286-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="19286-126">할당 요청을 완료할 수 물리적 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="19286-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19286-127">설명</span><span class="sxs-lookup"><span data-stu-id="19286-127">Remarks</span></span>  
 <span data-ttu-id="19286-128">`CreateMAlloc` CLR 표준 Win32 함수를 사용 하는 대신 호스트를 통해 할당 요청을 허용 하는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="19286-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19286-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19286-129">Requirements</span></span>  
 <span data-ttu-id="19286-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="19286-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19286-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19286-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19286-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="19286-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19286-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19286-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19286-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="19286-134">See also</span></span>

- [<span data-ttu-id="19286-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19286-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="19286-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19286-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
