---
title: ICorProfilerCallback3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: 25d674a143019ac5d724e36f03f36c79602b1e11
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439504"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="4e469-102">ICorProfilerCallback3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e469-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="4e469-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span><span class="sxs-lookup"><span data-stu-id="4e469-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e469-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4e469-104">Methods</span></span>  
  
|<span data-ttu-id="4e469-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4e469-105">Method</span></span>|<span data-ttu-id="4e469-106">설명</span><span class="sxs-lookup"><span data-stu-id="4e469-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e469-107">InitializeForAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="4e469-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="4e469-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span><span class="sxs-lookup"><span data-stu-id="4e469-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="4e469-109">ProfilerAttachComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="4e469-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="4e469-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span><span class="sxs-lookup"><span data-stu-id="4e469-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="4e469-111">ProfilerDetachSucceeded 메서드</span><span class="sxs-lookup"><span data-stu-id="4e469-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="4e469-112">CLR(공용 언어 런타임)이 프로파일러 DLL을 언로드한다고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4e469-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e469-113">주의</span><span class="sxs-lookup"><span data-stu-id="4e469-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e469-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e469-114">Requirements</span></span>  
 <span data-ttu-id="4e469-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e469-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e469-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e469-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e469-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e469-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e469-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e469-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e469-119">참조</span><span class="sxs-lookup"><span data-stu-id="4e469-119">See also</span></span>

- [<span data-ttu-id="4e469-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e469-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4e469-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e469-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4e469-122">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e469-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="4e469-123">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e469-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
