---
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
ms.openlocfilehash: e40687f7f843dc563801bb01b503d2ae94a094fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446022"
---
# <a name="functionleave2-function"></a><span data-ttu-id="da2fb-102">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="da2fb-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="da2fb-103">함수가 호출자에 게 반환 될 것을 프로파일러에 알리고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="da2fb-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da2fb-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="da2fb-106">진행 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="da2fb-107">진행 이전에 [Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 함수를 통해 지정한 프로파일러에서 다시 매핑된 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="da2fb-108">진행 스택 프레임에 대 한 정보를 가리키는 `COR_PRF_FRAME_INFO` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="da2fb-109">프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="da2fb-110">진행 함수 반환 값의 메모리 위치를 지정 하는 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="da2fb-111">반환 값 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="da2fb-112">프로파일러는 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da2fb-113">설명</span><span class="sxs-lookup"><span data-stu-id="da2fb-113">Remarks</span></span>  
 <span data-ttu-id="da2fb-114">값이 변경 되거나 제거 될 수 있으므로 `FunctionLeave2` 함수가 반환 된 후에는 `func` 및 `retvalRange` 매개 변수의 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="da2fb-115">`FunctionLeave2` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="da2fb-116">구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="da2fb-117">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="da2fb-118">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="da2fb-119">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="da2fb-120">`FunctionLeave2` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="da2fb-121">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="da2fb-122">가비지 수집을 시도 하면 `FunctionLeave2` 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="da2fb-123">또한 `FunctionLeave2` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da2fb-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2fb-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da2fb-124">Requirements</span></span>  
 <span data-ttu-id="da2fb-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da2fb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2fb-126">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="da2fb-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="da2fb-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da2fb-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da2fb-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2fb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2fb-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="da2fb-129">See also</span></span>

- [<span data-ttu-id="da2fb-130">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="da2fb-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="da2fb-131">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="da2fb-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="da2fb-132">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="da2fb-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="da2fb-133">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="da2fb-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
