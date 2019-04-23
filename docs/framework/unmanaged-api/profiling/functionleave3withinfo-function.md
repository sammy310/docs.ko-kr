---
title: FunctionLeave3WithInfo 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4304c933b9802ef565b8d18f1e04591e7fa83cb8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189929"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="8514f-102">FunctionLeave3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="8514f-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="8514f-103">컨트롤은 함수에서 반환 되는 프로파일러에 알립니다. 및 전달할 수 있는 핸들을 제공 합니다 [ICorProfilerInfo3::GetFunctionLeave3Info 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 스택 프레임 및 반환 값을 검색할 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8514f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8514f-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8514f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8514f-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="8514f-106">[in] 컨트롤이 반환 된 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="8514f-107">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="8514f-108">이 핸들이 전달 된 콜백 하는 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8514f-109">설명</span><span class="sxs-lookup"><span data-stu-id="8514f-109">Remarks</span></span>  
 <span data-ttu-id="8514f-110">합니다 `FunctionLeave3WithInfo` 콜백 메서드를 사용 하 여 프로파일러가 호출 함수 처럼 프로파일러에 알립니다 합니다 [ICorProfilerInfo3::GetFunctionLeave3Info 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 반환 값을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="8514f-111">반환 값 정보에 액세스할 수는 `COR_PRF_ENABLE_FUNCTION_RETVAL` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="8514f-112">프로파일러를 사용할 수는 [icorprofilerinfo:: Seteventmask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 사용 하 여 합니다 [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 등록 프로그램 이 함수의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="8514f-113">`FunctionLeave3WithInfo` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="8514f-114">구현을 사용 해야 합니다는 `__declspec(naked)` 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="8514f-115">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="8514f-116">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="8514f-117">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8514f-118">구현의 `FunctionLeave3WithInfo` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="8514f-119">구현을 스택 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8514f-120">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionLeave3WithInfo` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="8514f-121">`FunctionLeave3WithInfo` 함수 관리 코드를 호출 하거나 어떤 방식으로 관리 되는 메모리를 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8514f-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8514f-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8514f-122">Requirements</span></span>  
 <span data-ttu-id="8514f-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8514f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8514f-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8514f-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8514f-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8514f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8514f-126">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8514f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8514f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="8514f-127">See also</span></span>

- [<span data-ttu-id="8514f-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="8514f-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="8514f-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="8514f-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="8514f-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="8514f-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="8514f-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="8514f-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="8514f-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8514f-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="8514f-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8514f-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="8514f-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="8514f-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="8514f-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8514f-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="8514f-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="8514f-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8514f-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="8514f-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="8514f-138">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8514f-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
