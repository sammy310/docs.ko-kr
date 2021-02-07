---
description: '자세히 알아보기: IHostMemoryManager:: VirtualAlloc 메서드'
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
ms.openlocfilehash: 28682aea5e6e7951b3b8f0a9af946a3f3828601b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707854"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="1cec2-103">IHostMemoryManager::VirtualAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="1cec2-103">IHostMemoryManager::VirtualAlloc Method</span></span>

<span data-ttu-id="1cec2-104">해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="1cec2-105">의 Win32 구현은 `VirtualAlloc` 호출 프로세스의 가상 주소 공간에서 페이지 영역을 예약 하거나 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-105">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cec2-106">구문</span><span class="sxs-lookup"><span data-stu-id="1cec2-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cec2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1cec2-107">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="1cec2-108">진행 할당할 영역의 시작 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-108">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="1cec2-109">진행 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-109">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="1cec2-110">진행 메모리 할당의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-110">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="1cec2-111">진행 할당할 페이지 영역에 대 한 메모리 보호입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-111">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="1cec2-112">진행 할당 오류의 영향을 나타내는 [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-112">[in] An [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="1cec2-113">제한이 할당 된 메모리의 시작 주소에 대 한 포인터 이거나, 요청을 충족 하지 못할 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-113">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cec2-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="1cec2-114">Return Value</span></span>  
  
|<span data-ttu-id="1cec2-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cec2-115">HRESULT</span></span>|<span data-ttu-id="1cec2-116">설명</span><span class="sxs-lookup"><span data-stu-id="1cec2-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cec2-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cec2-117">S_OK</span></span>|<span data-ttu-id="1cec2-118">`VirtualAlloc` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-118">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="1cec2-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cec2-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cec2-120">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cec2-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cec2-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cec2-122">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-122">The call timed out.</span></span>|  
|<span data-ttu-id="1cec2-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cec2-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cec2-124">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cec2-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cec2-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cec2-126">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cec2-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cec2-127">E_FAIL</span></span>|<span data-ttu-id="1cec2-128">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cec2-129">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cec2-130">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1cec2-131">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1cec2-131">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1cec2-132">할당 요청을 완료 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-132">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cec2-133">설명</span><span class="sxs-lookup"><span data-stu-id="1cec2-133">Remarks</span></span>  

 <span data-ttu-id="1cec2-134">를 호출 하 여 프로세스의 주소 공간에서 영역을 예약 `VirtualAlloc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-134">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="1cec2-135">`pAddress`매개 변수에는 원하는 메모리 블록의 시작 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-135">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="1cec2-136">이 매개 변수는 일반적으로 null로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-136">This parameter is typically set to null.</span></span> <span data-ttu-id="1cec2-137">운영 체제는 프로세스에 사용할 수 있는 무료 주소 범위에 대 한 레코드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-137">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="1cec2-138">`pAddress`Null 값은 시스템이 적합 한 위치에 있는 영역을 예약 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-138">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="1cec2-139">또는 메모리 블록에 대 한 특정 시작 주소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-139">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="1cec2-140">두 경우 모두 출력 매개 변수는 `ppMem` 할당 된 메모리에 대 한 포인터로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-140">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="1cec2-141">함수 자체는 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-141">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="1cec2-142">Win32 함수에는 `VirtualAlloc` `ppMem` 매개 변수가 없으며 대신 할당 된 메모리에 대 한 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-142">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="1cec2-143">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cec2-143">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cec2-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1cec2-144">Requirements</span></span>  

 <span data-ttu-id="1cec2-145">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cec2-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cec2-146">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1cec2-146">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cec2-147">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cec2-147">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cec2-148">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cec2-148">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cec2-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cec2-149">See also</span></span>

- [<span data-ttu-id="1cec2-150">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1cec2-150">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
