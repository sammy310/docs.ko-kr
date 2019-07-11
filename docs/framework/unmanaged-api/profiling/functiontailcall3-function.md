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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aec2304e00d5328fcf55adbf5521c08865c05c56
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763295"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="b857f-102">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="b857f-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="b857f-103">현재 실행 중인 함수에 대 한 다른 함수에 대 한 마무리 호출이 수행 하는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b857f-104">구문</span><span class="sxs-lookup"><span data-stu-id="b857f-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b857f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b857f-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="b857f-106">[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b857f-107">설명</span><span class="sxs-lookup"><span data-stu-id="b857f-107">Remarks</span></span>  
 <span data-ttu-id="b857f-108">`FunctionTailcall3` 함수를 호출 하는 콜백 함수가 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="b857f-109">사용 하 여는 [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 구현의이 함수를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="b857f-110">`FunctionTailcall3` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="b857f-111">구현을 사용 해야 합니다는 `__declspec(naked)` 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="b857f-112">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b857f-113">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b857f-114">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b857f-115">구현의 `FunctionTailcall3` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="b857f-116">구현을 스택 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b857f-117">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall3` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="b857f-118">`FunctionTailcall3` 함수 관리 코드를 호출 하거나 어떤 방식으로 관리 되는 메모리를 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b857f-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b857f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b857f-119">Requirements</span></span>  
 <span data-ttu-id="b857f-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b857f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b857f-121">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b857f-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b857f-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b857f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b857f-123">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b857f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b857f-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="b857f-124">See also</span></span>

- [<span data-ttu-id="b857f-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="b857f-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="b857f-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="b857f-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="b857f-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b857f-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="b857f-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b857f-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="b857f-129">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="b857f-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b857f-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="b857f-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="b857f-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b857f-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="b857f-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="b857f-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="b857f-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="b857f-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="b857f-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b857f-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
