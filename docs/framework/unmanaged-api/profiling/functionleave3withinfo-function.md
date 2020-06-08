---
title: FunctionLeave3WithInfo 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
ms.openlocfilehash: 235bae64fe5e6a534f2a650050c6c9ad4aa8fe84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500626"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="f7514-102">FunctionLeave3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="f7514-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="f7514-103">는 컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알리고 [ICorProfilerInfo3:: GetFunctionLeave3Info 메서드에](icorprofilerinfo3-getfunctionleave3info-method.md) 전달 하 여 스택 프레임 및 반환 값을 검색 하는 핸들을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7514-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7514-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7514-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7514-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="f7514-106">\[in] 컨트롤이 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-106">\[in] The identifier of the function from which control is returned.</span></span>

- `eltInfo`

  <span data-ttu-id="f7514-107">\[in] 지정 된 스택 프레임에 대 한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="f7514-108">이 핸들은 전달 되는 콜백 중에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7514-109">설명</span><span class="sxs-lookup"><span data-stu-id="f7514-109">Remarks</span></span>  
 <span data-ttu-id="f7514-110">`FunctionLeave3WithInfo`콜백 메서드는 함수가 호출 될 때 프로파일러에 게 알리고 [ICorProfilerInfo3:: GetFunctionLeave3Info 메서드](icorprofilerinfo3-getfunctionleave3info-method.md) 를 사용 하 여 반환 값을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="f7514-111">반환 값 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="f7514-112">프로파일러는 [ICorProfilerInfo:: SetEventMask 메서드](icorprofilerinfo-seteventmask-method.md) 를 사용 하 여 이벤트 플래그를 설정한 다음 [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo 메서드](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 를 사용 하 여이 함수의 구현을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f7514-113">`FunctionLeave3WithInfo`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="f7514-114">구현에서는 저장소 클래스 특성을 사용 해야 합니다 `__declspec(naked)` .</span><span class="sxs-lookup"><span data-stu-id="f7514-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="f7514-115">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="f7514-116">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="f7514-117">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f7514-118">의 구현은 `FunctionLeave3WithInfo` 가비지 수집을 지연 하므로를 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="f7514-119">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f7514-120">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionLeave3WithInfo` .</span><span class="sxs-lookup"><span data-stu-id="f7514-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="f7514-121">`FunctionLeave3WithInfo`함수는 관리 코드를 호출 하거나 다른 방식으로 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7514-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7514-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7514-122">Requirements</span></span>  
 <span data-ttu-id="f7514-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7514-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7514-124">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="f7514-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f7514-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7514-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7514-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7514-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7514-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7514-127">See also</span></span>

- [<span data-ttu-id="f7514-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="f7514-128">GetFunctionLeave3Info</span></span>](icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="f7514-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="f7514-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="f7514-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="f7514-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="f7514-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f7514-131">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="f7514-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f7514-132">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="f7514-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f7514-133">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f7514-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="f7514-134">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f7514-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f7514-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="f7514-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="f7514-136">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="f7514-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="f7514-137">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="f7514-138">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f7514-138">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
