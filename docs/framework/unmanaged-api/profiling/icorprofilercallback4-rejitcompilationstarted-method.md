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
ms.openlocfilehash: 6e340fa08800f31d36e6cfb280cac847a4fca548
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499352"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c1299-102">ICorProfilerCallback4::ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c1299-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c1299-103">JIT (just-in-time) 컴파일러가 함수를 다시 컴파일하기 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1299-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1299-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1299-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1299-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c1299-106">진행 JIT 컴파일러에서 다시 컴파일을 시작한 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c1299-107">진행 새 버전의 함수에 대 한 재컴파일 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c1299-108">[in] `true` 차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 대기 하 게 될 수 있음을 나타내려면이 고, `false`를 지정 하면 차단이 런타임 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c1299-109">값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1299-110">설명</span><span class="sxs-lookup"><span data-stu-id="c1299-110">Remarks</span></span>  
 <span data-ttu-id="c1299-111">`ReJITCompilationStarted`런타임이 클래스 생성자를 처리 하는 방식 때문에 각 함수에 대해 둘 이상의 및 [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c1299-112">예를 들어 런타임은 메서드 A를 다시 컴파일하기 시작 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c1299-113">따라서 런타임은 클래스 B에 대 한 생성자를 다시 컴파일 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c1299-114">생성자는를 실행 하는 동안 메서드 a를 호출 하 여 메서드 A를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c1299-115">이 시나리오에서는 메서드 A의 첫 번째 재컴파일을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c1299-116">그러나 메서드 A를 다시 컴파일하는 두 시도는 JIT 다시 컴파일 이벤트로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c1299-117">두 스레드가 동시에 콜백을 수행 하는 경우에는 프로파일러에서 JIT 다시 컴파일 콜백 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c1299-118">예를 들어 스레드 A가를 호출 합니다. 그러나 스레드 a가 `ReJITCompilationStarted` [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)를 호출 하기 전에 스레드 B는 스레드 a의 콜백에서 함수 ID를 사용 하 여 [ICorProfilerCallback:: exceptionsearchfunctionenter](icorprofilercallback-exceptionsearchfunctionenter-method.md) 를 호출 합니다 `ReJITCompilationStarted` . [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) 에 대 한 호출을 프로파일러가 아직 받지 않았기 때문에 함수 ID가 아직 유효 하지 않은 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c1299-119">그러나이 경우에는 함수 ID가 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1299-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1299-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1299-120">Requirements</span></span>  
 <span data-ttu-id="c1299-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1299-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1299-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1299-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1299-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1299-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1299-124">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1299-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1299-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1299-125">See also</span></span>

- [<span data-ttu-id="c1299-126">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1299-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c1299-127">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1299-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="c1299-128">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c1299-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="c1299-129">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="c1299-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
