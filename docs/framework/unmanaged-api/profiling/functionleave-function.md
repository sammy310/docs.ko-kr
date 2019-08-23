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
ms.openlocfilehash: 238a5f19bd8cbd89a5537b2b9297bfa9e1f54613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952890"
---
# <a name="functionleave-function"></a><span data-ttu-id="10e95-102">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="10e95-102">FunctionLeave Function</span></span>
<span data-ttu-id="10e95-103">함수가 호출자에 게 반환 될 것 이라고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10e95-104">함수 `FunctionLeave` 는 .NET Framework 2.0에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="10e95-105">계속 작동 하지만 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="10e95-106">대신 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e95-107">구문</span><span class="sxs-lookup"><span data-stu-id="10e95-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10e95-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10e95-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="10e95-109">진행 반환 되는 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10e95-110">설명</span><span class="sxs-lookup"><span data-stu-id="10e95-110">Remarks</span></span>  
 <span data-ttu-id="10e95-111">함수 `FunctionLeave` 는 콜백입니다. 함수를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="10e95-112">구현은 ( `__declspec``naked`) 저장소 클래스 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="10e95-113">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="10e95-114">항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="10e95-115">종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="10e95-116">의 `FunctionLeave` 구현은 가비지 수집을 지연 하므로 차단 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="10e95-117">스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="10e95-118">가비지 수집을 시도 하면 런타임이 반환 될 때까지 `FunctionLeave` 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="10e95-119">또한 함수는 `FunctionLeave` 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e95-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e95-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10e95-120">Requirements</span></span>  
 <span data-ttu-id="10e95-121">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="10e95-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e95-122">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="10e95-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="10e95-123">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e95-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e95-124">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="10e95-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e95-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="10e95-125">See also</span></span>

- [<span data-ttu-id="10e95-126">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="10e95-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="10e95-127">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="10e95-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="10e95-128">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="10e95-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="10e95-129">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="10e95-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="10e95-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="10e95-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
