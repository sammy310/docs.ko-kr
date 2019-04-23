---
title: IHostMalloc 인터페이스
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136414"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="e4845-102">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4845-102">IHostMalloc Interface</span></span>
<span data-ttu-id="e4845-103">CLR (공용 언어 런타임)에서 호스트를 통해 힙의 세분화 된 할당을 요청할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4845-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4845-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e4845-104">Methods</span></span>  
  
|<span data-ttu-id="e4845-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e4845-105">Method</span></span>|<span data-ttu-id="e4845-106">설명</span><span class="sxs-lookup"><span data-stu-id="e4845-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4845-107">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="e4845-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="e4845-108">힙에서 호스트 요청 된 메모리 양을 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4845-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="e4845-109">DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="e4845-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="e4845-110">호스트 힙에에서 요청 된 크기의 메모리를 할당 하 고 또한 메모리가 할당 된 위치를 추적을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4845-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="e4845-111">Free 메서드</span><span class="sxs-lookup"><span data-stu-id="e4845-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="e4845-112">사용 하 여 할당 된 메모리를 해제 합니다 `Alloc` 메서드.</span><span class="sxs-lookup"><span data-stu-id="e4845-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4845-113">설명</span><span class="sxs-lookup"><span data-stu-id="e4845-113">Remarks</span></span>  
 <span data-ttu-id="e4845-114">CLR에 대 한 인터페이스 포인터를 가져옵니다는 `IHostMalloc` 를 호출 하 여 인스턴스를 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e4845-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4845-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4845-115">Requirements</span></span>  
 <span data-ttu-id="e4845-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4845-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4845-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4845-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4845-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e4845-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4845-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4845-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4845-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4845-120">See also</span></span>

- [<span data-ttu-id="e4845-121">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4845-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e4845-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4845-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
