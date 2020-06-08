---
title: COR_PRF_GC_GENERATION 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: b7a068efcf20b2028e9c193567d15b59e582febf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500925"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="e4d3b-102">COR_PRF_GC_GENERATION 열거형</span><span class="sxs-lookup"><span data-stu-id="e4d3b-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="e4d3b-103">가비지 컬렉션 생성을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e4d3b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="e4d3b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e4d3b-105">Members</span></span>  
  
|<span data-ttu-id="e4d3b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e4d3b-106">Member</span></span>|<span data-ttu-id="e4d3b-107">설명</span><span class="sxs-lookup"><span data-stu-id="e4d3b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="e4d3b-108">개체는 0 세대로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="e4d3b-109">개체는 1 세대로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="e4d3b-110">개체는 2 세대로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="e4d3b-111">개체가 대량 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-111">The object is stored in the large-object heap.</span></span>|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|<span data-ttu-id="e4d3b-112">개체는 고정 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-112">The object is stored in the pinned-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4d3b-113">설명</span><span class="sxs-lookup"><span data-stu-id="e4d3b-113">Remarks</span></span>  
 <span data-ttu-id="e4d3b-114">가비지 수집기는 개체를 age를 기반으로 하는 세대로 분할 하 여 메모리 관리 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-114">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="e4d3b-115">가비지 수집기는 현재 세 세대 (0, 1, 2) 및 두 개의 특수 힙 세그먼트를 사용 합니다. 하나는 큰 개체이 고 다른 하나는 고정 된 개체에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-115">The garbage collector currently uses three generations, numbered 0, 1, and 2, and two special heap segments, one for large objects and one for pinned objects.</span></span>
  
 <span data-ttu-id="e4d3b-116">크기가 임계값 보다 큰 개체는 큰 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-116">Objects whose size is larger than a threshold value are stored in the large-object heap.</span></span> <span data-ttu-id="e4d3b-117">고정 된 개체는 고정 개체 힙에 할당 되어 일반 힙에 할당 되는 성능 비용을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-117">Pinned objects can be allocated to the pinned-object heap to avoid the performance cost of allocating them on the normal heaps.</span></span> <span data-ttu-id="e4d3b-118">할당 된 다른 개체는 0 세대에 속하는 것으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-118">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="e4d3b-119">0 세대에서 가비지 수집 후에 존재 하는 모든 개체는 1 세대로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-119">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="e4d3b-120">1 세대에서 가비지 수집이 수행 된 후 존재 하는 개체는 2 세대로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-120">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="e4d3b-121">세대를 사용 하면 가비지 수집기에서 한 번에 할당 된 개체의 하위 집합만 작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-121">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="e4d3b-122">`COR_PRF_GC_GENERATION`열거형은 [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) 구조에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-122">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d3b-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4d3b-123">Requirements</span></span>  
 <span data-ttu-id="e4d3b-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d3b-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4d3b-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4d3b-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d3b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d3b-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d3b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d3b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4d3b-128">See also</span></span>

- [<span data-ttu-id="e4d3b-129">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="e4d3b-129">Profiling Enumerations</span></span>](profiling-enumerations.md)
