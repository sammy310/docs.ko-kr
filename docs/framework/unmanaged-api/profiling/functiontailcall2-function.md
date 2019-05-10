---
title: FunctionTailcall2 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e10b1a77586a09f8f5f7a59e811953fbede8773
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586890"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="b6609-102">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="b6609-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="b6609-103">현재 실행 중인 함수를 다른 함수에 대 한 마무리 호출이 수행 하려고 하는 스택 프레임에 대 한 정보를 제공 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6609-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6609-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6609-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6609-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="b6609-106">[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="b6609-107">[in] 프로파일러를 통해 이전에 지정 하는 매핑된 함수 식별자 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)를 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="b6609-108">[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="b6609-109">프로파일러에 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이 처리 해야 합니다 [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b6609-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6609-110">설명</span><span class="sxs-lookup"><span data-stu-id="b6609-110">Remarks</span></span>  
 <span data-ttu-id="b6609-111">마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하 고 마무리 호출을 수행한 함수 호출자에 게 직접 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="b6609-112">즉, 한 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 마무리 호출의 대상이 되는 함수에 대 한 콜백 발행 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="b6609-113">값을 `func` 후 매개 변수가 올바르지 않습니다는 `FunctionTailcall2` 함수 반환 값이 변경 될 수 있습니다 되거나 제거 되어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="b6609-114">`FunctionTailcall2` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="b6609-115">구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b6609-116">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b6609-117">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b6609-118">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b6609-119">구현의 `FunctionTailcall2` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b6609-120">구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b6609-121">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall2` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="b6609-122">또한는 `FunctionTailcall2` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6609-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6609-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6609-123">Requirements</span></span>  
 <span data-ttu-id="b6609-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6609-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6609-125">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b6609-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b6609-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6609-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6609-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6609-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6609-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6609-128">See also</span></span>

- [<span data-ttu-id="b6609-129">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="b6609-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="b6609-130">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="b6609-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="b6609-131">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="b6609-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="b6609-132">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b6609-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
