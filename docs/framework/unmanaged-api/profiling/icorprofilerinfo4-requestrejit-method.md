---
title: ICorProfilerInfo4::RequestReJIT 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: eb4d5e1c4efd67914df95868b67ec5cc3fe6139a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444824"
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="59fa8-102">ICorProfilerInfo4::RequestReJIT 메서드</span><span class="sxs-lookup"><span data-stu-id="59fa8-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="59fa8-103">지정된 함수의 모든 인스턴스에 대한 JIT 다시 컴파일을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59fa8-104">구문</span><span class="sxs-lookup"><span data-stu-id="59fa8-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59fa8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59fa8-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="59fa8-106">[in] 다시 컴파일할 함수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="59fa8-107">[in] 다시 컴파일할 함수를 식별하는 (`moduleId`, `module`) 쌍의 `methodDef` 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="59fa8-108">[in] 다시 컴파일할 함수를 식별하는 (`methodId`, `module`) 쌍의 `methodDef` 부분을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59fa8-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="59fa8-109">Return Value</span></span>  
 <span data-ttu-id="59fa8-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="59fa8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59fa8-111">HRESULT</span></span>|<span data-ttu-id="59fa8-112">설명</span><span class="sxs-lookup"><span data-stu-id="59fa8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59fa8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="59fa8-113">S_OK</span></span>|<span data-ttu-id="59fa8-114">JIT 다시 컴파일을 위해 모든 메서드에 표시하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="59fa8-115">프로파일러는 [ICorProfilerCallback4:: ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) 메서드를 구현 하 여 JIT 다시 컴파일을 위해 성공적으로 표시 된 메서드를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="59fa8-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="59fa8-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="59fa8-117">이 호출이 지원 되려면 프로파일러가 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-117">The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="59fa8-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="59fa8-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="59fa8-119">JIT 다시 컴파일이 사용하도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="59fa8-120">[ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 `COR_PRF_ENABLE_REJIT` 플래그를 설정 하 여 초기화 하는 동안 JIT 재컴파일을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="59fa8-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="59fa8-121">E_INVALIDARG</span></span>|<span data-ttu-id="59fa8-122">`cFunctions` 0 이거나 `moduleIds` 또는 `methodIds` `NULL`입니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="59fa8-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="59fa8-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="59fa8-124">메모리 부족 때문에 CLR에서 요청을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59fa8-125">주의</span><span class="sxs-lookup"><span data-stu-id="59fa8-125">Remarks</span></span>  
 <span data-ttu-id="59fa8-126">`RequestReJIT`를 호출하여 런타임에서 지정된 함수 집합을 다시 컴파일하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="59fa8-127">그런 다음 코드 프로파일러는 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 인터페이스를 사용 하 여 함수가 다시 컴파일될 때 생성 되는 코드를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-127">A code profiler can then use the [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="59fa8-128">이 기능은 현재 실행 중인 함수에는 영향을 주지 않고 이후 함수 호출에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="59fa8-129">지정된 함수가 이전에 JIT 다시 컴파일된 경우 다시 컴파일 요청은 함수를 되돌리고 다시 컴파일하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="59fa8-130">되돌리는 기능을 유지하기 위해 JIT 컴파일러는 함수의 원래 버전은 컴파일할 때 인라인 처리 결정을 위해 호출 수신자의 원래 버전만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="59fa8-131">JIT 컴파일러는 함수를 다시 컴파일할 때 인라인 처리를 위해 호출 수신자의 현재 버전(다시 컴파일된 버전 또는 원래 버전)을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="59fa8-132">프로파일러는 일반적으로 프로파일러가 하나 이상의 메서드를 계측하도록 요청하는 사용자 입력에 대한 응답으로 `RequestReJIT`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="59fa8-133">`RequestReJIT`는 일반적으로 작업의 일부를 수행 하기 위해 런타임을 일시 중단 하며, 잠재적으로 가비지 수집을 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="59fa8-134">따라서 프로파일러는 현재 프로파일러 콜백을 실행 중인 CLR에서 만든 스레드가 아니라 이전에 만든 스레드에서 `RequestReJIT`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59fa8-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59fa8-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59fa8-135">Requirements</span></span>  
 <span data-ttu-id="59fa8-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59fa8-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59fa8-137">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59fa8-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59fa8-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59fa8-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59fa8-139">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59fa8-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fa8-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59fa8-140">See also</span></span>

- [<span data-ttu-id="59fa8-141">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59fa8-141">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="59fa8-142">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59fa8-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="59fa8-143">프로파일링</span><span class="sxs-lookup"><span data-stu-id="59fa8-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
