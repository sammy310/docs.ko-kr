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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177061"
---
# <a name="functionenter2-function"></a><span data-ttu-id="4b82a-102">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="4b82a-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="4b82a-103">컨트롤이 함수에 전달되고 있음을 프로파일러에 통보하고 스택 프레임 및 함수 인수에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="4b82a-104">이 함수는 [FunctionEnter](functionenter-function.md) 함수를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b82a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4b82a-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b82a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b82a-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="4b82a-107">\[in] 컨트롤이 전달되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="4b82a-108">\[in] 프로파일러가 [FunctionIDMapper](functionidmapper-function.md) 함수를 사용하여 이전에 지정한 리메드 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="4b82a-109">\[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="4b82a-110">프로파일러는 [이를 ICorProfilerInfo2:GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드의 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="4b82a-111">\[in] 함수 인수의 메모리에 있는 위치를 지정하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="4b82a-112">인수 정보에 액세스하려면 플래그를 `COR_PRF_ENABLE_FUNCTION_ARGS` 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="4b82a-113">프로파일러는 [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용하여 이벤트 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="4b82a-114">설명</span><span class="sxs-lookup"><span data-stu-id="4b82a-114">Remarks</span></span>  
 <span data-ttu-id="4b82a-115">`func` 값이 변경되거나 `argumentInfo` 소멸될 수 있으므로 `FunctionEnter2` 함수가 반환된 후에 및 매개 변수의 값이 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="4b82a-116">함수는 `FunctionEnter2` 콜백입니다. 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="4b82a-117">구현은 `__declspec`()`naked`저장소 클래스 특성을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="4b82a-118">실행 엔진은 이 함수를 호출하기 전에 레지스터를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="4b82a-119">입력시 부동 점 단위(FPU)를 포함하여 사용하는 모든 레지스터를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="4b82a-120">종료 시 호출자에 의해 푸시된 모든 매개 변수를 터뜨려 스택을 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="4b82a-121">가비지 `FunctionEnter2` 수집을 지연시킬 수 있으므로 구현이 차단되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="4b82a-122">스택이 가비지 콜렉션 친화적인 상태에 있지 않을 수 있으므로 구현은 가비지 수집을 시도해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="4b82a-123">가비지 수집을 시도하면 런타임이 `FunctionEnter2` 반환될 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="4b82a-124">또한 함수는 `FunctionEnter2` 관리 되는 코드에 호출 하거나 어떤 식으로든 관리되는 메모리 할당을 발생 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b82a-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b82a-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b82a-125">Requirements</span></span>  
 <span data-ttu-id="4b82a-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b82a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b82a-127">**헤더:** 코르프로프.아이들</span><span class="sxs-lookup"><span data-stu-id="4b82a-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4b82a-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b82a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b82a-129">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b82a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b82a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b82a-130">See also</span></span>

- [<span data-ttu-id="4b82a-131">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="4b82a-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="4b82a-132">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="4b82a-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="4b82a-133">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="4b82a-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="4b82a-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="4b82a-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
