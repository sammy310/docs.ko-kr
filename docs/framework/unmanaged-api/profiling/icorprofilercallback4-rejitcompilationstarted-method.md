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
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177087"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="6bb6d-102">ICorProfilerCallback4::ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="6bb6d-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="6bb6d-103">JIT(적정 시) 컴파일러가 함수를 다시 컴파일하기 시작했다는 것을 프로파일러에 알린다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6bb6d-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bb6d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6bb6d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6bb6d-106">【인】 JIT 컴파일러가 다시 컴파일하기 시작한 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="6bb6d-107">【인】 함수의 새 버전의 재컴파일 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="6bb6d-108">【인】 `true` 차단으로 인해 런타임이 호출 스레드가 이 콜백에서 반환될 때까지 기다릴 수 있음을 나타냅니다. `false` 을 사용하여 차단이 런타임 작업에 영향을 미치지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="6bb6d-109">값은 `true` 런타임에 해를 끼치지 않지만 프로파일링 결과에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bb6d-110">설명</span><span class="sxs-lookup"><span data-stu-id="6bb6d-110">Remarks</span></span>  
 <span data-ttu-id="6bb6d-111">런타임이 클래스 생성기를 처리하는 `ReJITCompilationStarted` 방식으로 인해 두 쌍 이상의 [ReJITCompilation 완료](icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출을 각 함수에 대해 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="6bb6d-112">예를 들어 런타임은 메서드 A를 다시 컴파일하기 시작하지만 클래스 B에 대한 클래스 생성자는 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="6bb6d-113">따라서 런타임클래스 B에 대한 생성자다시 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="6bb6d-114">생성자가 실행되는 동안 메서드 A를 호출하여 메서드 A를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="6bb6d-115">이 시나리오에서는 메서드 A의 첫 번째 재컴파일이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="6bb6d-116">그러나 메서드 A를 다시 컴파일하려는 두 시도는 JIT 재컴파일 이벤트와 함께 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="6bb6d-117">프로파일러는 두 스레드가 동시에 콜백을 만드는 경우 JIT 재컴파일 콜백 시퀀스를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="6bb6d-118">예를 들어, 스레드 `ReJITCompilationStarted`A 호출 ; 그러나 스레드 A가 [ReJITCompilation을](icorprofilercallback4-rejitcompilationfinished-method.md)호출하기 전에 완료된 스레드 B는 스레드 A에 대한 `ReJITCompilationStarted` 콜백의 함수 ID를 사용하여 [ICorProfilerCallback을](icorprofilercallback-exceptionsearchfunctionenter-method.md) 호출합니다. [ReJITCompilationFinished에](icorprofilercallback4-rejitcompilationfinished-method.md) 대한 호출이 프로파일러에서 아직 수신되지 않았기 때문에 함수 ID가 아직 유효하지 않은 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="6bb6d-119">그러나 이 경우 함수 ID는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb6d-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6bb6d-120">Requirements</span></span>  
 <span data-ttu-id="6bb6d-121">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bb6d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb6d-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6bb6d-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6bb6d-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bb6d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bb6d-124">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb6d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb6d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bb6d-125">See also</span></span>

- [<span data-ttu-id="6bb6d-126">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bb6d-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6bb6d-127">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6bb6d-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="6bb6d-128">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="6bb6d-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="6bb6d-129">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="6bb6d-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
