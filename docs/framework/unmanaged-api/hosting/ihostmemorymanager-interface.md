---
title: IHostMemoryManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760183"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="692b8-102">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="692b8-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="692b8-103">표준 Win32 가상 메모리 함수를 사용 하는 대신는 CLR (공용 언어 런타임) 호스트를 통해 가상 메모리 요청을 허용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="692b8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-104">Methods</span></span>  
  
|<span data-ttu-id="692b8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-105">Method</span></span>|<span data-ttu-id="692b8-106">설명</span><span class="sxs-lookup"><span data-stu-id="692b8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="692b8-107">AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="692b8-108">CLR (공용 언어 런타임) 운영 체제에서 지정된 된 메모리를 획득에 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="692b8-109">CreateMAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="692b8-110">한 인터페이스 포인터를 가져옵니다는 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 호스트에서 만든 힙에서 메모리 할당을 요청 하는 데 사용 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="692b8-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="692b8-111">GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="692b8-112">호스트에서 보고 있는 현재 사용 중인 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="692b8-113">NeedsVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="692b8-114">CLR이 지정 된 메모리 사용을 시도 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="692b8-115">RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="692b8-116">호스트 컴퓨터의 현재 메모리 로드 CLR에 알리기 위해 호출 되는 콜백 함수에 대 한 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="692b8-117">ReleasedVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="692b8-118">지정된 된 메모리를 사용 하 여 CLR가 완료 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="692b8-119">VirtualAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="692b8-120">예약 또는 호출 프로세스의 가상 주소 공간에서 페이지의 영역을 커밋에 해당 Win32 함수에 대 한 논리적 래퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="692b8-121">VirtualFree 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="692b8-122">릴리스, 커밋 또는 해제 하 고 호출 하는 프로세스의 가상 주소 공간 내의 페이지 영역을 커밋 해제 하는 해당 Win32 함수에 대 한 논리적 래퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="692b8-123">VirtualProtect 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="692b8-124">호출 프로세스의 가상 주소 공간에서 커밋된 페이지의 지역에 대 한 보호를 변경 하는 해당 Win32 함수에 대 한 논리적 래퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="692b8-125">VirtualQuery 메서드</span><span class="sxs-lookup"><span data-stu-id="692b8-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="692b8-126">호출 프로세스의 가상 주소 공간에서 페이지 범위에 대 한 정보를 검색 하는 해당 Win32 함수에 대 한 논리적 래퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="692b8-127">설명</span><span class="sxs-lookup"><span data-stu-id="692b8-127">Remarks</span></span>  
 <span data-ttu-id="692b8-128">`IHostMemoryManager` 또한 호스트에 의해 보고 되는 힙의 메모리 요청을 확인 하 고 프로세스의 메모리 압력 수준에 대 한 포인터를 가져오려면 CLR에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="692b8-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692b8-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="692b8-129">Requirements</span></span>  
 <span data-ttu-id="692b8-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="692b8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692b8-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="692b8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="692b8-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="692b8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="692b8-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692b8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692b8-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="692b8-134">See also</span></span>

- [<span data-ttu-id="692b8-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="692b8-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="692b8-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="692b8-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
