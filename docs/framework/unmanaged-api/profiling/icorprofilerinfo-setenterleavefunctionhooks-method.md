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
ms.openlocfilehash: cf0726a12b0274fd7a38e82b66c33430d26b031a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497454"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="c2ec2-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드</span><span class="sxs-lookup"><span data-stu-id="c2ec2-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="c2ec2-103">관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ec2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2ec2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2ec2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2ec2-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="c2ec2-106">진행 [Functionenter](functionenter-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-106">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="c2ec2-107">진행 [Functionleave](functionleave-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-107">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="c2ec2-108">진행 [FunctionTailcall](functiontailcall-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2ec2-109">설명</span><span class="sxs-lookup"><span data-stu-id="c2ec2-109">Remarks</span></span>  
 <span data-ttu-id="c2ec2-110">.NET Framework 버전 1.0에서는 각 함수 포인터가 null 일 수 있으므로 해당 콜백을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="c2ec2-111">한 번에 하나의 콜백 집합만 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="c2ec2-112">따라서 프로파일러가 `SetEnterLeaveFunctionHooks` 및 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 모두 호출 하면가 우선적으로 `SetEnterLeaveFunctionHooks2` 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="c2ec2-113">`SetEnterLeaveFunctionHooks`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2ec2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2ec2-114">Requirements</span></span>  
 <span data-ttu-id="c2ec2-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ec2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2ec2-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2ec2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2ec2-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2ec2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2ec2-118">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2ec2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ec2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2ec2-119">See also</span></span>

- [<span data-ttu-id="c2ec2-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2ec2-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
