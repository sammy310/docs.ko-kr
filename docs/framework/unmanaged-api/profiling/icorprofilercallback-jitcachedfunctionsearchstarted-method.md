---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4d35179b8ae35c03370cc3798609d6ed430cde3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782848"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="c1fc0-102">ICorProfilerCallback::JITCachedFunctionSearchStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="c1fc0-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="c1fc0-103">네이티브 이미지 생성기 (NGen.exe)를 사용 하 여 이전에 컴파일된 함수에 대 한 검색이 시작는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1fc0-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1fc0-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1fc0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1fc0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c1fc0-106">[in] 검색이 수행 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="c1fc0-107">[out] `true` (있는 경우) 실행 엔진에서 캐시 된 버전의 함수를 사용 해야 하는 경우이 고 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="c1fc0-108">값이 `false`, 실행 엔진에서는 JIT 컴파일된 되지 않은 버전을 사용 하는 대신 함수 JIT 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1fc0-109">설명</span><span class="sxs-lookup"><span data-stu-id="c1fc0-109">Remarks</span></span>  
 <span data-ttu-id="c1fc0-110">.NET Framework 버전 2.0에에서는 `JITCachedFunctionSearchStarted` 및 [icorprofilercallback:: Jitcachedfunctionsearchfinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) 콜백을 일반 NGen 이미지의 모든 함수에 대 한 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="c1fc0-111">만 NGen 이미지의 프로필에 대 한 액세스에 최적화 된 이미지의 모든 함수에 대 한 콜백을 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="c1fc0-112">그러나 추가 오버 헤드로 인해 프로파일러 요청 해야 프로파일러에 최적화 된 NGen 이미지를 컴파일된-just-in-time (JIT) 함수를 적용할 이러한 콜백을 사용 하려는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="c1fc0-113">그렇지 않은 경우 프로파일러 함수 정보를 수집 지연 전략을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="c1fc0-114">프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동시에 동일한 메서드를 호출 되는 경우 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="c1fc0-115">예를 들어 스레드는 호출 `JITCachedFunctionSearchStarted` 프로파일러를 설정 하 여 응답 *pbUseCachedFunction*JIT 컴파일을 FALSE로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="c1fc0-116">다음 호출 스레드가 [icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) 하 고 [icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="c1fc0-117">이제 B 호출 스레드 `JITCachedFunctionSearchStarted` 동일한 함수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="c1fc0-118">프로파일러는 profiler가 스레드 A의 호출에 응답 하기 전에 스레드 B 콜백을 보내므로 두 번째 콜백 수신 프로파일러는 JIT 컴파일되나요 함수를 언급 하는 경우에 `JITCachedFunctionSearchStarted`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="c1fc0-119">스레드 호출을 수행 하는 순서는 스레드의 예약 하는 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="c1fc0-120">프로파일러 중복 콜백을 받으면에서 참조 값을 설정 해야이 `pbUseCachedFunction` 모든 중복 콜백에 대 한 동일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="c1fc0-121">즉, `JITCachedFunctionSearchStarted` 동일한 여러 번 호출 `functionId` 값 프로파일러 응답 해야 동일한 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1fc0-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1fc0-122">Requirements</span></span>  
 <span data-ttu-id="c1fc0-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1fc0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1fc0-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1fc0-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1fc0-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1fc0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1fc0-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1fc0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fc0-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="c1fc0-127">See also</span></span>

- [<span data-ttu-id="c1fc0-128">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1fc0-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
