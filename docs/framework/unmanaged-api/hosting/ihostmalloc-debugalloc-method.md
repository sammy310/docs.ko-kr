---
title: IHostMAlloc::DebugAlloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178032"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="99f06-102">IHostMAlloc::DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="99f06-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="99f06-103">호스트가 힙에서 지정된 양의 메모리를 할당하고 메모리가 할당된 위치를 추가로 추적할 것을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f06-104">구문</span><span class="sxs-lookup"><span data-stu-id="99f06-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f06-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99f06-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="99f06-106">【인】 현재 메모리 할당 요청의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="99f06-107">【인】 할당 실패의 영향을 나타내는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="99f06-108">【인】 디버깅 중인 실행 파일의 코드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="99f06-109">【인】 할당이 `pszFileName` 요청된 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="99f06-110">【아웃】 할당된 메모리에 대한 포인터 또는 요청을 완료할 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99f06-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="99f06-111">Return Value</span></span>  
  
|<span data-ttu-id="99f06-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99f06-112">HRESULT</span></span>|<span data-ttu-id="99f06-113">Description</span><span class="sxs-lookup"><span data-stu-id="99f06-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99f06-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="99f06-114">S_OK</span></span>|<span data-ttu-id="99f06-115">`DebugAlloc`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="99f06-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99f06-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99f06-117">CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99f06-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99f06-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99f06-119">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-119">The call timed out.</span></span>|  
|<span data-ttu-id="99f06-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99f06-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99f06-121">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99f06-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99f06-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99f06-123">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99f06-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99f06-124">E_FAIL</span></span>|<span data-ttu-id="99f06-125">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99f06-126">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99f06-127">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="99f06-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="99f06-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="99f06-129">할당 요청을 완료하는 데 사용할 수 있는 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99f06-130">설명</span><span class="sxs-lookup"><span data-stu-id="99f06-130">Remarks</span></span>  
 <span data-ttu-id="99f06-131">CLR은 [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드를 호출하여 [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인스턴스에 대한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="99f06-132">`DebugAlloc`런타임에서 디버깅 중에 사용할 코드 파일 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f06-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f06-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99f06-133">Requirements</span></span>  
 <span data-ttu-id="99f06-134">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99f06-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f06-135">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="99f06-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99f06-136">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99f06-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99f06-137">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f06-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f06-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99f06-138">See also</span></span>

- [<span data-ttu-id="99f06-139">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f06-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="99f06-140">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f06-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
