---
title: COR_PRF_GC_GENERATION_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: a0ee2c9ce38272caef4960bfe5949c11083c12dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674933"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="16aa0-102">COR_PRF_GC_GENERATION_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="16aa0-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>

<span data-ttu-id="16aa0-103">가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16aa0-104">구문</span><span class="sxs-lookup"><span data-stu-id="16aa0-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="16aa0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="16aa0-105">Members</span></span>  
  
|<span data-ttu-id="16aa0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="16aa0-106">Member</span></span>|<span data-ttu-id="16aa0-107">설명</span><span class="sxs-lookup"><span data-stu-id="16aa0-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="16aa0-108">메모리 블록이 속한 세대를 지정 하는 [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-108">A value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="16aa0-109">메모리 블록의 시작 위치를 지정 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="16aa0-110">메모리 블록에서 사용 되는 메모리의 양 (블록 내에 사용 되는 메모리 양)의 크기를 지정 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="16aa0-111">메모리 블록의 크기를 지정 하는 정수에 대 한 포인터입니다. 즉, 블록에 예약 된 메모리의 양입니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16aa0-112">설명</span><span class="sxs-lookup"><span data-stu-id="16aa0-112">Remarks</span></span>  

 <span data-ttu-id="16aa0-113">이 `rangeLength` 값은 구조체를 사용 하는 [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) 또는 [ICorProfilerInfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)모두 `COR_PRF_GC_GENERATION_RANGE` [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) 또는 [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 메서드에서 호출 되는 경우에만 정확 하 게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16aa0-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16aa0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16aa0-114">Requirements</span></span>  

 <span data-ttu-id="16aa0-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16aa0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16aa0-116">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="16aa0-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="16aa0-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16aa0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16aa0-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16aa0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aa0-119">참조</span><span class="sxs-lookup"><span data-stu-id="16aa0-119">See also</span></span>

- [<span data-ttu-id="16aa0-120">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="16aa0-120">Profiling Structures</span></span>](profiling-structures.md)
