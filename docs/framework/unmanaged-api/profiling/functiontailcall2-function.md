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
ms.openlocfilehash: db3c3d38e0200f9849c84d7605a436816d56b813
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427431"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="da536-102">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="da536-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="da536-103">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da536-104">구문</span><span class="sxs-lookup"><span data-stu-id="da536-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da536-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da536-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="da536-106">진행 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da536-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="da536-107">진행 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 함수에 대해 이전에 [Functionidmapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)를 통해 지정한 다시 매핑된 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da536-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="da536-108">진행 스택 프레임에 대 한 정보를 가리키는 `COR_PRF_FRAME_INFO` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="da536-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="da536-109">프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da536-110">주의</span><span class="sxs-lookup"><span data-stu-id="da536-110">Remarks</span></span>  
 <span data-ttu-id="da536-111">마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하며, 마무리 호출을 수행한 함수의 호출자에 게 직접 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da536-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="da536-112">즉, 마무리 호출의 대상인 함수에 대해 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 콜백이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da536-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="da536-113">값이 변경 되거나 제거 될 수 있으므로 `FunctionTailcall2` 함수가 반환 된 후에는 `func` 매개 변수의 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da536-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="da536-114">`FunctionTailcall2` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="da536-115">구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="da536-116">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da536-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="da536-117">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="da536-118">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="da536-119">`FunctionTailcall2` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da536-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="da536-120">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da536-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="da536-121">가비지 수집을 시도 하면 `FunctionTailcall2` 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da536-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="da536-122">또한 `FunctionTailcall2` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da536-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da536-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da536-123">Requirements</span></span>  
 <span data-ttu-id="da536-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da536-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da536-125">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="da536-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="da536-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da536-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da536-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da536-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da536-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da536-128">See also</span></span>

- [<span data-ttu-id="da536-129">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="da536-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="da536-130">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="da536-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="da536-131">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="da536-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="da536-132">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="da536-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
