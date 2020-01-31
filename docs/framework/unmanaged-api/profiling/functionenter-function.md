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
ms.openlocfilehash: 38ed7de647aabefc95f515d9aa627b0e9c8d9015
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790253"
---
# <a name="functionenter-function"></a><span data-ttu-id="6119e-102">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="6119e-102">FunctionEnter Function</span></span>
<span data-ttu-id="6119e-103">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6119e-104">`FunctionEnter` 함수는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않으며,이 함수를 사용 하면 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="6119e-105">대신 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6119e-106">구문</span><span class="sxs-lookup"><span data-stu-id="6119e-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6119e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6119e-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="6119e-108">\[] 컨트롤을 전달할 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6119e-109">주의</span><span class="sxs-lookup"><span data-stu-id="6119e-109">Remarks</span></span>  
 <span data-ttu-id="6119e-110">`FunctionEnter` 함수는 콜백입니다. 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="6119e-111">구현은 `__declspec`(`naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="6119e-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6119e-113">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6119e-114">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6119e-115">`FunctionEnter` 구현은 가비지 수집을 지연 시킬 수 있으므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="6119e-116">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6119e-117">가비지 수집을 시도 하면 `FunctionEnter` 반환 될 때까지 런타임이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="6119e-118">또한 `FunctionEnter` 함수는 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6119e-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6119e-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6119e-119">Requirements</span></span>  
 <span data-ttu-id="6119e-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6119e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6119e-121">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="6119e-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6119e-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6119e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6119e-123">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="6119e-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6119e-124">참조</span><span class="sxs-lookup"><span data-stu-id="6119e-124">See also</span></span>

- [<span data-ttu-id="6119e-125">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="6119e-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="6119e-126">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="6119e-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="6119e-127">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="6119e-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="6119e-128">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="6119e-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="6119e-129">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6119e-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
