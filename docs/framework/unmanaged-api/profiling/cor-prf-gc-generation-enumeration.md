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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775078"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="0f161-102">COR_PRF_GC_GENERATION 열거형</span><span class="sxs-lookup"><span data-stu-id="0f161-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="0f161-103">가비지 수집 세대를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f161-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f161-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="0f161-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0f161-105">Members</span></span>  
  
|<span data-ttu-id="0f161-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0f161-106">Member</span></span>|<span data-ttu-id="0f161-107">설명</span><span class="sxs-lookup"><span data-stu-id="0f161-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="0f161-108">개체는 세대 0으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="0f161-109">개체는 1 세대도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="0f161-110">개체는 2 세대도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="0f161-111">개체는 대형 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f161-112">설명</span><span class="sxs-lookup"><span data-stu-id="0f161-112">Remarks</span></span>  
 <span data-ttu-id="0f161-113">가비지 수집기 기준 세대를 나눠 개체에서 메모리 관리 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="0f161-114">가비지 수집기는 현재 세 가지 세대와 0, 1, 2 및 큰 개체에 사용 되는 특수 힙 세그먼트를 번호 매기기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="0f161-115">특정 값 보다 큰 개체는 대형 개체 힙에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="0f161-116">0 세대에 속하는 다른 할당 된 개체를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="0f161-117">가비지 컬렉션이 0 세대에서 발생 한 후에 있는 모든 개체는 1 세대로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="0f161-118">1 세대에서 가비지 수집이 수행 된 후 존재 하는 개체 세대 2로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="0f161-119">사용 세대의 가비지 수집기는 한 번에 할당 된 개체의 하위 집합만 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="0f161-120">합니다 `COR_PRF_GC_GENERATION` 열거형에서 사용 되는 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0f161-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f161-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f161-121">Requirements</span></span>  
 <span data-ttu-id="0f161-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f161-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f161-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f161-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f161-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f161-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f161-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f161-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f161-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f161-126">See also</span></span>

- [<span data-ttu-id="0f161-127">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="0f161-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
