---
description: '자세히 알아보기: IHostMemoryManager:: VirtualQuery 메서드'
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
ms.openlocfilehash: 8518ef71ad7d493fa04d4e2321f1f90ef8ecd18d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707554"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="2f372-103">IHostMemoryManager::VirtualQuery 메서드</span><span class="sxs-lookup"><span data-stu-id="2f372-103">IHostMemoryManager::VirtualQuery Method</span></span>

<span data-ttu-id="2f372-104">해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="2f372-105">의 Win32 구현은 `VirtualQuery` 호출 프로세스의 가상 주소 공간에 있는 페이지 범위에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-105">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f372-106">구문</span><span class="sxs-lookup"><span data-stu-id="2f372-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f372-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f372-107">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="2f372-108">진행 쿼리할 가상 메모리의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-108">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="2f372-109">제한이 지정 된 메모리 영역에 대 한 정보를 포함 하는 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-109">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2f372-110">진행 가 가리키는 버퍼의 크기 (바이트)입니다 `lpBuffer` .</span><span class="sxs-lookup"><span data-stu-id="2f372-110">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="2f372-111">제한이 정보 버퍼에서 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-111">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f372-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="2f372-112">Return Value</span></span>  
  
|<span data-ttu-id="2f372-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f372-113">HRESULT</span></span>|<span data-ttu-id="2f372-114">설명</span><span class="sxs-lookup"><span data-stu-id="2f372-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f372-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f372-115">S_OK</span></span>|<span data-ttu-id="2f372-116">`VirtualQuery` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-116">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="2f372-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f372-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f372-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f372-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f372-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f372-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-120">The call timed out.</span></span>|  
|<span data-ttu-id="2f372-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f372-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f372-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f372-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f372-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f372-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f372-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f372-125">E_FAIL</span></span>|<span data-ttu-id="2f372-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f372-127">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f372-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f372-129">설명</span><span class="sxs-lookup"><span data-stu-id="2f372-129">Remarks</span></span>  

 <span data-ttu-id="2f372-130">`VirtualQuery` 호출 프로세스의 가상 주소 공간에 있는 페이지 범위에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-130">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="2f372-131">이 구현에서는 매개 변수의 값을 `pResult` 정보 버퍼에서 반환 된 바이트 수로 설정 하 고 HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-131">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="2f372-132">Win32 함수에서 `VirtualQuery` 반환 값은 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-132">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="2f372-133">자세한 내용은 Windows 플랫폼 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f372-133">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2f372-134">운영 체제의 구현에는 `VirtualQuery` 교착 상태가 발생 하지 않으며 사용자 코드에서 일시 중단 된 임의 스레드를 사용 하 여 완료 될 때까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-134">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="2f372-135">이 메서드의 호스팅된 버전을 구현 하는 경우 매우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-135">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f372-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f372-136">Requirements</span></span>  

 <span data-ttu-id="2f372-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f372-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f372-138">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2f372-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f372-139">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f372-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f372-140">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f372-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f372-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f372-141">See also</span></span>

- [<span data-ttu-id="2f372-142">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f372-142">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
