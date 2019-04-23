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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92bc16091abd3e21ebd226fb13dd47b55b0c9cc4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166831"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="55cf9-102">ICorProfilerInfo4::EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="55cf9-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="55cf9-103">JIT로 컴파일되고 JIT 다시 컴파일된 이전에 있던 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="55cf9-104">이 메서드를 대체 합니다 [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 메서드를 JIT 다시 컴파일된 Id를 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55cf9-105">구문</span><span class="sxs-lookup"><span data-stu-id="55cf9-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55cf9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55cf9-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="55cf9-107">[out] 에 대 한 포인터를 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55cf9-108">설명</span><span class="sxs-lookup"><span data-stu-id="55cf9-108">Remarks</span></span>  
 <span data-ttu-id="55cf9-109">이 메서드를 사용 하 여 겹치면 `JITCompilation` 와 같이 콜백 합니다 [icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="55cf9-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="55cf9-110">반환된 된 열거형에 대 한 값이 포함 된 `COR_PRF_FUNCTION::reJitId` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="55cf9-111">합니다 [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 때문에이 메서드를 대체 하는 메서드를 JIT 다시 컴파일된 Id를 열거 하지 않습니다는 `COR_PRF_FUNCTION::reJitId` 필드는 항상 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="55cf9-112">`ICorProfilerInfo4::EnumJITedFunctions` 했기 때문에 메서드 JIT 다시 컴파일된 Id를 열거할지 않습니다는 `COR_PRF_FUNCTION::reJitId` 필드는 올바르게 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="55cf9-113">유의 합니다 [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) 반면 메서드는 가비지 수집을 트리거할 수 있습니다 [ICorProfilerInfo3::EnumJITedFunctions 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="55cf9-114">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf9-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55cf9-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55cf9-115">Requirements</span></span>  
 <span data-ttu-id="55cf9-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55cf9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55cf9-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55cf9-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55cf9-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55cf9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55cf9-119">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55cf9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cf9-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="55cf9-120">See also</span></span>

- [<span data-ttu-id="55cf9-121">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="55cf9-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="55cf9-122">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55cf9-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="55cf9-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55cf9-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="55cf9-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="55cf9-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
