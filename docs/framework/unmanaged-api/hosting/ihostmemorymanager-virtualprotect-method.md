---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62aa6b1d9be86a9b60abf894d67555f706e6a8ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760169"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="655e9-102">IHostMemoryManager::VirtualProtect 메서드</span><span class="sxs-lookup"><span data-stu-id="655e9-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="655e9-103">역할을 해당 하는 Win32 함수에 대 한 논리적 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="655e9-104">Win32 구현의 `VirtualProtect` 호출 프로세스의 가상 주소 공간에서 커밋된 페이지의 지역에 대 한 보호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655e9-105">구문</span><span class="sxs-lookup"><span data-stu-id="655e9-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="655e9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="655e9-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="655e9-107">[in] 변경 된 보호 특성을 가진 가상 메모리의 기본 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="655e9-108">[in] (바이트)를 변경할지 메모리 페이지의 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="655e9-109">[in] 적용할 메모리 보호의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="655e9-110">[out] 이전 메모리 보호 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="655e9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="655e9-111">Return Value</span></span>  
  
|<span data-ttu-id="655e9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="655e9-112">HRESULT</span></span>|<span data-ttu-id="655e9-113">설명</span><span class="sxs-lookup"><span data-stu-id="655e9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="655e9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="655e9-114">S_OK</span></span>|<span data-ttu-id="655e9-115">`VirtualProtect` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="655e9-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="655e9-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="655e9-117">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="655e9-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="655e9-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="655e9-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-119">The call timed out.</span></span>|  
|<span data-ttu-id="655e9-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="655e9-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="655e9-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="655e9-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="655e9-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="655e9-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="655e9-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="655e9-124">E_FAIL</span></span>|<span data-ttu-id="655e9-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="655e9-126">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="655e9-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="655e9-128">설명</span><span class="sxs-lookup"><span data-stu-id="655e9-128">Remarks</span></span>  
 <span data-ttu-id="655e9-129">이 구현의 `VirtualProtect` Win32 구현은 성공을 나타내기 위해 0이 아닌 값을 반환 하는 동안에 HRESULT 값 및 0 개 실패를 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="655e9-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="655e9-130">자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="655e9-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655e9-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="655e9-131">Requirements</span></span>  
 <span data-ttu-id="655e9-132">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="655e9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655e9-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="655e9-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="655e9-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="655e9-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="655e9-135">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="655e9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655e9-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="655e9-136">See also</span></span>

- [<span data-ttu-id="655e9-137">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="655e9-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
