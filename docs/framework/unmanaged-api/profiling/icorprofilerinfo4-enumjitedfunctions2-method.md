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
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496131"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="f41fe-102">ICorProfilerInfo4::EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="f41fe-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="f41fe-103">이전에 JIT 컴파일된 후 JIT 다시 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="f41fe-104">이 메서드는 JIT 다시 컴파일된 Id를 열거 하지 않는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f41fe-105">구문</span><span class="sxs-lookup"><span data-stu-id="f41fe-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f41fe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f41fe-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f41fe-107">제한이 [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f41fe-108">설명</span><span class="sxs-lookup"><span data-stu-id="f41fe-108">Remarks</span></span>  
 <span data-ttu-id="f41fe-109">이 메서드 `JITCompilation` 는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 메서드와 같은 콜백과 겹칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="f41fe-110">반환 된 열거형에는 필드에 대 한 값이 포함 됩니다 `COR_PRF_FUNCTION::reJitId` .</span><span class="sxs-lookup"><span data-stu-id="f41fe-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="f41fe-111">이 메서드가 대체 하는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 항상 0으로 설정 되므로 JIT 다시 컴파일된 id를 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="f41fe-112">`ICorProfilerInfo4::EnumJITedFunctions`이 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 올바르게 설정 되어 있으므로 JIT 다시 컴파일된 id를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="f41fe-113">[ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드는 가비지 수집을 트리거할 수 있지만 [ICorProfilerInfo3:: EnumJITedFunctions 메서드](icorprofilerinfo3-enumjitedfunctions-method.md) 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f41fe-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="f41fe-114">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f41fe-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41fe-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f41fe-115">Requirements</span></span>  
 <span data-ttu-id="f41fe-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f41fe-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41fe-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f41fe-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f41fe-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f41fe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f41fe-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f41fe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41fe-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f41fe-120">See also</span></span>

- [<span data-ttu-id="f41fe-121">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="f41fe-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="f41fe-122">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f41fe-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f41fe-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f41fe-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f41fe-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="f41fe-124">Profiling</span></span>](index.md)
