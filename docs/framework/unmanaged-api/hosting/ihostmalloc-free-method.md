---
description: '자세히 알아보기: IHostMAlloc:: Free 메서드'
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
ms.openlocfilehash: 097e2e95b6dfb9d6a1bae68f9e0455a96383159e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708205"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="50f17-103">IHostMAlloc::Free 메서드</span><span class="sxs-lookup"><span data-stu-id="50f17-103">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="50f17-104">[Alloc](ihostmalloc-alloc-method.md) 함수를 사용 하 여 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-104">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f17-105">구문</span><span class="sxs-lookup"><span data-stu-id="50f17-105">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50f17-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50f17-106">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="50f17-107">진행 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-107">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50f17-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="50f17-108">Return Value</span></span>  
  
|<span data-ttu-id="50f17-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50f17-109">HRESULT</span></span>|<span data-ttu-id="50f17-110">설명</span><span class="sxs-lookup"><span data-stu-id="50f17-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50f17-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="50f17-111">S_OK</span></span>|<span data-ttu-id="50f17-112">`Free` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-112">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="50f17-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50f17-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50f17-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50f17-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50f17-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50f17-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-116">The call timed out.</span></span>|  
|<span data-ttu-id="50f17-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50f17-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50f17-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50f17-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50f17-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50f17-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50f17-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50f17-121">E_FAIL</span></span>|<span data-ttu-id="50f17-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50f17-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50f17-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50f17-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="50f17-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="50f17-126">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-126">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50f17-127">설명</span><span class="sxs-lookup"><span data-stu-id="50f17-127">Remarks</span></span>  

 <span data-ttu-id="50f17-128">`pMem`매개 변수가에 대 한 호출을 사용 하 여 할당 되지 않은 메모리 영역을 참조 하는 경우 `Alloc` 호스트는 HOST_E_INVALIDOPERATION을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-128">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f17-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50f17-129">Requirements</span></span>  

 <span data-ttu-id="50f17-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50f17-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f17-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="50f17-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50f17-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50f17-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50f17-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f17-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f17-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50f17-134">See also</span></span>

- [<span data-ttu-id="50f17-135">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50f17-135">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="50f17-136">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50f17-136">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
