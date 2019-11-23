---
title: FunctionTailcall3WithInfo 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: 202aed64de78675c79f998afb4483e0d19b811de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445964"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="6b604-102">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="6b604-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="6b604-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span><span class="sxs-lookup"><span data-stu-id="6b604-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b604-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b604-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b604-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b604-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="6b604-106">[in] The identifier of the currently executing function that is about to make a tail call.</span><span class="sxs-lookup"><span data-stu-id="6b604-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="6b604-107">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6b604-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6b604-108">This handle is valid only during the callback to which it is passed.</span><span class="sxs-lookup"><span data-stu-id="6b604-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b604-109">주의</span><span class="sxs-lookup"><span data-stu-id="6b604-109">Remarks</span></span>  
 <span data-ttu-id="6b604-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span><span class="sxs-lookup"><span data-stu-id="6b604-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="6b604-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span><span class="sxs-lookup"><span data-stu-id="6b604-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="6b604-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span><span class="sxs-lookup"><span data-stu-id="6b604-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6b604-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="6b604-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="6b604-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="6b604-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="6b604-115">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="6b604-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6b604-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="6b604-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6b604-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="6b604-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6b604-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6b604-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="6b604-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="6b604-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6b604-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span><span class="sxs-lookup"><span data-stu-id="6b604-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="6b604-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span><span class="sxs-lookup"><span data-stu-id="6b604-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b604-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b604-122">Requirements</span></span>  
 <span data-ttu-id="6b604-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b604-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b604-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6b604-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6b604-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b604-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b604-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b604-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b604-127">참조</span><span class="sxs-lookup"><span data-stu-id="6b604-127">See also</span></span>

- [<span data-ttu-id="6b604-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6b604-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="6b604-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6b604-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="6b604-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="6b604-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="6b604-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6b604-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="6b604-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6b604-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="6b604-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="6b604-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="6b604-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6b604-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="6b604-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="6b604-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="6b604-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="6b604-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="6b604-137">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6b604-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
