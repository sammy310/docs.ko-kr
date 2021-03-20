---
description: '자세히 알아보기: ICorProfilerCallback:: JITCachedFunctionSearchStarted 메서드'
title: ICorProfilerCallback::JITCachedFunctionSearchStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 3f384c1a02da1747b28701d2eba994b56a85c18f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759957"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="853c5-103">ICorProfilerCallback::JITCachedFunctionSearchStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="853c5-103">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>

<span data-ttu-id="853c5-104">NGen.exe (네이티브 이미지 생성기)를 사용 하 여 이전에 컴파일된 함수에 대해 검색이 시작 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-104">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="853c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="853c5-105">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="853c5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="853c5-106">Parameters</span></span>

<span data-ttu-id="853c5-107">`functionId` 진행 검색을 수행 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-107">`functionId` [in] The ID of the function for which the search is being performed.</span></span>

<span data-ttu-id="853c5-108">`pbUseCachedFunction` [out] `true` 실행 엔진이 캐시 된 버전의 함수 (있는 경우)를 사용 해야 하면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-108">`pbUseCachedFunction` [out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="853c5-109">값이 이면 `false` 실행 엔진이 jit 컴파일되지 않는 버전을 사용 하는 대신 함수를 jit 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-109">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="853c5-110">설명</span><span class="sxs-lookup"><span data-stu-id="853c5-110">Remarks</span></span>  

 <span data-ttu-id="853c5-111">.NET Framework 버전 2.0에서는 `JITCachedFunctionSearchStarted` 일반 NGen 이미지의 모든 함수에 대해 및 [ICorProfilerCallback:: JITCachedFunctionSearchFinished 메서드](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) 콜백이 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-111">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="853c5-112">프로필에 대해 최적화 된 NGen 이미지만이 이미지의 모든 함수에 대해 콜백을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-112">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="853c5-113">그러나 추가 오버 헤드로 인해 프로파일러는 이러한 콜백을 사용 하 여 함수를 JIT (just-in-time)로 강제 컴파일하는 경우에만 프로파일러 최적화 NGen 이미지를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-113">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="853c5-114">그렇지 않으면 프로파일러는 함수 정보를 수집 하기 위해 지연 전략을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-114">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="853c5-115">프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동일한 메서드를 동시에 호출 하는 경우를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-115">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="853c5-116">예를 들어 스레드 A가를 호출 하 `JITCachedFunctionSearchStarted` 고 프로파일러는 *PBUSECACHEDFUNCTION* 을 FALSE로 설정 하 여 강제로 JIT 컴파일을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-116">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction* to FALSE to force JIT compilation.</span></span> <span data-ttu-id="853c5-117">그런 다음 스레드 A는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 및 [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-117">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="853c5-118">이제 스레드 B `JITCachedFunctionSearchStarted` 는 동일한 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-118">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="853c5-119">프로파일러에서 함수를 JIT 컴파일하는 의도를 언급 했더라도 프로파일러는 프로파일러가 스레드 A의 호출에 응답 하기 전에 콜백을 보내기 때문에 두 번째 콜백을 수신 합니다 `JITCachedFunctionSearchStarted` .</span><span class="sxs-lookup"><span data-stu-id="853c5-119">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="853c5-120">스레드가 호출 하는 순서는 스레드를 예약 하는 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-120">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="853c5-121">프로파일러에서 중복 콜백을 받으면에서 참조 하는 값을 `pbUseCachedFunction` 모든 중복 콜백에 대 한 동일한 값으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-121">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="853c5-122">즉, `JITCachedFunctionSearchStarted` 동일한 값을 사용 하 여를 여러 번 호출 하면 `functionId` 프로파일러가 매번 동일한 응답을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="853c5-122">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="853c5-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="853c5-123">Requirements</span></span>  

 <span data-ttu-id="853c5-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="853c5-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="853c5-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="853c5-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="853c5-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="853c5-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="853c5-127">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="853c5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853c5-128">참조</span><span class="sxs-lookup"><span data-stu-id="853c5-128">See also</span></span>

- [<span data-ttu-id="853c5-129">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="853c5-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
