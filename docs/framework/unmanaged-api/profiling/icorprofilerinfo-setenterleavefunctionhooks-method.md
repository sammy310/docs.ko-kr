---
description: '자세히 알아보기: ICorProfilerInfo:: SetEnterLeaveFunctionHooks 메서드'
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
ms.openlocfilehash: 45c161a76f3ae568da6a83a2c45acb214a327ff1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687209"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="4247c-103">ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드</span><span class="sxs-lookup"><span data-stu-id="4247c-103">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>

<span data-ttu-id="4247c-104">관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-104">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4247c-105">구문</span><span class="sxs-lookup"><span data-stu-id="4247c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4247c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4247c-106">Parameters</span></span>  

 `pFuncEnter`  
 <span data-ttu-id="4247c-107">진행 [Functionenter](functionenter-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-107">[in] A pointer to the implementation to be used as the [FunctionEnter](functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="4247c-108">진행 [Functionleave](functionleave-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-108">[in] A pointer to the implementation to be used as the [FunctionLeave](functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="4247c-109">진행 [FunctionTailcall](functiontailcall-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-109">[in] A pointer to the implementation to be used as the [FunctionTailcall](functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4247c-110">설명</span><span class="sxs-lookup"><span data-stu-id="4247c-110">Remarks</span></span>  

 <span data-ttu-id="4247c-111">.NET Framework 버전 1.0에서는 각 함수 포인터가 null 일 수 있으므로 해당 콜백을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-111">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="4247c-112">한 번에 하나의 콜백 집합만 활성 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-112">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="4247c-113">따라서 프로파일러가 `SetEnterLeaveFunctionHooks` 및 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 모두 호출 하면가 우선적으로 `SetEnterLeaveFunctionHooks2` 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-113">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="4247c-114">`SetEnterLeaveFunctionHooks`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4247c-114">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4247c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4247c-115">Requirements</span></span>  

 <span data-ttu-id="4247c-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4247c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4247c-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4247c-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4247c-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4247c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4247c-119">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4247c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4247c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4247c-120">See also</span></span>

- [<span data-ttu-id="4247c-121">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4247c-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
