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
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702162"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="fdba4-102">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdba4-102">IHostMalloc Interface</span></span>

<span data-ttu-id="fdba4-103">CLR (공용 언어 런타임)이 호스트를 통해 힙에서 세부적인 할당을 요청할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdba4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fdba4-104">Methods</span></span>  
  
|<span data-ttu-id="fdba4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fdba4-105">Method</span></span>|<span data-ttu-id="fdba4-106">설명</span><span class="sxs-lookup"><span data-stu-id="fdba4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdba4-107">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="fdba4-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="fdba4-108">호스트에서 힙에서 요청 된 양의 메모리를 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="fdba4-109">DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="fdba4-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="fdba4-110">호스트가 힙에서 요청 된 메모리 양을 할당 하도록 요청 하 고 추가적으로 메모리가 할당 된 위치를 추적 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="fdba4-111">Free 메서드</span><span class="sxs-lookup"><span data-stu-id="fdba4-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="fdba4-112">메서드를 사용 하 여 할당 된 메모리를 해제 `Alloc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdba4-113">설명</span><span class="sxs-lookup"><span data-stu-id="fdba4-113">Remarks</span></span>  

 <span data-ttu-id="fdba4-114">CLR은 `IHostMalloc` [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdba4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdba4-115">Requirements</span></span>  

 <span data-ttu-id="fdba4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fdba4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdba4-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fdba4-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdba4-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdba4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdba4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdba4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdba4-120">참조</span><span class="sxs-lookup"><span data-stu-id="fdba4-120">See also</span></span>

- [<span data-ttu-id="fdba4-121">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdba4-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="fdba4-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fdba4-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
