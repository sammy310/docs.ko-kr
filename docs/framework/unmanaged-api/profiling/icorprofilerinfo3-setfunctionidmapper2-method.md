---
title: ICorProfilerInfo3::SetFunctionIDMapper2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d04c15fa181d0e7bf8a92c1b6ecdef5b8b13bd7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182431"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="9fce1-102">ICorProfilerInfo3::SetFunctionIDMapper2 메서드</span><span class="sxs-lookup"><span data-stu-id="9fce1-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="9fce1-103">`FunctionID` 값을 대체 값에 매핑하기 위해 호출되는 프로파일러 구현 함수를 지정합니다. 대체 값은 프로파일러의 함수 진입점/종료점 후크에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fce1-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="9fce1-104">이 메서드가 확장 합니다 [icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) 프로파일러 런타임 중 명확히 구분 하는 데 사용할 수 있는 추가 데이터 매개 변수에 메서드.</span><span class="sxs-lookup"><span data-stu-id="9fce1-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fce1-105">구문</span><span class="sxs-lookup"><span data-stu-id="9fce1-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fce1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fce1-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="9fce1-107">[in] 에 대 한 포인터를 [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) 매핑할 호출 되는 구현 된 `FunctionID` 대체 값으로 값.</span><span class="sxs-lookup"><span data-stu-id="9fce1-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="9fce1-108">[in] 전달 되는 포인터를 매 [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) 현재 런타임에 의해 수행 된 호출 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fce1-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="9fce1-109">프로파일러는이 정보를 사용 하 여 런타임 중 명확히 구분 하 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fce1-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fce1-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="9fce1-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fce1-111">설명</span><span class="sxs-lookup"><span data-stu-id="9fce1-111">Remarks</span></span>  
 <span data-ttu-id="9fce1-112">FunctionID 값에 대 한 대안 프로파일러의 함수 항목/종료 점 후크에 전달 됩니다 ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)하십시오 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; 또는 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)를 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), 및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md))에서 지정 된 된 [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 나 [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9fce1-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="9fce1-113">합니다 `FunctionIDMapper2` 메서드를 한 번만 설정 될 수 있으며 설정 하는 것이 좋습니다 합니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fce1-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fce1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fce1-114">Requirements</span></span>  
 <span data-ttu-id="9fce1-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9fce1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fce1-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fce1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fce1-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fce1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fce1-118">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fce1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fce1-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fce1-119">See also</span></span>

- [<span data-ttu-id="9fce1-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="9fce1-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="9fce1-121">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fce1-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9fce1-122">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fce1-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9fce1-123">프로파일링</span><span class="sxs-lookup"><span data-stu-id="9fce1-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
