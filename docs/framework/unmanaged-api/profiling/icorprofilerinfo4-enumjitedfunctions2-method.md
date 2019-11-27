---
title: ICorProfilerInfo4::EnumJITedFunctions2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 09d273a81ed4f956508e4fadb628b28e18d00f90
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449570"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="f3c10-102">ICorProfilerInfo4::EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="f3c10-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="f3c10-103">이전에 JIT 컴파일된 후 JIT 다시 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="f3c10-104">이 메서드는 JIT 다시 컴파일된 Id를 열거 하지 않는 [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 메서드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c10-105">구문</span><span class="sxs-lookup"><span data-stu-id="f3c10-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3c10-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3c10-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f3c10-107">제한이 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3c10-108">설명</span><span class="sxs-lookup"><span data-stu-id="f3c10-108">Remarks</span></span>  
 <span data-ttu-id="f3c10-109">이 메서드는 [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) 메서드와 같은 `JITCompilation` 콜백과 겹칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="f3c10-110">반환 된 열거형에는 `COR_PRF_FUNCTION::reJitId` 필드의 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="f3c10-111">`COR_PRF_FUNCTION::reJitId` 필드가 항상 0으로 설정 되어 있으므로이 메서드에서 대체 하는 [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 메서드는 JIT 다시 컴파일된 id를 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="f3c10-112">`ICorProfilerInfo4::EnumJITedFunctions` 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 올바르게 설정 되어 있으므로 JIT 다시 컴파일된 Id를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="f3c10-113">[ICorProfilerInfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드는 가비지 수집을 트리거할 수 있지만 [ICorProfilerInfo3:: EnumJITedFunctions 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3c10-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="f3c10-114">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3c10-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c10-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3c10-115">Requirements</span></span>  
 <span data-ttu-id="f3c10-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3c10-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c10-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3c10-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3c10-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3c10-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c10-119">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c10-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c10-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="f3c10-120">See also</span></span>

- [<span data-ttu-id="f3c10-121">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="f3c10-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="f3c10-122">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3c10-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f3c10-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3c10-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f3c10-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f3c10-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
