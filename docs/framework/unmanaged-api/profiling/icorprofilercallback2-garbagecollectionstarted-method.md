---
title: ICorProfilerCallback2::GarbageCollectionStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439822"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="70901-102">ICorProfilerCallback2::GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="70901-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="70901-103">Notifies the code profiler that garbage collection has started.</span><span class="sxs-lookup"><span data-stu-id="70901-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70901-104">구문</span><span class="sxs-lookup"><span data-stu-id="70901-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70901-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70901-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="70901-106">[in] The total number of entries in the `generationCollected` array.</span><span class="sxs-lookup"><span data-stu-id="70901-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="70901-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span><span class="sxs-lookup"><span data-stu-id="70901-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="70901-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span><span class="sxs-lookup"><span data-stu-id="70901-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="70901-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span><span class="sxs-lookup"><span data-stu-id="70901-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70901-110">주의</span><span class="sxs-lookup"><span data-stu-id="70901-110">Remarks</span></span>  
 <span data-ttu-id="70901-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="70901-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="70901-112">These callbacks need not occur on the same thread.</span><span class="sxs-lookup"><span data-stu-id="70901-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="70901-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="70901-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="70901-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="70901-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="70901-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="70901-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70901-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70901-116">Requirements</span></span>  
 <span data-ttu-id="70901-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70901-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70901-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70901-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70901-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70901-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70901-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70901-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70901-121">참조</span><span class="sxs-lookup"><span data-stu-id="70901-121">See also</span></span>

- [<span data-ttu-id="70901-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70901-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="70901-123">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70901-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
