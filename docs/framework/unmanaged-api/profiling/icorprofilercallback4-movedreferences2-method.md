---
title: ICorProfilerCallback4::MovedReferences2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 37d5f5e8294bb87a8796d6dcae046864904b096b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439376"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="dfc7e-102">ICorProfilerCallback4::MovedReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="dfc7e-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>
<span data-ttu-id="dfc7e-103">압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고하려고 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="dfc7e-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="dfc7e-105">This callback replaces the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-105">This callback replaces the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc7e-106">구문</span><span class="sxs-lookup"><span data-stu-id="dfc7e-106">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc7e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfc7e-107">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="dfc7e-108">[in] 압축 가비지 컬렉션 후에 이동된 연속 개체 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="dfc7e-109">즉, `cMovedObjectIDRanges` 값은 `oldObjectIDRangeStart`, `newObjectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="dfc7e-110">`MovedReferences2`의 다음 세 인수는 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="dfc7e-111">즉, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` 및 `cObjectIDRangeLength[i]`는 모두 단일 연속 개체 블록과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="dfc7e-112">[in] 메모리에서 연속 라이브 개체 블록의 이전(가비지 수집 전) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="dfc7e-113">[in] 메모리에서 연속 라이브 개체 블록의 새(가비지 컬렉션 후) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="dfc7e-114">[in] 메모리의 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="dfc7e-115">크기는 `oldObjectIDRangeStart` 및 `newObjectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfc7e-116">주의</span><span class="sxs-lookup"><span data-stu-id="dfc7e-116">Remarks</span></span>  
 <span data-ttu-id="dfc7e-117">압축 가비지 수집기는 데드 개체가 사용한 메모리를 회수하고 확보된 공간을 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="dfc7e-118">따라서 라이브 개체가 힙 내에서 이동될 수 있고 이전 알림으로 분산된 `ObjectID` 값이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="dfc7e-119">기존 `ObjectID` 값(`oldObjectID`)이 다음 범위 내에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="dfc7e-120">이 경우 범위 시작부터 개체 시작까지 오프셋은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="dfc7e-121">다음 범위에 있는 `i` 값에 대해</span><span class="sxs-lookup"><span data-stu-id="dfc7e-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="dfc7e-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="dfc7e-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="dfc7e-123">새 `ObjectID`를 다음과 같이 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="dfc7e-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="dfc7e-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="dfc7e-125">콜백 자체가 진행되는 동안 `MovedReferences2`를 통해 전달된 `ObjectID` 값은 유효하지 않습니다. 가비지 수집기가 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="dfc7e-126">그러므로 프로파일러는 `MovedReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="dfc7e-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="dfc7e-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="dfc7e-129">프로파일러는 두 번째 메서드 호출을 방지하기 위해 `MovedReferences2` 메서드에서 실패를 나타내는 HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc7e-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfc7e-130">Requirements</span></span>  
 <span data-ttu-id="dfc7e-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfc7e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc7e-132">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dfc7e-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dfc7e-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfc7e-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfc7e-134">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc7e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc7e-135">참조</span><span class="sxs-lookup"><span data-stu-id="dfc7e-135">See also</span></span>

- [<span data-ttu-id="dfc7e-136">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfc7e-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dfc7e-137">MovedReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="dfc7e-137">MovedReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="dfc7e-138">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfc7e-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="dfc7e-139">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dfc7e-139">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="dfc7e-140">프로파일링</span><span class="sxs-lookup"><span data-stu-id="dfc7e-140">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
