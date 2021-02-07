---
description: '자세히 알아보기: IHostMemoryManager:: VirtualFree 메서드'
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
ms.openlocfilehash: 987661ce1b7bfd08f757f53082313b8eb60ff282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707540"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="ca54a-103">IHostMemoryManager::VirtualFree 메서드</span><span class="sxs-lookup"><span data-stu-id="ca54a-103">IHostMemoryManager::VirtualFree Method</span></span>

<span data-ttu-id="ca54a-104">해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="ca54a-105">의 Win32 구현은 호출 하는 `VirtualFree` 프로세스의 가상 주소 공간 내에서 페이지 영역을 해제, 커밋 취소 또는 해제 하 고 커밋을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-105">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca54a-106">구문</span><span class="sxs-lookup"><span data-stu-id="ca54a-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca54a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca54a-107">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="ca54a-108">진행 해제할 가상 메모리 페이지의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-108">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="ca54a-109">진행 해제할 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-109">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="ca54a-110">진행 해제 작업의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-110">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca54a-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="ca54a-111">Return Value</span></span>  
  
|<span data-ttu-id="ca54a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca54a-112">HRESULT</span></span>|<span data-ttu-id="ca54a-113">설명</span><span class="sxs-lookup"><span data-stu-id="ca54a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca54a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca54a-114">S_OK</span></span>|<span data-ttu-id="ca54a-115">`VirtualFree` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-115">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="ca54a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ca54a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ca54a-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ca54a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ca54a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ca54a-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-119">The call timed out.</span></span>|  
|<span data-ttu-id="ca54a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca54a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ca54a-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ca54a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ca54a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ca54a-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ca54a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ca54a-124">E_FAIL</span></span>|<span data-ttu-id="ca54a-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ca54a-126">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ca54a-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ca54a-128">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ca54a-128">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ca54a-129">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-129">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca54a-130">설명</span><span class="sxs-lookup"><span data-stu-id="ca54a-130">Remarks</span></span>  

 <span data-ttu-id="ca54a-131">`VirtualFree``lpAddress` [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) 함수에 대 한 이전 호출을 통해 매개 변수와 연결 된 가상 메모리 페이지를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-131">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="ca54a-132">호스트를 통해 할당 되지 않은 메모리를 해제 하려는 시도는 HOST_E_INVALIDOPERATION을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-132">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="ca54a-133">의미 체계는의 Win32 구현에 대 한 의미 체계와 동일 합니다 `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="ca54a-133">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="ca54a-134">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca54a-134">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca54a-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca54a-135">Requirements</span></span>  

 <span data-ttu-id="ca54a-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca54a-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca54a-137">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ca54a-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca54a-138">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca54a-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca54a-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca54a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca54a-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca54a-140">See also</span></span>

- [<span data-ttu-id="ca54a-141">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca54a-141">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="ca54a-142">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca54a-142">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
