---
title: ICorProfilerInfo2::GetObjectGeneration 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: fdfd3715220785a1fa5285b19e677bf0dc190719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433086"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="41e24-102">ICorProfilerInfo2::GetObjectGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="41e24-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="41e24-103">Gets the segment of the heap that contains the specified object.</span><span class="sxs-lookup"><span data-stu-id="41e24-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e24-104">구문</span><span class="sxs-lookup"><span data-stu-id="41e24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41e24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41e24-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="41e24-106">[in] The ID of the object.</span><span class="sxs-lookup"><span data-stu-id="41e24-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="41e24-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span><span class="sxs-lookup"><span data-stu-id="41e24-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="41e24-108">This range contains the specified object.</span><span class="sxs-lookup"><span data-stu-id="41e24-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41e24-109">주의</span><span class="sxs-lookup"><span data-stu-id="41e24-109">Remarks</span></span>  
 <span data-ttu-id="41e24-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span><span class="sxs-lookup"><span data-stu-id="41e24-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="41e24-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="41e24-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41e24-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41e24-112">Requirements</span></span>  
 <span data-ttu-id="41e24-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41e24-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e24-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41e24-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41e24-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41e24-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41e24-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41e24-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e24-117">참조</span><span class="sxs-lookup"><span data-stu-id="41e24-117">See also</span></span>

- [<span data-ttu-id="41e24-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41e24-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="41e24-119">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41e24-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
