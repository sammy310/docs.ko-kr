---
title: FunctionLeave3 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 456d9a0e8236948ac69ed069495b1999ebf7e80a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500613"
---
# <a name="functionleave3-function"></a><span data-ttu-id="96081-102">FunctionLeave3 함수</span><span class="sxs-lookup"><span data-stu-id="96081-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="96081-103">컨트롤이 함수에서 반환 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96081-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96081-104">구문</span><span class="sxs-lookup"><span data-stu-id="96081-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96081-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="96081-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="96081-106">\[in] 컨트롤이 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="96081-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="96081-107">설명</span><span class="sxs-lookup"><span data-stu-id="96081-107">Remarks</span></span>  
 <span data-ttu-id="96081-108">`FunctionLeave3`콜백 함수는 함수가 호출 될 때 프로파일러에 알립니다. 그러나 반환 값 검사는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96081-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="96081-109">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 를 사용 하 여이 함수의 구현을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="96081-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="96081-110">`FunctionLeave3`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96081-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="96081-111">구현에서는 저장소 클래스 특성을 사용 해야 합니다 `__declspec(naked)` .</span><span class="sxs-lookup"><span data-stu-id="96081-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="96081-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96081-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="96081-113">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96081-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="96081-114">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96081-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="96081-115">의 구현은 `FunctionLeave3` 가비지 수집을 지연 하므로를 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96081-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="96081-116">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96081-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="96081-117">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionLeave3` .</span><span class="sxs-lookup"><span data-stu-id="96081-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="96081-118">`FunctionLeave3`함수는 관리 코드를 호출 하거나 다른 방식으로 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96081-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96081-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96081-119">Requirements</span></span>  
 <span data-ttu-id="96081-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96081-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96081-121">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="96081-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="96081-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96081-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96081-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96081-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96081-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96081-124">See also</span></span>

- [<span data-ttu-id="96081-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="96081-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="96081-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="96081-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="96081-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="96081-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="96081-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="96081-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="96081-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="96081-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="96081-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="96081-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="96081-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="96081-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="96081-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="96081-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="96081-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="96081-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="96081-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="96081-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
