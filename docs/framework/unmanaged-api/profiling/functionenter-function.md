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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d38c32c4ed938de4a517009c5a76310df6d39fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586747"
---
# <a name="functionenter-function"></a><span data-ttu-id="d5a5a-102">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-102">FunctionEnter Function</span></span>
<span data-ttu-id="d5a5a-103">컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5a5a-104">`FunctionEnter` 함수는.NET Framework 버전 2.0에서에서 사용 되지 않습니다 및 용도는 성능 저하가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="d5a5a-105">사용 된 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a5a-106">구문</span><span class="sxs-lookup"><span data-stu-id="d5a5a-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5a5a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="d5a5a-108">[in] 컨트롤이 전달 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5a5a-109">설명</span><span class="sxs-lookup"><span data-stu-id="d5a5a-109">Remarks</span></span>  
 <span data-ttu-id="d5a5a-110">`FunctionEnter` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="d5a5a-111">구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d5a5a-112">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d5a5a-113">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d5a5a-114">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d5a5a-115">구현의 `FunctionEnter` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d5a5a-116">구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d5a5a-117">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionEnter` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="d5a5a-118">또한는 `FunctionEnter` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a5a-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5a5a-119">Requirements</span></span>  
 <span data-ttu-id="d5a5a-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5a5a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a5a-121">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d5a5a-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d5a5a-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5a5a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5a5a-123">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="d5a5a-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a5a-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5a5a-124">See also</span></span>

- [<span data-ttu-id="d5a5a-125">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d5a5a-126">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d5a5a-127">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="d5a5a-128">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="d5a5a-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d5a5a-129">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d5a5a-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
