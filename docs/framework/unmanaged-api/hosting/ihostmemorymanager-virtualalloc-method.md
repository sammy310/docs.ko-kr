---
title: IHostMemoryManager::VirtualAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e5ce46e1cf034e6b86d738d8ec69332df1ff9fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486262"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="a064d-102">IHostMemoryManager::VirtualAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="a064d-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="a064d-103">역할을 해당 하는 Win32 함수에 대 한 논리적 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="a064d-104">Win32 구현의 `VirtualAlloc` 예약 하거나 호출 프로세스의 가상 주소 공간에서 페이지의 영역을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a064d-105">구문</span><span class="sxs-lookup"><span data-stu-id="a064d-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a064d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a064d-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="a064d-107">[in] 할당할 영역의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="a064d-108">[in] 영역의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="a064d-109">[in] 메모리 할당의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="a064d-110">[in] 할당할 페이지 영역에 대 한 메모리 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="a064d-111">[in] [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 영향 할당 오류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="a064d-112">[out] 요청을 처리 하지 못한 경우 null을 할당 된 메모리의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a064d-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="a064d-113">Return Value</span></span>  
  
|<span data-ttu-id="a064d-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a064d-114">HRESULT</span></span>|<span data-ttu-id="a064d-115">설명</span><span class="sxs-lookup"><span data-stu-id="a064d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a064d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a064d-116">S_OK</span></span>|<span data-ttu-id="a064d-117">`VirtualAlloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a064d-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a064d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a064d-119">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a064d-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a064d-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a064d-121">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-121">The call timed out.</span></span>|  
|<span data-ttu-id="a064d-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a064d-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a064d-123">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a064d-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a064d-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a064d-125">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a064d-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a064d-126">E_FAIL</span></span>|<span data-ttu-id="a064d-127">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a064d-128">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a064d-129">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a064d-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a064d-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a064d-131">할당 요청을 완료 하려면 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a064d-132">설명</span><span class="sxs-lookup"><span data-stu-id="a064d-132">Remarks</span></span>  
 <span data-ttu-id="a064d-133">호출 하 여 프로세스의 주소 공간에서 영역을 예약 `VirtualAlloc`합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="a064d-134">`pAddress` 하려는 메모리 블록의 시작 주소를 포함 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="a064d-135">이 매개 변수는 일반적으로 설정 하는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-135">This parameter is typically set to null.</span></span> <span data-ttu-id="a064d-136">운영 체제는 프로세스에 사용할 수 있는 사용 가능한 주소 범위 레코드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="a064d-137">`pAddress` null 값에는 시스템에서 판단 되는 영역을 예약 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="a064d-138">또는 메모리 블록에 대 한 특정 시작 주소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="a064d-139">두 경우 모두 출력 매개 변수 `ppMem` 할당된 된 메모리에 대 한 포인터로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="a064d-140">함수 자체에 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="a064d-141">Win32 `VirtualAlloc` 함수에는 한 `ppMem` 매개 변수를 대신 할당된 된 메모리에 대 한 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a064d-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="a064d-142">자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a064d-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a064d-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a064d-143">Requirements</span></span>  
 <span data-ttu-id="a064d-144">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a064d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a064d-145">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a064d-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a064d-146">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a064d-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a064d-147">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a064d-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a064d-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="a064d-148">See also</span></span>
- [<span data-ttu-id="a064d-149">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a064d-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
