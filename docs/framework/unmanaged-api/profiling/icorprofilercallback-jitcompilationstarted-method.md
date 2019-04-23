---
title: ICorProfilerCallback::JITCompilationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075323"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="caf64-102">ICorProfilerCallback::JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="caf64-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="caf64-103">Just-in-time (JIT) 컴파일러에서 함수 컴파일을 시작 했다는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf64-104">구문</span><span class="sxs-lookup"><span data-stu-id="caf64-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caf64-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="caf64-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="caf64-106">[in] 컴파일이 시작 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="caf64-107">[in] 프로파일러 차단 여부를 나타내는 값을 런타임 작업에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="caf64-108">값이 `true` 런타임에서이 콜백에서; 반환할 호출 스레드에 대 한 대기를 차단 않을 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="caf64-109">하지만 값 `true` 런타임 나쁜 영향을 주지, 프로 파일링 결과 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caf64-110">설명</span><span class="sxs-lookup"><span data-stu-id="caf64-110">Remarks</span></span>  
 <span data-ttu-id="caf64-111">둘 이상의 쌍을 받을 수 있기 `JITCompilationStarted` 하 고 [icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) 생성자를 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="caf64-112">예를 들어, JIT 컴파일되나요 메서드 A는 런타임이 시작 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="caf64-113">따라서 런타임에서 JIT 컴파일을 클래스 B에 대 한 생성자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="caf64-114">생성자는 실행 되는 동안 메서드 A 다시 JIT 컴파일할 수 하는 메서드를 호출을 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="caf64-115">이 시나리오에서는 첫 번째 메서드는 JIT 컴파일을 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="caf64-116">그러나 두 하려고 JIT 컴파일되나요 메서드는 JIT 컴파일 이벤트를 사용 하 여 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="caf64-117">프로파일러는 메서드에 대 한 Microsoft MSIL (intermediate language) 코드를 호출 하 여 대체 하려는 경우는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드를 둘 다에 대해 이렇게 해야 `JITCompilationStarted` 이벤트 하지만 동일한 MSIL 블록을 사용할 수 있습니다 보십시오.</span><span class="sxs-lookup"><span data-stu-id="caf64-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="caf64-118">프로파일러는 두 스레드가 동시에 중인 콜백 하는 경우 JIT 콜백 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="caf64-119">예를 들어, 호출 스레드는 `JITCompilationStarted`합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="caf64-120">그러나 스레드는 호출 전에 `JITCompilationFinished`, 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) 스레드 A의에서 함수 ID를 가진 `JITCompilationStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="caf64-121">함수 ID는 아직 유효 하지 않은 것으로 보일 수 때문에 대 한 호출 `JITCompilationFinished` 프로파일러에 의해 아직 받지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="caf64-122">그러나 이와 같은 경우 함수 ID가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caf64-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf64-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="caf64-123">Requirements</span></span>  
 <span data-ttu-id="caf64-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="caf64-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf64-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="caf64-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="caf64-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf64-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf64-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf64-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf64-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="caf64-128">See also</span></span>

- [<span data-ttu-id="caf64-129">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="caf64-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="caf64-130">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="caf64-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
