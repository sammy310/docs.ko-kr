---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73321a28b1c61775d08e2c60ee2b9a863b8250dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121682"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="3dce6-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 메서드</span><span class="sxs-lookup"><span data-stu-id="3dce6-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="3dce6-103">호출 되는 프로파일러 구현 함수를 지정 합니다 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)를 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dce6-104">구문</span><span class="sxs-lookup"><span data-stu-id="3dce6-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dce6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3dce6-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="3dce6-106">[in] 로 사용할 구현에 대 한 포인터를 `FunctionEnter3` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="3dce6-107">[in] 로 사용할 구현에 대 한 포인터를 `FunctionLeave3` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="3dce6-108">[in] 로 사용할 구현에 대 한 포인터를 `FunctionTailcall3` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dce6-109">설명</span><span class="sxs-lookup"><span data-stu-id="3dce6-109">Remarks</span></span>  
 <span data-ttu-id="3dce6-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)하십시오 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) 후크 스택 프레임 및 인수 검사를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="3dce6-111">해당 정보에 액세스할 수는 `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, 및/또는 `COR_PRF_ENABLE_FRAME_INFO` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="3dce6-112">프로파일러를 사용 하 여 수를 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 사용 하 여 메서드를 [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 등록 하는 방법에 이 함수의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="3dce6-113">한 번에 콜백 집합을 하나만 active 수 있으며 최신 버전이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="3dce6-114">따라서 프로파일러 둘 다 호출 하는 경우는 [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 하며 `SetEnterLeaveFunctionHooks3` 메서드를 `SetEnterLeaveFunctionHooks3` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="3dce6-115">합니다 `SetEnterLeaveFunctionHooks3` 프로파일러의 에서만 메서드를 호출할 수 있습니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dce6-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dce6-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dce6-116">Requirements</span></span>  
 <span data-ttu-id="3dce6-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3dce6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dce6-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3dce6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3dce6-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dce6-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3dce6-120">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="3dce6-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3dce6-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3dce6-121">See also</span></span>

- [<span data-ttu-id="3dce6-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3dce6-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="3dce6-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="3dce6-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="3dce6-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="3dce6-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="3dce6-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="3dce6-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="3dce6-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3dce6-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="3dce6-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3dce6-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="3dce6-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3dce6-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="3dce6-129">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="3dce6-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="3dce6-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="3dce6-130">ICorProfilerInfo3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="3dce6-131">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3dce6-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="3dce6-132">프로파일링</span><span class="sxs-lookup"><span data-stu-id="3dce6-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
