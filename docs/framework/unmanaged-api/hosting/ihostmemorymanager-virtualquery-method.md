---
title: IHostMemoryManager::VirtualQuery 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 684d5e41e1d7cee2775aa0988d33a974315eac4e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772743"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="96b4b-102">IHostMemoryManager::VirtualQuery 메서드</span><span class="sxs-lookup"><span data-stu-id="96b4b-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="96b4b-103">역할을 해당 하는 Win32 함수에 대 한 논리적 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="96b4b-104">Win32 구현의 `VirtualQuery` 호출 프로세스의 가상 주소 공간에서 페이지 범위에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b4b-105">구문</span><span class="sxs-lookup"><span data-stu-id="96b4b-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96b4b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96b4b-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="96b4b-107">[in] 쿼리할 수 있는 가상 메모리 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="96b4b-108">[out] 지정 된 메모리 영역에 대 한 정보를 포함 하는 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="96b4b-109">[in] 버퍼의 바이트 크기는 `lpBuffer` 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="96b4b-110">[out] 정보 버퍼에서 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96b4b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="96b4b-111">Return Value</span></span>  
  
|<span data-ttu-id="96b4b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96b4b-112">HRESULT</span></span>|<span data-ttu-id="96b4b-113">Description</span><span class="sxs-lookup"><span data-stu-id="96b4b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96b4b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="96b4b-114">S_OK</span></span>|<span data-ttu-id="96b4b-115">`VirtualQuery` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="96b4b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96b4b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96b4b-117">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96b4b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96b4b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96b4b-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-119">The call timed out.</span></span>|  
|<span data-ttu-id="96b4b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96b4b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96b4b-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96b4b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96b4b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96b4b-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96b4b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96b4b-124">E_FAIL</span></span>|<span data-ttu-id="96b4b-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96b4b-126">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96b4b-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96b4b-128">설명</span><span class="sxs-lookup"><span data-stu-id="96b4b-128">Remarks</span></span>  
 <span data-ttu-id="96b4b-129">`VirtualQuery` 호출 프로세스의 가상 주소 공간에서 페이지 범위에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="96b4b-130">값을 설정 하는이 구현 된 `pResult` 바이트 수에 대 한 매개 변수 정보 버퍼에 반환 하 고 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="96b4b-131">Win32에서 `VirtualQuery` 함수 반환 값은 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="96b4b-132">자세한 내용은 Windows 플랫폼 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96b4b-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96b4b-133">운영 체제의 구현의 `VirtualQuery` 교착 상태가 발생 하지 않습니다 및 사용자 코드에서 일시 중단 하는 임의 스레드를 사용 하 여 실행을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="96b4b-134">이 메서드의 호스팅되는 버전을 구현 하는 경우에 주의 기울여야를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96b4b-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96b4b-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96b4b-135">Requirements</span></span>  
 <span data-ttu-id="96b4b-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="96b4b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96b4b-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96b4b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96b4b-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="96b4b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96b4b-139">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b4b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b4b-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="96b4b-140">See also</span></span>

- [<span data-ttu-id="96b4b-141">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="96b4b-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
