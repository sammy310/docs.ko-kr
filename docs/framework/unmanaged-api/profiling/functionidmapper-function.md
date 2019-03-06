---
title: FunctionIDMapper 함수
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0320c831648c15dfec42c1b693be2f13e6888ae9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475166"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="e62f0-102">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="e62f0-103">함수는 지정 된 식별자에 사용할 대체 ID를 다시 매핑할 수는 프로파일러에 알립니다. 합니다 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)를 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), 및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 함수에 대 한 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="e62f0-104">`FunctionIDMapper`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62f0-105">구문</span><span class="sxs-lookup"><span data-stu-id="e62f0-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e62f0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e62f0-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="e62f0-107">[in] 다시 매핑할 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="e62f0-108">[out] 프로파일러를 설정 하는 값에 대 한 포인터 `true` 수신 하려는 경우 `FunctionEnter2`를 `FunctionLeave2`, 및 `FunctionTailcall2` 콜백을;이 값을 설정 하는 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e62f0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e62f0-109">Return Value</span></span>  
 <span data-ttu-id="e62f0-110">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="e62f0-111">
  `false`가 `pbHookFunction\`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="e62f0-112">이 고, 그렇지 null 반환 값에는 프로세스 중지를 포함 한 예기치 않은 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e62f0-113">설명</span><span class="sxs-lookup"><span data-stu-id="e62f0-113">Remarks</span></span>  
 <span data-ttu-id="e62f0-114">`FunctionIDMapper` 는 콜백 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="e62f0-115">프로파일러에 대 한 더 유용한 다른 식별자 함수 ID를 매핑할 프로파일러에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="e62f0-116">`FunctionIDMapper` 지정된 된 함수에 사용할 대체 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="e62f0-117">다음 실행 엔진에서 프로파일러를 다시 기존 함수 ID 외에도이 대체 ID를 전달 하 여 프로파일러 요청을 적용 합니다 `clientData` 의 매개 변수를 `FunctionEnter2`를 `FunctionLeave2`, 및 `FunctionTailcall2` 후크를 식별 하 후크 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="e62f0-118">사용할 수는 [icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) 의 구현을 지정 하는 방법의 `FunctionIDMapper` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="e62f0-119">호출할 수 있습니다 합니다 `ICorProfilerInfo::SetFunctionIDMapper` 에서 수행 하는 한 번만 메서드를 권장 합니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="e62f0-120">기본적으로 가정는 프로파일러는 COR_PRF_MONITOR_ENTERLEAVE 플래그를 사용 하 여 설정 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)를 통해 후크를 설정 하 고 [icorprofilerinfo:: Setenterleavefunctionhooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 받아야 합니다 `FunctionEnter2`를 `FunctionLeave2`, 및 `FunctionTailcall2` 모든 함수에 대 한 콜백을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="e62f0-121">그러나 프로파일러 구현할 수 있습니다 `FunctionIDMapper` 선택적으로 특정 이러한 콜백을 수신 하지 않도록 설정 하 여 함수 `pbHookFunction` 에 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="e62f0-122">프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동시에 동일한 메서드/함수를 호출 하는 경우 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="e62f0-123">이러한 경우 프로파일러 여러 나타날 `FunctionIDMapper` 동일에 대 한 콜백을 `FunctionID`합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="e62f0-124">프로파일러 해야 동일한 여러 번 호출 될 때이 콜백에서 동일한 값을 반환 하려면 특정 `FunctionID`합니다.</span><span class="sxs-lookup"><span data-stu-id="e62f0-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e62f0-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e62f0-125">Requirements</span></span>  
 <span data-ttu-id="e62f0-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e62f0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62f0-127">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e62f0-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e62f0-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e62f0-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e62f0-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e62f0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62f0-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="e62f0-130">See also</span></span>
- [<span data-ttu-id="e62f0-131">SetFunctionIDMapper 메서드</span><span class="sxs-lookup"><span data-stu-id="e62f0-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e62f0-132">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [<span data-ttu-id="e62f0-133">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="e62f0-134">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="e62f0-135">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="e62f0-136">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e62f0-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
