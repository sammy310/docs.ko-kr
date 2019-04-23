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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5f9104dded44540c47c955c15354d8d76a27650
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183074"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="1066c-102">ICorProfilerCallback2::GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="1066c-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="1066c-103">가비지 수집이 시작 되었습니다 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1066c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1066c-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1066c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1066c-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="1066c-106">[in] 에 있는 항목의 총 수를 `generationCollected` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="1066c-107">[in] 부울 값의 배열을 `true` 고, 그렇지 않으면이 가비지 수집에 의해 수집 된 배열 인덱스에 해당 하는 생성 되 면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="1066c-108">배열 값으로 인덱싱된 합니다 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) 생성을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="1066c-109">[in] 값을 [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) 가비지 수집 이유를 나타내는 열거형 도출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1066c-110">설명</span><span class="sxs-lookup"><span data-stu-id="1066c-110">Remarks</span></span>  
 <span data-ttu-id="1066c-111">이 가비지 컬렉션에 속하는 모든 콜백 간에 발생 합니다 `GarbageCollectionStarted` 콜백 및 해당 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="1066c-112">이러한 콜백을 동일한 스레드에서 발생 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="1066c-113">프로파일러를 검사 하는 동안 원래 위치에서 개체에 대 한 안전 합니다 `GarbageCollectionStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="1066c-114">가비지 수집기에서 반환 된 후 개체를 이동할 예정 `GarbageCollectionStarted`합니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="1066c-115">이 콜백에서 프로파일러가 반환 된 후 프로파일러 잘못 된 것을 받을 때까지 모든 개체 Id를 고려해 야는 `ICorProfilerCallback2::GarbageCollectionFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="1066c-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1066c-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1066c-116">Requirements</span></span>  
 <span data-ttu-id="1066c-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1066c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1066c-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1066c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1066c-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1066c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1066c-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1066c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1066c-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="1066c-121">See also</span></span>

- [<span data-ttu-id="1066c-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1066c-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1066c-123">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1066c-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
