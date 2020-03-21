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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175176"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="5f092-102">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="5f092-103">해당 함수에 대 한 [FunctionEnter2,](functionenter2-function.md) [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 함수의 지정된 식별자가 다시 매핑될 수 있음을 프로파일러에 보임합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="5f092-104">`FunctionIDMapper`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f092-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f092-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f092-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f092-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="5f092-107">\[in] 함수 식별자를 다시 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="5f092-108">\[out] 프로파일러가 `true` 수신할 경우 설정하는 값에 대한 `FunctionEnter2` `FunctionLeave2`포인터 `FunctionTailcall2` 및 콜백을 수신합니다. 그렇지 않으면 이 값을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5f092-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5f092-109">Return Value</span></span>  
 <span data-ttu-id="5f092-110">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="5f092-111">`false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="5f092-112">그렇지 않으면 null 반환 값은 프로세스를 중지하는 등 예기치 않은 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f092-113">설명</span><span class="sxs-lookup"><span data-stu-id="5f092-113">Remarks</span></span>  
 <span data-ttu-id="5f092-114">함수는 `FunctionIDMapper` 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="5f092-115">프로파일러에 더 유용한 다른 식별자로 함수 ID를 다시 매핑하기 위해 프로파일러에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="5f092-116">지정된 `FunctionIDMapper` 함수에 사용할 대체 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="5f092-117">그런 다음 실행 엔진은 기존 함수 ID 외에 이 대체 `clientData` ID를 `FunctionEnter2`의 매개 변수인 에 `FunctionLeave2`있는 프로파일러로 `FunctionTailcall2` 다시 전달하여 hook이 호출되는 함수를 식별하여 프로파일러의 요청을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="5f092-118">[ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) 메서드를 사용하여 `FunctionIDMapper` 함수의 구현을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="5f092-119">메서드를 `ICorProfilerInfo::SetFunctionIDMapper` 한 번만 호출할 수 있으며 [ICorProfilerCallback::초기화](icorprofilercallback-initialize-method.md) 콜백에서 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="5f092-120">기본적으로 [ICorProfilerInfo:SetEventMask를](icorprofilerinfo-seteventmask-method.md)사용하여 COR_PRF_MONITOR_ENTERLEAVE 플래그를 설정하고 ICorProfilerInfo를 통해 후크를 설정하는 프로파일러가 다음과 같은 [경우:SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2는](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)모든 함수에 대해 `FunctionEnter2`에서 , `FunctionLeave2`및 `FunctionTailcall2` 콜백을 수신해야 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="5f092-121">그러나 프로파일러는 을 `FunctionIDMapper` 설정하여 `pbHookFunction` 특정 함수에 대해 이러한 콜백을 `false`선택적으로 수신하지 않도록 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="5f092-122">프로파일러는 프로파일링된 응용 프로그램의 여러 스레드가 동일한 메서드/함수를 동시에 호출하는 경우를 관대해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="5f092-123">이러한 경우 프로파일러는 동일한 `FunctionIDMapper` `FunctionID`에 대해 여러 콜백을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="5f092-124">프로파일러는 동일한 을 사용하여 여러 번 호출될 때 이 콜백에서 `FunctionID`동일한 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f092-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f092-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f092-125">Requirements</span></span>  
 <span data-ttu-id="5f092-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f092-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f092-127">**헤더:** 코르프로프.아이들</span><span class="sxs-lookup"><span data-stu-id="5f092-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5f092-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f092-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f092-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f092-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f092-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f092-130">See also</span></span>

- [<span data-ttu-id="5f092-131">SetFunctionIDMapper 메서드</span><span class="sxs-lookup"><span data-stu-id="5f092-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="5f092-132">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="5f092-133">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="5f092-134">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="5f092-135">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="5f092-136">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5f092-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
