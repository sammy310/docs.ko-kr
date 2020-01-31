---
title: FunctionEnter2 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 6cd35c180b8a322b3402b050c6d6840073010b1f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866985"
---
# <a name="functionenter2-function"></a><span data-ttu-id="8f05b-102">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="8f05b-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="8f05b-103">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알리고 스택 프레임 및 함수 인수에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="8f05b-104">이 함수는 [Functionenter](functionenter-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f05b-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f05b-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f05b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f05b-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="8f05b-107">\[] 컨트롤을 전달할 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="8f05b-108">\[에서 이전에 [Functionidmapper](functionidmapper-function.md) 함수를 사용 하 여 지정한 프로파일러에서 다시 매핑된 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="8f05b-109">\[] 스택 프레임에 대 한 정보를 가리키는 `COR_PRF_FRAME_INFO` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="8f05b-110">프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="8f05b-111">\[in] 함수 인수의 메모리에서 위치를 지정 하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="8f05b-112">인수 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="8f05b-113">프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f05b-114">주의</span><span class="sxs-lookup"><span data-stu-id="8f05b-114">Remarks</span></span>  
 <span data-ttu-id="8f05b-115">값이 변경 되거나 제거 될 수 있으므로 `FunctionEnter2` 함수가 반환 된 후에는 `func` 및 `argumentInfo` 매개 변수의 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="8f05b-116">`FunctionEnter2` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="8f05b-117">구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="8f05b-118">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="8f05b-119">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="8f05b-120">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8f05b-121">`FunctionEnter2` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="8f05b-122">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8f05b-123">가비지 수집을 시도 하면 `FunctionEnter2` 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="8f05b-124">또한 `FunctionEnter2` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f05b-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f05b-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f05b-125">Requirements</span></span>  
 <span data-ttu-id="8f05b-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f05b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f05b-127">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="8f05b-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8f05b-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f05b-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f05b-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f05b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f05b-130">참조</span><span class="sxs-lookup"><span data-stu-id="8f05b-130">See also</span></span>

- [<span data-ttu-id="8f05b-131">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="8f05b-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="8f05b-132">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="8f05b-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="8f05b-133">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="8f05b-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="8f05b-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8f05b-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
