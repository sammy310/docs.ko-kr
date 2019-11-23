---
title: ICorProfilerInfo2::GetGenerationBounds 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
ms.openlocfilehash: 11157bca2d0f0be2b9b9bc36c382188a43db22a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433120"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="ef3f3-102">ICorProfilerInfo2::GetGenerationBounds 메서드</span><span class="sxs-lookup"><span data-stu-id="ef3f3-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="ef3f3-103">다양한 가비지 컬렉션 세대를 구성하는 힙 세그먼트인 메모리 영역을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef3f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef3f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef3f3-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="ef3f3-106">[in] `ranges` 배열에 대해 호출자가 할당한 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="ef3f3-107">[out] 일부 또는 전체가 `ranges` 배열로 반환되는 총 범위 수를 지정하는 정수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="ef3f3-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef3f3-109">주의</span><span class="sxs-lookup"><span data-stu-id="ef3f3-109">Remarks</span></span>  
 <span data-ttu-id="ef3f3-110">가비지 컬렉션이 진행되고 있지 않으면 모든 프로파일러 콜백에서 `GetGenerationBounds` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="ef3f3-111">대부분의 세대 이동은 가비지 수집 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="ef3f3-112">컬렉션 간에 세대가 증가할 수 있지만 일반적으로 이동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="ef3f3-113">따라서 가장 흥미로운 `GetGenerationBounds` 호출 위치는 `ICorProfilerCallback2::GarbageCollectionStarted` 및 `ICorProfilerCallback2::GarbageCollectionFinished`입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="ef3f3-114">프로그램 시작 중에 일부 개체는 CLR(공용 언어 런타임)에 의해 일반적으로 3세대 및 0세대에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="ef3f3-115">따라서 관리 코드 실행이 시작되는 시간에는 이러한 세대에 이미 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="ef3f3-116">1세대와 2세대는 가비지 수집기에서 생성되는 더미 개체를 제외하고 일반적으로 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="ef3f3-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="ef3f3-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="ef3f3-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="ef3f3-119">이 함수는 호출자 할당 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3f3-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef3f3-120">Requirements</span></span>  
 <span data-ttu-id="ef3f3-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef3f3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3f3-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef3f3-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef3f3-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef3f3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef3f3-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3f3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3f3-125">참조</span><span class="sxs-lookup"><span data-stu-id="ef3f3-125">See also</span></span>

- [<span data-ttu-id="ef3f3-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef3f3-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ef3f3-127">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef3f3-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="ef3f3-128">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef3f3-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="ef3f3-129">프로파일링</span><span class="sxs-lookup"><span data-stu-id="ef3f3-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
