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
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866236"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="b17be-102">ICorProfilerCallback::JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="b17be-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="b17be-103">JIT (just-in-time) 컴파일러가 함수 컴파일을 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b17be-104">구문</span><span class="sxs-lookup"><span data-stu-id="b17be-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b17be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b17be-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b17be-106">진행 컴파일을 시작 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="b17be-107">진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="b17be-108">차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 대기 하는 경우 값이 `true` 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="b17be-109">`true` 값은 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b17be-110">주의</span><span class="sxs-lookup"><span data-stu-id="b17be-110">Remarks</span></span>  
 <span data-ttu-id="b17be-111">런타임이 클래스 생성자를 처리 하는 방식 때문에 각 함수에 대해 둘 이상의 `JITCompilationStarted` 및 [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) 호출을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="b17be-112">예를 들어 런타임은 메서드 A를 JIT 컴파일하도록 시작 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="b17be-113">따라서 런타임은 클래스 B에 대 한 생성자를 JIT로 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="b17be-114">생성자는를 실행 하는 동안 메서드 a를 호출 하 여 메서드 A를 다시 JIT 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="b17be-115">이 시나리오에서는 메서드 A의 첫 번째 JIT 컴파일이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="b17be-116">그러나 메서드 A를 JIT 컴파일하는 두 시도는 JIT 컴파일 이벤트로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="b17be-117">프로파일러가 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드를 호출 하 여 메서드 A의 MSIL (Microsoft 중간 언어) 코드를 바꾸려는 경우 두 `JITCompilationStarted` 이벤트에 대해 모두이 작업을 수행 해야 하지만 둘 다에 대해 동일한 msil 블록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="b17be-118">두 스레드가 동시에 콜백을 수행 하는 경우 프로파일러는 JIT 콜백의 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="b17be-119">예를 들어 스레드 A가 `JITCompilationStarted`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="b17be-120">그러나 스레드 A가 `JITCompilationFinished`를 호출 하기 전에 스레드 B는 스레드 A의 `JITCompilationStarted` 콜백에서 함수 ID를 사용 하 여 [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="b17be-121">`JITCompilationFinished`에 대 한 호출이 아직 수신 되지 않았기 때문에 함수 ID가 유효 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="b17be-122">그러나 이와 같은 경우에는 함수 ID가 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b17be-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b17be-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b17be-123">Requirements</span></span>  
 <span data-ttu-id="b17be-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b17be-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b17be-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b17be-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b17be-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b17be-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b17be-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b17be-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17be-128">참조</span><span class="sxs-lookup"><span data-stu-id="b17be-128">See also</span></span>

- [<span data-ttu-id="b17be-129">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b17be-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b17be-130">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="b17be-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
