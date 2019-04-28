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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3efee2e2b595f1e0d9116dcac3fdaa99aa4659d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598898"
---
# <a name="functionleave2-function"></a><span data-ttu-id="0ec1a-102">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="0ec1a-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="0ec1a-103">함수에 대 한 호출자에 게 반환 하는 것을 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ec1a-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ec1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ec1a-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="0ec1a-106">[in] 식별자를 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="0ec1a-107">[in] 프로파일러를 통해 이전에 지정 하는 매핑된 함수 식별자를 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="0ec1a-108">[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="0ec1a-109">프로파일러에 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이 처리 해야 합니다 [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="0ec1a-110">[in] 에 대 한 포인터를 [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) 함수의 반환 값의 메모리 위치를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="0ec1a-111">반환 값 정보에 액세스 하기 위해는 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="0ec1a-112">프로파일러를 사용 하 여 수를 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 설정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ec1a-113">설명</span><span class="sxs-lookup"><span data-stu-id="0ec1a-113">Remarks</span></span>  
 <span data-ttu-id="0ec1a-114">값을 `func` 및 `retvalRange` 매개 변수가 후 올바르면는 `FunctionLeave2` 함수 반환 값이 변경 될 수 있습니다 또는 제거 하기 때문에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="0ec1a-115">`FunctionLeave2` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="0ec1a-116">구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="0ec1a-117">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="0ec1a-118">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="0ec1a-119">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0ec1a-120">구현의 `FunctionLeave2` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="0ec1a-121">구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0ec1a-122">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionLeave2` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="0ec1a-123">또한는 `FunctionLeave2` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec1a-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ec1a-124">Requirements</span></span>  
 <span data-ttu-id="0ec1a-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ec1a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec1a-126">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0ec1a-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0ec1a-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ec1a-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ec1a-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec1a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec1a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ec1a-129">See also</span></span>

- [<span data-ttu-id="0ec1a-130">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="0ec1a-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="0ec1a-131">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="0ec1a-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="0ec1a-132">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="0ec1a-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="0ec1a-133">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="0ec1a-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
