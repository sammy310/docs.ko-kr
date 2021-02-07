---
description: '자세히 알아보기: IHostMemoryManager 인터페이스'
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
ms.openlocfilehash: c9b6f83b5c70a53388e886e1047798f660b826e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707887"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="1eba0-103">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eba0-103">IHostMemoryManager Interface</span></span>

<span data-ttu-id="1eba0-104">표준 Win32 가상 메모리 함수를 사용 하는 대신 CLR (공용 언어 런타임)에서 호스트를 통해 가상 메모리 요청을 수행할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-104">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1eba0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-105">Methods</span></span>  
  
|<span data-ttu-id="1eba0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-106">Method</span></span>|<span data-ttu-id="1eba0-107">설명</span><span class="sxs-lookup"><span data-stu-id="1eba0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1eba0-108">AcquiredVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-108">AcquiredVirtualAddressSpace Method</span></span>](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="1eba0-109">CLR (공용 언어 런타임)이 운영 체제에서 지정 된 메모리를 획득 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-109">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="1eba0-110">CreateMAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-110">CreateMAlloc Method</span></span>](ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="1eba0-111">호스트에서 만든 힙에서 메모리 할당을 요청 하는 데 사용 되는 [IHostMAlloc](ihostmalloc-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-111">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="1eba0-112">GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-112">GetMemoryLoad Method</span></span>](ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="1eba0-113">호스트에서 보고 하는 현재 사용 중인 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-113">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="1eba0-114">NeedsVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-114">NeedsVirtualAddressSpace Method</span></span>](ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="1eba0-115">CLR에서 지정 된 메모리를 사용 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-115">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="1eba0-116">RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-116">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="1eba0-117">호스트에서 컴퓨터의 현재 메모리 로드를 알리기 위해 호출 하는 콜백 함수에 대 한 포인터를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-117">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="1eba0-118">ReleasedVirtualAddressSpace 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-118">ReleasedVirtualAddressSpace Method</span></span>](ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="1eba0-119">지정 된 메모리를 사용 하 여 CLR이 완료 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-119">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="1eba0-120">VirtualAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-120">VirtualAlloc Method</span></span>](ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="1eba0-121">호출 프로세스의 가상 주소 공간에서 페이지 영역을 예약 하거나 커밋하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-121">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="1eba0-122">VirtualFree 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-122">VirtualFree Method</span></span>](ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="1eba0-123">호출 프로세스의 가상 주소 공간 내에서 페이지 영역을 릴리스, 커밋 취소 또는 해제 하 고 커밋을 취소 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-123">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="1eba0-124">VirtualProtect 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-124">VirtualProtect Method</span></span>](ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="1eba0-125">호출 프로세스의 가상 주소 공간에서 커밋된 페이지 영역에 대 한 보호를 변경 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-125">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="1eba0-126">VirtualQuery 메서드</span><span class="sxs-lookup"><span data-stu-id="1eba0-126">VirtualQuery Method</span></span>](ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="1eba0-127">호출 프로세스의 가상 주소 공간에 있는 페이지 범위에 대 한 정보를 검색 하는 해당 Win32 함수에 대 한 논리 래퍼로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-127">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eba0-128">설명</span><span class="sxs-lookup"><span data-stu-id="1eba0-128">Remarks</span></span>  

 <span data-ttu-id="1eba0-129">`IHostMemoryManager` 는 또한 CLR에서 힙에 대 한 메모리 요청을 수행 하 고 호스트에서 보고 하는 프로세스의 메모리 압력 수준을 가져오는 포인터를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-129">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eba0-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eba0-130">Requirements</span></span>  

 <span data-ttu-id="1eba0-131">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1eba0-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eba0-132">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1eba0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1eba0-133">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eba0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1eba0-134">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eba0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eba0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eba0-135">See also</span></span>

- [<span data-ttu-id="1eba0-136">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eba0-136">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="1eba0-137">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1eba0-137">Hosting Interfaces</span></span>](hosting-interfaces.md)
