---
title: IHostMemoryManager::VirtualFree 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: 4d37b7d803509ebfa861b7502d419f868bd12e11
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804382"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="c53d1-102">IHostMemoryManager::VirtualFree 메서드</span><span class="sxs-lookup"><span data-stu-id="c53d1-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="c53d1-103">해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="c53d1-104">의 Win32 구현은 호출 하는 `VirtualFree` 프로세스의 가상 주소 공간 내에서 페이지 영역을 해제, 커밋 취소 또는 해제 하 고 커밋을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="c53d1-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c53d1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c53d1-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="c53d1-107">진행 해제할 가상 메모리 페이지의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="c53d1-108">진행 해제할 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="c53d1-109">진행 해제 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c53d1-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c53d1-110">Return Value</span></span>  
  
|<span data-ttu-id="c53d1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c53d1-111">HRESULT</span></span>|<span data-ttu-id="c53d1-112">Description</span><span class="sxs-lookup"><span data-stu-id="c53d1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c53d1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c53d1-113">S_OK</span></span>|<span data-ttu-id="c53d1-114">`VirtualFree`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="c53d1-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c53d1-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c53d1-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c53d1-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c53d1-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c53d1-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-118">The call timed out.</span></span>|  
|<span data-ttu-id="c53d1-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c53d1-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c53d1-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c53d1-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c53d1-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c53d1-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c53d1-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c53d1-123">E_FAIL</span></span>|<span data-ttu-id="c53d1-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c53d1-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c53d1-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c53d1-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="c53d1-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="c53d1-128">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c53d1-129">설명</span><span class="sxs-lookup"><span data-stu-id="c53d1-129">Remarks</span></span>  
 <span data-ttu-id="c53d1-130">`VirtualFree``lpAddress` [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) 함수에 대 한 이전 호출을 통해 매개 변수와 연결 된 가상 메모리 페이지를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="c53d1-131">호스트를 통해 할당 되지 않은 메모리를 해제 하려는 시도는 HOST_E_INVALIDOPERATION을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="c53d1-132">의미 체계는의 Win32 구현에 대 한 의미 체계와 동일 합니다 `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="c53d1-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="c53d1-133">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c53d1-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53d1-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c53d1-134">Requirements</span></span>  
 <span data-ttu-id="c53d1-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c53d1-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c53d1-136">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c53d1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c53d1-137">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c53d1-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c53d1-138">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c53d1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53d1-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c53d1-139">See also</span></span>

- [<span data-ttu-id="c53d1-140">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c53d1-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="c53d1-141">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c53d1-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
