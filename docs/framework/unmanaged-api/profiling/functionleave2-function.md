---
description: '자세히 알아보기: FunctionLeave2 함수'
title: FunctionLeave2 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: a9a97b84c70fd50044e8340b6f59fdbefe1d1a60
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760147"
---
# <a name="functionleave2-function"></a><span data-ttu-id="de5c0-103">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="de5c0-103">FunctionLeave2 Function</span></span>

<span data-ttu-id="de5c0-104">함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-104">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de5c0-105">구문</span><span class="sxs-lookup"><span data-stu-id="de5c0-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de5c0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de5c0-106">Parameters</span></span>

<span data-ttu-id="de5c0-107">`funcId` 진행 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-107">`funcId` [in] The identifier of the function that is returning.</span></span>

<span data-ttu-id="de5c0-108">`clientData` 진행 이전에 [Functionidmapper](functionidmapper-function.md) 함수를 통해 지정한 프로파일러에서 다시 매핑된 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-108">`clientData` [in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

<span data-ttu-id="de5c0-109">`func` 진행 `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-109">`func` [in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

<span data-ttu-id="de5c0-110">프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
<span data-ttu-id="de5c0-111">`retvalRange` 진행 함수 반환 값의 메모리 위치를 지정 하는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-111">`retvalRange` [in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

<span data-ttu-id="de5c0-112">반환 값 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-112">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="de5c0-113">프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="de5c0-114">설명</span><span class="sxs-lookup"><span data-stu-id="de5c0-114">Remarks</span></span>  

 <span data-ttu-id="de5c0-115">`func` `retvalRange` `FunctionLeave2` 값이 변경 되거나 제거 될 수 있으므로 함수에서를 반환한 후에는 및 매개 변수의 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-115">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="de5c0-116">`FunctionLeave2`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-116">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="de5c0-117">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="de5c0-118">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="de5c0-119">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="de5c0-120">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="de5c0-121">의 구현은 `FunctionLeave2` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-121">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="de5c0-122">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="de5c0-123">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionLeave2` .</span><span class="sxs-lookup"><span data-stu-id="de5c0-123">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="de5c0-124">또한 함수는 관리 `FunctionLeave2` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5c0-124">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de5c0-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de5c0-125">Requirements</span></span>  

 <span data-ttu-id="de5c0-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de5c0-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de5c0-127">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="de5c0-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="de5c0-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de5c0-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de5c0-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de5c0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5c0-130">참조</span><span class="sxs-lookup"><span data-stu-id="de5c0-130">See also</span></span>

- [<span data-ttu-id="de5c0-131">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="de5c0-131">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="de5c0-132">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="de5c0-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="de5c0-133">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="de5c0-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="de5c0-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="de5c0-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
