---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
ms.openlocfilehash: b17ab9382e5195881e5629d482e4327fc67562f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449595"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="f1f20-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f1f20-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="f1f20-103">관리 되는 함수의 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 후크에 대해 호출 되는 프로파일러 구현 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f20-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1f20-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f20-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1f20-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="f1f20-106">진행 `FunctionEnter3WithInfo` 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="f1f20-107">진행 `FunctionLeave3WithInfo` 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="f1f20-108">진행 `FunctionTailcall3WithInfo` 콜백으로 사용할 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f20-109">설명</span><span class="sxs-lookup"><span data-stu-id="f1f20-109">Remarks</span></span>  
 <span data-ttu-id="f1f20-110">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 후크는 스택 프레임 및 인수 검사를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="f1f20-111">이 정보에 액세스 하려면 `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`및/또는 `COR_PRF_ENABLE_FRAME_INFO` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="f1f20-112">프로파일러는 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드를 사용 하 여 이벤트 플래그를 설정한 다음 `SetEnterLeaveFunctionHooks3WithInfo` 메서드를 사용 하 여이 함수의 구현을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f1f20-113">한 번에 하나의 콜백 집합만 활성 상태일 수 있으며 최신 버전이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="f1f20-114">따라서 프로파일러가 [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) 및 `SetEnterLeaveFunctionHooks3WithInfo`를 모두 호출 하는 경우 `SetEnterLeaveFunctionHooks3WithInfo` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="f1f20-115">`SetEnterLeaveFunctionHooks3WithInfo` 메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f20-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f20-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1f20-116">Requirements</span></span>  
 <span data-ttu-id="f1f20-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1f20-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f20-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1f20-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1f20-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f20-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f20-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f20-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f20-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1f20-121">See also</span></span>

- [<span data-ttu-id="f1f20-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="f1f20-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f1f20-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="f1f20-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="f1f20-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="f1f20-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="f1f20-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f1f20-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="f1f20-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f1f20-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="f1f20-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f1f20-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="f1f20-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f1f20-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f1f20-129">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f1f20-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="f1f20-130">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1f20-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f1f20-131">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1f20-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f1f20-132">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f1f20-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
