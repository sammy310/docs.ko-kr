---
description: '자세한 정보: FunctionEnter 함수'
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
ms.openlocfilehash: 0f5c9f0dde405aaadf50a7da476bbae664ef8ef7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759380"
---
# <a name="functionenter-function"></a><span data-ttu-id="e3cb4-103">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-103">FunctionEnter Function</span></span>

<span data-ttu-id="e3cb4-104">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-104">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3cb4-105">`FunctionEnter`함수는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않으며,이 함수를 사용 하면 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-105">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="e3cb4-106">대신 [FunctionEnter2](functionenter2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-106">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cb4-107">구문</span><span class="sxs-lookup"><span data-stu-id="e3cb4-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3cb4-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-108">Parameters</span></span>

<span data-ttu-id="e3cb4-109">`funcID` 진행 제어가 전달 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-109">`funcID` [in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3cb4-110">설명</span><span class="sxs-lookup"><span data-stu-id="e3cb4-110">Remarks</span></span>  

 <span data-ttu-id="e3cb4-111">`FunctionEnter`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-111">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="e3cb4-112">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e3cb4-113">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e3cb4-114">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e3cb4-115">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e3cb4-116">의 구현은 `FunctionEnter` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-116">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e3cb4-117">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e3cb4-118">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionEnter` .</span><span class="sxs-lookup"><span data-stu-id="e3cb4-118">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="e3cb4-119">또한 함수는 관리 `FunctionEnter` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-119">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3cb4-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3cb4-120">Requirements</span></span>  

 <span data-ttu-id="e3cb4-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3cb4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3cb4-122">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="e3cb4-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e3cb4-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3cb4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3cb4-124">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="e3cb4-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cb4-125">참조</span><span class="sxs-lookup"><span data-stu-id="e3cb4-125">See also</span></span>

- [<span data-ttu-id="e3cb4-126">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="e3cb4-127">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="e3cb4-128">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="e3cb4-129">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="e3cb4-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="e3cb4-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e3cb4-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
