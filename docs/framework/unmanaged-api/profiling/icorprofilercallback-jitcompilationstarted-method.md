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
ms.openlocfilehash: 7ce100a68a3e2b8963ed14bbf044fa9ba11d629f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725523"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="6f534-102">ICorProfilerCallback::JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="6f534-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>

<span data-ttu-id="6f534-103">JIT (just-in-time) 컴파일러가 함수 컴파일을 시작 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f534-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f534-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f534-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f534-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="6f534-106">진행 컴파일을 시작 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="6f534-107">진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="6f534-108">`true`차단 하면 호출 스레드가이 콜백에서 반환 될 때까지 런타임이 대기 하 게 될 수 있으면 값이이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="6f534-109">값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f534-110">설명</span><span class="sxs-lookup"><span data-stu-id="6f534-110">Remarks</span></span>  

 <span data-ttu-id="6f534-111">`JITCompilationStarted`런타임이 클래스 생성자를 처리 하는 방식 때문에 각 함수에 대해 둘 이상의 및 [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) 호출을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="6f534-112">예를 들어 런타임은 메서드 A를 JIT 컴파일하도록 시작 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="6f534-113">따라서 런타임은 클래스 B에 대 한 생성자를 JIT로 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="6f534-114">생성자는를 실행 하는 동안 메서드 a를 호출 하 여 메서드 A를 다시 JIT 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="6f534-115">이 시나리오에서는 메서드 A의 첫 번째 JIT 컴파일이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="6f534-116">그러나 메서드 A를 JIT 컴파일하는 두 시도는 JIT 컴파일 이벤트로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="6f534-117">프로파일러가 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드를 호출 하 여 메서드 A의 MSIL (Microsoft 중간 언어) 코드를 바꾸려는 경우 두 이벤트 모두에 대해이 작업을 수행 해야 `JITCompilationStarted` 하지만 둘 다에 대해 동일한 msil 블록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="6f534-118">두 스레드가 동시에 콜백을 수행 하는 경우 프로파일러는 JIT 콜백의 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="6f534-119">예를 들어 스레드 A를 호출 `JITCompilationStarted` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="6f534-120">그러나 스레드 A가를 호출 하기 전에 스레드 `JITCompilationFinished` B는 스레드 a의 콜백에서 함수 ID를 사용 하 여 [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) 를 호출 `JITCompilationStarted` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="6f534-121">에 대 한 호출이 `JITCompilationFinished` 프로파일러에서 아직 수신 되지 않았기 때문에 함수 ID가 아직 유효 하지 않은 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="6f534-122">그러나 이와 같은 경우에는 함수 ID가 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f534-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f534-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f534-123">Requirements</span></span>  

 <span data-ttu-id="6f534-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f534-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f534-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f534-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f534-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f534-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f534-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f534-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f534-128">참조</span><span class="sxs-lookup"><span data-stu-id="6f534-128">See also</span></span>

- [<span data-ttu-id="6f534-129">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f534-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6f534-130">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="6f534-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
