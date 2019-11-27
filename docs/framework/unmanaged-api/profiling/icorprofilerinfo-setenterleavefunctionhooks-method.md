---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 45593e7e30e1c8f8036489936aab3c607b01dd52
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438651"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="aee5c-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드</span><span class="sxs-lookup"><span data-stu-id="aee5c-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="aee5c-103">관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="aee5c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aee5c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aee5c-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="aee5c-106">진행 [Functionenter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="aee5c-107">진행 [Functionleave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="aee5c-108">진행 [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aee5c-109">설명</span><span class="sxs-lookup"><span data-stu-id="aee5c-109">Remarks</span></span>  
 <span data-ttu-id="aee5c-110">.NET Framework 버전 1.0에서는 각 함수 포인터가 null 일 수 있으므로 해당 콜백을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="aee5c-111">한 번에 하나의 콜백 집합만 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="aee5c-112">따라서 프로파일러가 `SetEnterLeaveFunctionHooks` 및 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 모두 호출 하는 경우 `SetEnterLeaveFunctionHooks2`가 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="aee5c-113">`SetEnterLeaveFunctionHooks` 메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee5c-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aee5c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aee5c-114">Requirements</span></span>  
 <span data-ttu-id="aee5c-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aee5c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aee5c-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aee5c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aee5c-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aee5c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aee5c-118">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aee5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee5c-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="aee5c-119">See also</span></span>

- [<span data-ttu-id="aee5c-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aee5c-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
