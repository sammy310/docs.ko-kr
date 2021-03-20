---
description: '자세히 알아보기: FunctionEnter3 함수'
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
ms.openlocfilehash: 4726a080157b99c7538fe8a66cf8b26403564ad2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759301"
---
# <a name="functionenter3-function"></a><span data-ttu-id="5a7c9-103">FunctionEnter3 함수</span><span class="sxs-lookup"><span data-stu-id="5a7c9-103">FunctionEnter3 Function</span></span>

<span data-ttu-id="5a7c9-104">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-104">Notifies the profiler that control is being passed to a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a7c9-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a7c9-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a7c9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a7c9-106">Parameters</span></span>

<span data-ttu-id="5a7c9-107">`functionOrRemappedID` 진행 제어가 전달 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-107">`functionOrRemappedID` [in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a7c9-108">설명</span><span class="sxs-lookup"><span data-stu-id="5a7c9-108">Remarks</span></span>  

 <span data-ttu-id="5a7c9-109">`FunctionEnter3`콜백 함수는 함수가 호출 될 때 프로파일러에 알립니다. 하지만 인수 검사는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-109">The `FunctionEnter3` callback function notifies the profiler as functions are being called, but does not support argument inspection.</span></span> <span data-ttu-id="5a7c9-110">[ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 를 사용 하 여이 함수의 구현을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-110">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="5a7c9-111">`FunctionEnter3`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-111">The `FunctionEnter3` function is a callback; you must implement it.</span></span> <span data-ttu-id="5a7c9-112">구현에서는 저장소 클래스 특성을 사용 해야 합니다 `__declspec(naked)` .</span><span class="sxs-lookup"><span data-stu-id="5a7c9-112">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="5a7c9-113">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5a7c9-114">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5a7c9-115">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a7c9-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a7c9-116">Requirements</span></span>  

 <span data-ttu-id="5a7c9-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a7c9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a7c9-118">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="5a7c9-118">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5a7c9-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a7c9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a7c9-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a7c9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7c9-121">참조</span><span class="sxs-lookup"><span data-stu-id="5a7c9-121">See also</span></span>

- [<span data-ttu-id="5a7c9-122">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="5a7c9-122">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="5a7c9-123">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="5a7c9-123">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="5a7c9-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5a7c9-124">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="5a7c9-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5a7c9-125">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="5a7c9-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5a7c9-126">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="5a7c9-127">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="5a7c9-127">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="5a7c9-128">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5a7c9-128">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="5a7c9-129">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="5a7c9-129">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="5a7c9-130">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="5a7c9-130">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="5a7c9-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5a7c9-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
