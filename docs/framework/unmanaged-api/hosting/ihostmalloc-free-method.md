---
title: IHostMAlloc::Free 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: d4c9048c89d55ed048a55a771572823905a056df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687140"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="de61b-102">IHostMAlloc::Free 메서드</span><span class="sxs-lookup"><span data-stu-id="de61b-102">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="de61b-103">[Alloc](ihostmalloc-alloc-method.md) 함수를 사용 하 여 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de61b-104">구문</span><span class="sxs-lookup"><span data-stu-id="de61b-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de61b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de61b-105">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="de61b-106">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de61b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="de61b-107">Return Value</span></span>  
  
|<span data-ttu-id="de61b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de61b-108">HRESULT</span></span>|<span data-ttu-id="de61b-109">설명</span><span class="sxs-lookup"><span data-stu-id="de61b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de61b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="de61b-110">S_OK</span></span>|<span data-ttu-id="de61b-111">`Free` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="de61b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="de61b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="de61b-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="de61b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="de61b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="de61b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-115">The call timed out.</span></span>|  
|<span data-ttu-id="de61b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="de61b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="de61b-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="de61b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="de61b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="de61b-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="de61b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="de61b-120">E_FAIL</span></span>|<span data-ttu-id="de61b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="de61b-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="de61b-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="de61b-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="de61b-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="de61b-125">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de61b-126">설명</span><span class="sxs-lookup"><span data-stu-id="de61b-126">Remarks</span></span>  

 <span data-ttu-id="de61b-127">`pMem`매개 변수가에 대 한 호출을 사용 하 여 할당 되지 않은 메모리 영역을 참조 하는 경우 `Alloc` 호스트는 HOST_E_INVALIDOPERATION을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de61b-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de61b-128">Requirements</span></span>  

 <span data-ttu-id="de61b-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de61b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de61b-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="de61b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de61b-131">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de61b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de61b-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de61b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de61b-133">참조</span><span class="sxs-lookup"><span data-stu-id="de61b-133">See also</span></span>

- [<span data-ttu-id="de61b-134">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de61b-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="de61b-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de61b-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
