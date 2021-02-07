---
description: '자세히 알아보기: IHostMemoryManager:: VirtualProtect 메서드'
title: IHostMemoryManager::VirtualProtect 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
ms.openlocfilehash: 66e1fb5afdc3aa5c400ed0ffa9cea569d300e6a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707442"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="bcfd6-103">IHostMemoryManager::VirtualProtect 메서드</span><span class="sxs-lookup"><span data-stu-id="bcfd6-103">IHostMemoryManager::VirtualProtect Method</span></span>

<span data-ttu-id="bcfd6-104">해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="bcfd6-105">의 Win32 구현은 `VirtualProtect` 호출 프로세스의 가상 주소 공간에서 커밋된 페이지 영역에 대 한 보호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-105">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfd6-106">구문</span><span class="sxs-lookup"><span data-stu-id="bcfd6-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcfd6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bcfd6-107">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="bcfd6-108">진행 보호 특성을 변경할 가상 메모리의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-108">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="bcfd6-109">진행 변경할 메모리 페이지 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-109">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="bcfd6-110">진행 적용할 메모리 보호의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-110">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="bcfd6-111">제한이 이전 메모리 보호 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-111">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcfd6-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="bcfd6-112">Return Value</span></span>  
  
|<span data-ttu-id="bcfd6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bcfd6-113">HRESULT</span></span>|<span data-ttu-id="bcfd6-114">설명</span><span class="sxs-lookup"><span data-stu-id="bcfd6-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bcfd6-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcfd6-115">S_OK</span></span>|<span data-ttu-id="bcfd6-116">`VirtualProtect` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-116">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="bcfd6-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bcfd6-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bcfd6-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bcfd6-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bcfd6-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bcfd6-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-120">The call timed out.</span></span>|  
|<span data-ttu-id="bcfd6-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bcfd6-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bcfd6-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bcfd6-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bcfd6-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bcfd6-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bcfd6-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bcfd6-125">E_FAIL</span></span>|<span data-ttu-id="bcfd6-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bcfd6-127">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bcfd6-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcfd6-129">설명</span><span class="sxs-lookup"><span data-stu-id="bcfd6-129">Remarks</span></span>  

 <span data-ttu-id="bcfd6-130">이 구현 `VirtualProtect` 에서는 HRESULT 값을 반환 하는 반면, Win32 구현은 성공 여부를 나타내는 0이 아닌 값을 반환 하 고 실패를 나타내는 0 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-130">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="bcfd6-131">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-131">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcfd6-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bcfd6-132">Requirements</span></span>  

 <span data-ttu-id="bcfd6-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfd6-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bcfd6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcfd6-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcfd6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcfd6-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfd6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfd6-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfd6-137">See also</span></span>

- [<span data-ttu-id="bcfd6-138">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bcfd6-138">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
