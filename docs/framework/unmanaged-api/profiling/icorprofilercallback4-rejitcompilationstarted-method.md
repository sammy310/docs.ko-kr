---
title: ICorProfilerCallback4::ReJITCompilationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075901"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="a43bb-102">ICorProfilerCallback4::ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="a43bb-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="a43bb-103">함수를 다시 컴파일 (JIT)-just-in-time 컴파일러가 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="a43bb-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a43bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a43bb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a43bb-106">[in] JIT 컴파일러는 recompile을 시작 했음을 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="a43bb-107">[in] 함수의 새 버전의 다시 컴파일 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="a43bb-108">[in] `true` 차단 호출 스레드가이 콜백에서; 반환 될 때까지 대기할 런타임 시를 나타내려면 `false` 는 차단 영향을 주지 것입니다 런타임의 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="a43bb-109">값 `true` 런타임에 영향을 주지 않으며 하지만 프로 파일링 결과 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a43bb-110">설명</span><span class="sxs-lookup"><span data-stu-id="a43bb-110">Remarks</span></span>  
 <span data-ttu-id="a43bb-111">둘 이상의 쌍을 받을 수 있기 `ReJITCompilationStarted` 하 고 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="a43bb-112">예를 들어 메서드는, 다시 컴파일 런타임이 시작 있지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="a43bb-113">따라서 런타임 클래스 B에 대 한 생성자를 다시 컴파일 및 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="a43bb-114">생성자는 실행 되는 동안 메서드 A 다시 컴파일해야 하는 메서드를 호출을 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="a43bb-115">이 시나리오에서는 첫 번째 메서드는 다시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="a43bb-116">그러나 둘 다 JIT 다시 컴파일 이벤트를 사용 하 여이 보고 하는 메서드를 다시 컴파일할 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="a43bb-117">프로파일러는 두 스레드가 동시에 중인 콜백 하는 경우 JIT 다시 컴파일 콜백 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="a43bb-118">그러나 예를 들어 스레드는 호출 `ReJITCompilationStarted`; 스레드는 호출 전에 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) 함수 ID를 사용 하 여 `ReJITCompilationStarted` A. 스레드에 대 한 콜백 함수 ID는 아직 유효 하지 않은 것으로 보일 수 때문에 대 한 호출 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 프로파일러에 의해 아직 받지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="a43bb-119">그러나이 경우 함수 ID는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a43bb-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43bb-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a43bb-120">Requirements</span></span>  
 <span data-ttu-id="a43bb-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a43bb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a43bb-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a43bb-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a43bb-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a43bb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a43bb-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a43bb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43bb-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="a43bb-125">See also</span></span>

- [<span data-ttu-id="a43bb-126">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a43bb-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a43bb-127">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a43bb-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="a43bb-128">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a43bb-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="a43bb-129">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="a43bb-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
