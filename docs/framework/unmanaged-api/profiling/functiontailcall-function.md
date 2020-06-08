---
title: FunctionTailcall 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: 42ea497bdcab71518bec08514b827d76f0317d57
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500600"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="4a219-102">FunctionTailcall 함수</span><span class="sxs-lookup"><span data-stu-id="4a219-102">FunctionTailcall Function</span></span>
<span data-ttu-id="4a219-103">현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a219-104">`FunctionTailcall`함수는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4a219-105">계속 작동 하지만 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="4a219-106">대신 [FunctionTailcall2](functiontailcall2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-106">Use the [FunctionTailcall2](functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a219-107">구문</span><span class="sxs-lookup"><span data-stu-id="4a219-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a219-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a219-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="4a219-109">\[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-109">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a219-110">설명</span><span class="sxs-lookup"><span data-stu-id="4a219-110">Remarks</span></span>  
 <span data-ttu-id="4a219-111">마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하며, 마무리 호출을 수행한 함수의 호출자에 게 직접 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="4a219-112">즉, tail 호출의 대상인 함수에 대해 [Functionleave](functionleave-function.md) 콜백이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-112">This means that a [FunctionLeave](functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="4a219-113">`FunctionTailcall`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="4a219-114">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="4a219-115">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="4a219-116">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="4a219-117">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="4a219-118">의 구현은 `FunctionTailcall` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="4a219-119">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="4a219-120">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionTailcall` .</span><span class="sxs-lookup"><span data-stu-id="4a219-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="4a219-121">또한 함수는 관리 `FunctionTailcall` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a219-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a219-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a219-122">Requirements</span></span>  
 <span data-ttu-id="4a219-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a219-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a219-124">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="4a219-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4a219-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a219-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a219-126">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="4a219-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a219-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a219-127">See also</span></span>

- [<span data-ttu-id="4a219-128">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="4a219-128">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="4a219-129">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="4a219-129">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="4a219-130">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="4a219-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="4a219-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="4a219-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
