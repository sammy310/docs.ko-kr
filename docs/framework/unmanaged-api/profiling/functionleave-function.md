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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b1fe219c4c852792390b48b0ea4d38adb702281
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218890"
---
# <a name="functionleave-function"></a><span data-ttu-id="7f1dc-102">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-102">FunctionLeave Function</span></span>
<span data-ttu-id="7f1dc-103">호출자에 게 반환 하려고 하는 함수는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f1dc-104">`FunctionLeave` 함수는.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="7f1dc-105">계속 작동 하지만 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="7f1dc-106">사용 된 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1dc-107">구문</span><span class="sxs-lookup"><span data-stu-id="7f1dc-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f1dc-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="7f1dc-109">[in] 식별자를 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f1dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="7f1dc-110">Remarks</span></span>  
 <span data-ttu-id="7f1dc-111">`FunctionLeave` 함수 콜백을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="7f1dc-112">구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="7f1dc-113">실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="7f1dc-114">항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="7f1dc-115">종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7f1dc-116">구현의 `FunctionLeave` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="7f1dc-117">구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7f1dc-118">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionLeave` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="7f1dc-119">또한는 `FunctionLeave` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f1dc-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f1dc-120">Requirements</span></span>  
 <span data-ttu-id="7f1dc-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f1dc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f1dc-122">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7f1dc-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7f1dc-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f1dc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f1dc-124">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="7f1dc-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1dc-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f1dc-125">See also</span></span>

- [<span data-ttu-id="7f1dc-126">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="7f1dc-127">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="7f1dc-128">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="7f1dc-129">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="7f1dc-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="7f1dc-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7f1dc-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
