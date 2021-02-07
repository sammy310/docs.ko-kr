---
description: '자세히 알아보기: IHostMalloc 인터페이스'
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
ms.openlocfilehash: cd04a0f71fd429ea10b9edcce02806f4afa57148
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708179"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="ff3d9-103">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff3d9-103">IHostMalloc Interface</span></span>

<span data-ttu-id="ff3d9-104">CLR (공용 언어 런타임)이 호스트를 통해 힙에서 세부적인 할당을 요청할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-104">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff3d9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ff3d9-105">Methods</span></span>  
  
|<span data-ttu-id="ff3d9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ff3d9-106">Method</span></span>|<span data-ttu-id="ff3d9-107">설명</span><span class="sxs-lookup"><span data-stu-id="ff3d9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff3d9-108">Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="ff3d9-108">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="ff3d9-109">호스트에서 힙에서 요청 된 양의 메모리를 할당 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-109">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="ff3d9-110">DebugAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="ff3d9-110">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="ff3d9-111">호스트가 힙에서 요청 된 메모리 양을 할당 하도록 요청 하 고 추가적으로 메모리가 할당 된 위치를 추적 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-111">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="ff3d9-112">Free 메서드</span><span class="sxs-lookup"><span data-stu-id="ff3d9-112">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="ff3d9-113">메서드를 사용 하 여 할당 된 메모리를 해제 `Alloc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-113">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff3d9-114">설명</span><span class="sxs-lookup"><span data-stu-id="ff3d9-114">Remarks</span></span>  

 <span data-ttu-id="ff3d9-115">CLR은 `IHostMalloc` [IHostMemoryManager:: CreateMalloc](ihostmemorymanager-createmalloc-method.md) 메서드를 호출 하 여 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-115">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff3d9-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff3d9-116">Requirements</span></span>  

 <span data-ttu-id="ff3d9-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff3d9-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ff3d9-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff3d9-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff3d9-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff3d9-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff3d9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3d9-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff3d9-121">See also</span></span>

- [<span data-ttu-id="ff3d9-122">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff3d9-122">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="ff3d9-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff3d9-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
