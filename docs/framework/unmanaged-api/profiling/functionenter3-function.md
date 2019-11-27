---
title: FunctionEnter3 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter3
helpviewer_keywords:
- FunctionEnter3 function [.NET Framework profiling]
ms.assetid: ef782c53-dae7-4990-b4ad-fddb1e690d4e
topic_type:
- apiref
ms.openlocfilehash: fd224279b3df6c9e8e55cd81ebfbf2e5ea2428d5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440783"
---
# <a name="functionenter3-function"></a><span data-ttu-id="759c0-102">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="759c0-102">FunctionEnter3 Function</span></span>
<span data-ttu-id="759c0-103">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="759c0-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="759c0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="759c0-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="759c0-106">진행 제어가 전달 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-106">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="759c0-107">설명</span><span class="sxs-lookup"><span data-stu-id="759c0-107">Remarks</span></span>  
 <span data-ttu-id="759c0-108">`FunctionEnter3` 콜백 함수는 함수가 호출 될 때 프로파일러에 알립니다. 하지만 인수 검사는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-108">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="759c0-109">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 를 사용 하 여이 함수의 구현을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="759c0-110">`FunctionEnter3` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-110">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="759c0-111">구현에서 `__declspec(naked)` 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="759c0-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="759c0-113">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="759c0-114">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="759c0-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759c0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="759c0-115">Requirements</span></span>  
 <span data-ttu-id="759c0-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="759c0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759c0-117">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="759c0-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="759c0-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="759c0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="759c0-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759c0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759c0-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="759c0-120">See also</span></span>

- [<span data-ttu-id="759c0-121">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="759c0-121">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="759c0-122">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="759c0-122">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="759c0-123">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="759c0-123">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="759c0-124">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="759c0-124">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="759c0-125">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="759c0-125">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="759c0-126">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="759c0-126">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="759c0-127">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="759c0-127">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="759c0-128">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="759c0-128">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="759c0-129">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="759c0-129">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="759c0-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="759c0-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
