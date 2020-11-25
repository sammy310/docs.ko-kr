---
title: FunctionTailcall3 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
ms.openlocfilehash: dfe1a530ea009300e7cfbf002053d2e2b6034845
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719283"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="7f571-102">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="7f571-102">FunctionTailcall3 Function</span></span>

<span data-ttu-id="7f571-103">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f571-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f571-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f571-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f571-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="7f571-106">\[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f571-107">설명</span><span class="sxs-lookup"><span data-stu-id="7f571-107">Remarks</span></span>  

 <span data-ttu-id="7f571-108">`FunctionTailcall3`콜백 함수는 함수가 호출 될 때 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="7f571-109">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 를 사용 하 여이 함수의 구현을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="7f571-110">`FunctionTailcall3`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="7f571-111">구현에서는 저장소 클래스 특성을 사용 해야 합니다 `__declspec(naked)` .</span><span class="sxs-lookup"><span data-stu-id="7f571-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="7f571-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="7f571-113">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="7f571-114">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7f571-115">의 구현은 `FunctionTailcall3` 가비지 수집을 지연 하므로를 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="7f571-116">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7f571-117">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionTailcall3` .</span><span class="sxs-lookup"><span data-stu-id="7f571-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="7f571-118">`FunctionTailcall3`함수는 관리 코드를 호출 하거나 다른 방식으로 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f571-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f571-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f571-119">Requirements</span></span>  

 <span data-ttu-id="7f571-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f571-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f571-121">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="7f571-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7f571-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f571-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f571-123">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f571-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f571-124">참조</span><span class="sxs-lookup"><span data-stu-id="7f571-124">See also</span></span>

- [<span data-ttu-id="7f571-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="7f571-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="7f571-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="7f571-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="7f571-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7f571-127">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="7f571-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7f571-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="7f571-129">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="7f571-129">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="7f571-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="7f571-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="7f571-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="7f571-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="7f571-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="7f571-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="7f571-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="7f571-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="7f571-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7f571-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
