---
description: '자세한 정보: FunctionLeave 함수'
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
ms.openlocfilehash: 619c1ecd92d2cc53512687d542becb3a2636b8af
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759497"
---
# <a name="functionleave-function"></a><span data-ttu-id="da70b-103">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="da70b-103">FunctionLeave Function</span></span>

<span data-ttu-id="da70b-104">함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-104">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da70b-105">`FunctionLeave`함수는 .NET Framework 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-105">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="da70b-106">계속 작동 하지만 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-106">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="da70b-107">대신 [FunctionLeave2](functionleave2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-107">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da70b-108">구문</span><span class="sxs-lookup"><span data-stu-id="da70b-108">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da70b-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da70b-109">Parameters</span></span>

<span data-ttu-id="da70b-110">`funcID` 진행 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-110">`funcID` [in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="da70b-111">설명</span><span class="sxs-lookup"><span data-stu-id="da70b-111">Remarks</span></span>  

 <span data-ttu-id="da70b-112">`FunctionLeave`함수는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-112">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="da70b-113">구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-113">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="da70b-114">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-114">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="da70b-115">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-115">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="da70b-116">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-116">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="da70b-117">의 구현은 `FunctionLeave` 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-117">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="da70b-118">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-118">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="da70b-119">가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionLeave` .</span><span class="sxs-lookup"><span data-stu-id="da70b-119">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="da70b-120">또한 함수는 관리 `FunctionLeave` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da70b-120">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da70b-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da70b-121">Requirements</span></span>  

 <span data-ttu-id="da70b-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da70b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da70b-123">**헤더:** Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="da70b-123">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="da70b-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da70b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da70b-125">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="da70b-125">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da70b-126">참조</span><span class="sxs-lookup"><span data-stu-id="da70b-126">See also</span></span>

- [<span data-ttu-id="da70b-127">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="da70b-127">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="da70b-128">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="da70b-128">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="da70b-129">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="da70b-129">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="da70b-130">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="da70b-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="da70b-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="da70b-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
