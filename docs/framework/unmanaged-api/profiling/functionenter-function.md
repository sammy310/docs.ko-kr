---
title: FunctionEnter 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: caea1d3d526017c0118f95bb138ee4ac45d2c137
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866998"
---
# <a name="functionenter-function"></a><span data-ttu-id="e35c2-102">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="e35c2-102">FunctionEnter Function</span></span>
<span data-ttu-id="e35c2-103">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e35c2-104">`FunctionEnter` 함수는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않으며,이 함수를 사용 하면 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="e35c2-105">대신 [FunctionEnter2](functionenter2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-105">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35c2-106">구문</span><span class="sxs-lookup"><span data-stu-id="e35c2-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e35c2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e35c2-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="e35c2-108">\[] 컨트롤을 전달할 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e35c2-109">주의</span><span class="sxs-lookup"><span data-stu-id="e35c2-109">Remarks</span></span>  
 <span data-ttu-id="e35c2-110">`FunctionEnter` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="e35c2-111">구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e35c2-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e35c2-113">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e35c2-114">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e35c2-115">`FunctionEnter` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e35c2-116">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e35c2-117">가비지 수집을 시도 하면 `FunctionEnter` 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="e35c2-118">또한 `FunctionEnter` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35c2-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e35c2-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e35c2-119">Requirements</span></span>  
 <span data-ttu-id="e35c2-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e35c2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e35c2-121">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e35c2-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e35c2-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e35c2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e35c2-123">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e35c2-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35c2-124">참조</span><span class="sxs-lookup"><span data-stu-id="e35c2-124">See also</span></span>

- [<span data-ttu-id="e35c2-125">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="e35c2-125">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="e35c2-126">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="e35c2-126">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="e35c2-127">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="e35c2-127">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="e35c2-128">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="e35c2-128">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="e35c2-129">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e35c2-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
