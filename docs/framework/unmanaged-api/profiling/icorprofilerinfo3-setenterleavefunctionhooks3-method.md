---
description: '자세히 알아보기: ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 메서드'
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: c741054c50fb74afe79f10607e24424a07d2f8c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687027"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="71789-103">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 메서드</span><span class="sxs-lookup"><span data-stu-id="71789-103">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>

<span data-ttu-id="71789-104">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md) 함수에서 호출 되는 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71789-104">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71789-105">구문</span><span class="sxs-lookup"><span data-stu-id="71789-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71789-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71789-106">Parameters</span></span>  

 `pFuncEnter3`  
 <span data-ttu-id="71789-107">진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionEnter3` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71789-107">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="71789-108">진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionLeave3` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71789-108">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="71789-109">진행 콜백으로 사용할 구현에 대 한 포인터 `FunctionTailcall3` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71789-109">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71789-110">설명</span><span class="sxs-lookup"><span data-stu-id="71789-110">Remarks</span></span>  

 <span data-ttu-id="71789-111">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)및 [FunctionTailcall3](functiontailcall3-function.md) 후크는 스택 프레임 및 인수 검사를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71789-111">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="71789-112">이 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` 및/또는 플래그를  `COR_PRF_ENABLE_FRAME_INFO` 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71789-112">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="71789-113">프로파일러는 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정한 다음 [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 메서드를 사용 하 여이 함수의 구현을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71789-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="71789-114">한 번에 하나의 콜백 집합만 활성 상태일 수 있으며 최신 버전이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71789-114">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="71789-115">따라서 프로파일러가 [SetEnterLeaveFunctionHooks2 메서드와](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 메서드를 모두 호출 하면 `SetEnterLeaveFunctionHooks3` `SetEnterLeaveFunctionHooks3` 이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71789-115">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="71789-116">`SetEnterLeaveFunctionHooks3`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71789-116">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71789-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71789-117">Requirements</span></span>  

 <span data-ttu-id="71789-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71789-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71789-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71789-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71789-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71789-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71789-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71789-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71789-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71789-122">See also</span></span>

- [<span data-ttu-id="71789-123">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71789-123">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="71789-124">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="71789-124">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="71789-125">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="71789-125">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="71789-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="71789-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="71789-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71789-127">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="71789-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71789-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="71789-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="71789-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="71789-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="71789-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="71789-131">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="71789-131">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="71789-132">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71789-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="71789-133">프로파일링</span><span class="sxs-lookup"><span data-stu-id="71789-133">Profiling</span></span>](index.md)
