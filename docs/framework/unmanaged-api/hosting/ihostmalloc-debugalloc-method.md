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
ms.openlocfilehash: 49de0398dd32970bd8ceb0fd24178e75df5d14b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713497"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="cba5d-102">IHostMAlloc::DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="cba5d-102">IHostMAlloc::DebugAlloc Method</span></span>

<span data-ttu-id="cba5d-103">호스트가 힙에서 지정 된 양의 메모리를 할당 하도록 요청 하 고 추가적으로 메모리가 할당 된 위치를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cba5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="cba5d-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cba5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cba5d-105">Parameters</span></span>  

 `cbSize`  
 <span data-ttu-id="cba5d-106">진행 현재 메모리 할당 요청의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="cba5d-107">진행 할당 오류의 영향을 나타내는 [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="cba5d-108">진행 디버깅 되는 실행 파일의 코드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="cba5d-109">진행 할당이 요청 된의 줄 번호 `pszFileName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="cba5d-110">제한이 할당 된 메모리에 대 한 포인터 이거나, 요청을 완료할 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cba5d-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="cba5d-111">Return Value</span></span>  
  
|<span data-ttu-id="cba5d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cba5d-112">HRESULT</span></span>|<span data-ttu-id="cba5d-113">설명</span><span class="sxs-lookup"><span data-stu-id="cba5d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cba5d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="cba5d-114">S_OK</span></span>|<span data-ttu-id="cba5d-115">`DebugAlloc` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="cba5d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cba5d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cba5d-117">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cba5d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cba5d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cba5d-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-119">The call timed out.</span></span>|  
|<span data-ttu-id="cba5d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cba5d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cba5d-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cba5d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cba5d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cba5d-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cba5d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cba5d-124">E_FAIL</span></span>|<span data-ttu-id="cba5d-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cba5d-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cba5d-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cba5d-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cba5d-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="cba5d-129">할당 요청을 완료 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cba5d-130">설명</span><span class="sxs-lookup"><span data-stu-id="cba5d-130">Remarks</span></span>  

 <span data-ttu-id="cba5d-131">CLR은 [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 [IHostMalloc](ihostmalloc-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-131">The CLR gets an interface pointer to an [IHostMalloc](ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="cba5d-132">`DebugAlloc` 런타임에 디버깅 중에 사용할 코드 파일 정보를 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cba5d-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cba5d-133">Requirements</span></span>  

 <span data-ttu-id="cba5d-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cba5d-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cba5d-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cba5d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cba5d-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cba5d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cba5d-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cba5d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba5d-138">참조</span><span class="sxs-lookup"><span data-stu-id="cba5d-138">See also</span></span>

- [<span data-ttu-id="cba5d-139">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cba5d-139">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="cba5d-140">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cba5d-140">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
