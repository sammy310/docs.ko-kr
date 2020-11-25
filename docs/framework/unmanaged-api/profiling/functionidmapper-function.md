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
ms.openlocfilehash: 17396d3038578c16b74c3717174dc0fa4dc17631
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722845"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="891a5-102">FunctionIDMapper 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-102">FunctionIDMapper Function</span></span>

<span data-ttu-id="891a5-103">함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="891a5-104">`FunctionIDMapper`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="891a5-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="891a5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="891a5-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="891a5-107">\[in] 다시 매핑할 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="891a5-108">\[out], 및 콜백을 받으려는 경우 프로파일러가 설정 하는 값에 대 한 포인터이 고, `true` `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` 그렇지 않으면이 값을로 설정 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="891a5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="891a5-109">Return Value</span></span>  

 <span data-ttu-id="891a5-110">프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="891a5-111">`false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="891a5-112">그렇지 않으면 null 반환 값이 프로세스 중지를 포함 하 여 예기치 않은 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="891a5-113">설명</span><span class="sxs-lookup"><span data-stu-id="891a5-113">Remarks</span></span>  

 <span data-ttu-id="891a5-114">`FunctionIDMapper`함수는 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="891a5-115">프로파일러는 프로파일러에 더 유용한 다른 식별자로 함수 ID를 다시 매핑하기 위해 프로파일러에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="891a5-116">는 `FunctionIDMapper` 지정 된 함수에 사용할 대체 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="891a5-117">그러면 실행 엔진이 기존 함수 ID 외에 `clientData` `FunctionEnter2` 도, 및 후크에 매개 변수의 프로파일러를 다시 전달 하 여 후크를 호출 하는 `FunctionLeave2` 함수를 식별 하는 방식으로 프로파일러 요청을 `FunctionTailcall2` 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="891a5-118">[ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) 메서드를 사용 하 여 함수의 구현을 지정할 수 있습니다 `FunctionIDMapper` .</span><span class="sxs-lookup"><span data-stu-id="891a5-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="891a5-119">`ICorProfilerInfo::SetFunctionIDMapper`메서드를 한 번만 호출할 수 있으며, [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="891a5-120">기본적으로 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 사용 하 여 COR_PRF_MONITOR_ENTERLEAVE 플래그를 설정 하 고 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 통해 후크를 설정 하는 프로파일러는 `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` 모든 함수에 대해, 및 콜백을 받아야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="891a5-121">그러나 프로파일러는 `FunctionIDMapper` 를로 설정 하 여 특정 함수에 대해 이러한 콜백을 수신 하지 않도록 선택적으로 구현할 수 있습니다 `pbHookFunction` `false` .</span><span class="sxs-lookup"><span data-stu-id="891a5-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="891a5-122">프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동일한 메서드/함수를 동시에 호출 하는 경우를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="891a5-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="891a5-123">이러한 경우 프로파일러는 `FunctionIDMapper` 동일한에 대해 여러 콜백을 수신할 수 있습니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="891a5-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="891a5-124">프로파일러에서는 동일한 값을 사용 하 여 여러 번 호출 될 때이 콜백에서 동일한 값을 반환 해야 합니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="891a5-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891a5-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="891a5-125">Requirements</span></span>  

 <span data-ttu-id="891a5-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="891a5-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="891a5-127">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="891a5-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="891a5-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="891a5-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="891a5-129">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891a5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891a5-130">참조</span><span class="sxs-lookup"><span data-stu-id="891a5-130">See also</span></span>

- [<span data-ttu-id="891a5-131">SetFunctionIDMapper 메서드</span><span class="sxs-lookup"><span data-stu-id="891a5-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="891a5-132">FunctionIDMapper2 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="891a5-133">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="891a5-134">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="891a5-135">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="891a5-136">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="891a5-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
