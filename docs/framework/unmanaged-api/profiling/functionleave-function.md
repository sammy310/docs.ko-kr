---
title: FunctionLeave 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 836e4843ead940bc9f76ff6bdd0433e21e400afd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500639"
---
# <a name="functionleave-function"></a><span data-ttu-id="5cb64-102">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="5cb64-102">FunctionLeave Function</span></span>
<span data-ttu-id="5cb64-103">함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5cb64-104">`FunctionLeave`함수는 .NET Framework 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="5cb64-105">계속 작동 하지만 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="5cb64-106">대신 [FunctionLeave2](functionleave2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb64-107">구문</span><span class="sxs-lookup"><span data-stu-id="5cb64-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cb64-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cb64-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="5cb64-109">\[in] 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cb64-110">설명</span><span class="sxs-lookup"><span data-stu-id="5cb64-110">Remarks</span></span>  
 <span data-ttu-id="5cb64-111">`FunctionLeave`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="5cb64-112">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="5cb64-113">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5cb64-114">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5cb64-115">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5cb64-116">의 구현은 `FunctionLeave` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="5cb64-117">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5cb64-118">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionLeave` .</span><span class="sxs-lookup"><span data-stu-id="5cb64-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="5cb64-119">또한 함수는 관리 `FunctionLeave` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cb64-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cb64-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cb64-120">Requirements</span></span>  
 <span data-ttu-id="5cb64-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cb64-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cb64-122">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="5cb64-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5cb64-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cb64-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cb64-124">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="5cb64-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb64-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cb64-125">See also</span></span>

- [<span data-ttu-id="5cb64-126">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="5cb64-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="5cb64-127">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="5cb64-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="5cb64-128">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="5cb64-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="5cb64-129">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="5cb64-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="5cb64-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5cb64-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
