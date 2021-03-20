---
description: '자세히 알아보기: FunctionTailcall2 함수'
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
ms.openlocfilehash: e06c3bde7ad0700de3d7f08b33159032b31eae8a
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760069"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="2d855-103">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="2d855-103">FunctionTailcall2 Function</span></span>

<span data-ttu-id="2d855-104">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알리고 스택 프레임에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-104">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d855-105">구문</span><span class="sxs-lookup"><span data-stu-id="2d855-105">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d855-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d855-106">Parameters</span></span>

<span data-ttu-id="2d855-107">`funcId` 진행 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-107">`funcId` [in] The identifier of the currently executing function that is about to make a tail call.</span></span>

<span data-ttu-id="2d855-108">`clientData` 진행 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 함수에 대해 이전에 [Functionidmapper](functionidmapper-function.md)를 통해 지정한 다시 매핑된 함수 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-108">`clientData` [in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
<span data-ttu-id="2d855-109">`func` 진행 `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-109">`func` [in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

<span data-ttu-id="2d855-110">프로파일러는 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드에서 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로이를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d855-111">설명</span><span class="sxs-lookup"><span data-stu-id="2d855-111">Remarks</span></span>  

 <span data-ttu-id="2d855-112">마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하며, 마무리 호출을 수행한 함수의 호출자에 게 직접 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-112">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="2d855-113">즉, 마무리 호출의 대상인 함수에 대해 [FunctionLeave2](functionleave2-function.md) 콜백이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-113">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="2d855-114">`func` `FunctionTailcall2` 값이 변경 되거나 제거 될 수 있으므로 함수가 반환 된 후에는 매개 변수 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-114">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="2d855-115">`FunctionTailcall2`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-115">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="2d855-116">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="2d855-117">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="2d855-118">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="2d855-119">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="2d855-120">의 구현은 `FunctionTailcall2` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-120">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="2d855-121">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="2d855-122">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionTailcall2` .</span><span class="sxs-lookup"><span data-stu-id="2d855-122">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="2d855-123">또한 함수는 관리 `FunctionTailcall2` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d855-123">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d855-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d855-124">Requirements</span></span>  

 <span data-ttu-id="2d855-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2d855-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d855-126">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="2d855-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2d855-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d855-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d855-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d855-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d855-129">참조</span><span class="sxs-lookup"><span data-stu-id="2d855-129">See also</span></span>

- [<span data-ttu-id="2d855-130">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="2d855-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="2d855-131">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="2d855-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="2d855-132">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="2d855-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="2d855-133">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="2d855-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
