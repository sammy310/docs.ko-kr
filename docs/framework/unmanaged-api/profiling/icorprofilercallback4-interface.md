---
title: ICorProfilerCallback4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: a3394820f673e35777e1749229d4f8319841ca58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439384"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="7b962-102">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b962-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="7b962-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span><span class="sxs-lookup"><span data-stu-id="7b962-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b962-104">메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-104">Methods</span></span>  
  
|<span data-ttu-id="7b962-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-105">Method</span></span>|<span data-ttu-id="7b962-106">설명</span><span class="sxs-lookup"><span data-stu-id="7b962-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b962-107">GetReJITParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="7b962-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span><span class="sxs-lookup"><span data-stu-id="7b962-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="7b962-109">MovedReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="7b962-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7b962-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="7b962-111">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="7b962-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span><span class="sxs-lookup"><span data-stu-id="7b962-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="7b962-113">ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="7b962-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span><span class="sxs-lookup"><span data-stu-id="7b962-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="7b962-115">ReJITError 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="7b962-116">Reports an error encountered while processing a recompile request.</span><span class="sxs-lookup"><span data-stu-id="7b962-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="7b962-117">SurvivingReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="7b962-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="7b962-118">비압축 가비지 수집의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="7b962-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b962-119">주의</span><span class="sxs-lookup"><span data-stu-id="7b962-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b962-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b962-120">Requirements</span></span>  
 <span data-ttu-id="7b962-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b962-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b962-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7b962-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7b962-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b962-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b962-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b962-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b962-125">참조</span><span class="sxs-lookup"><span data-stu-id="7b962-125">See also</span></span>

- [<span data-ttu-id="7b962-126">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b962-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="7b962-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b962-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="7b962-128">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b962-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
