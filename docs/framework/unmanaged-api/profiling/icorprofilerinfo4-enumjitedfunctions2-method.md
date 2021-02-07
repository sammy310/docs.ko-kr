---
description: '자세히 알아보기: ICorProfilerInfo4:: EnumJITedFunctions2 메서드'
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
ms.openlocfilehash: 3740236cfe2bc7ecc6cd3bbeb3345c7510dd159f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686949"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="59764-103">ICorProfilerInfo4::EnumJITedFunctions2 메서드</span><span class="sxs-lookup"><span data-stu-id="59764-103">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>

<span data-ttu-id="59764-104">이전에 JIT 컴파일된 후 JIT 다시 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59764-104">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="59764-105">이 메서드는 JIT 다시 컴파일된 Id를 열거 하지 않는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="59764-105">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59764-106">구문</span><span class="sxs-lookup"><span data-stu-id="59764-106">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59764-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59764-107">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="59764-108">제한이 [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59764-108">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59764-109">설명</span><span class="sxs-lookup"><span data-stu-id="59764-109">Remarks</span></span>  

 <span data-ttu-id="59764-110">이 메서드 `JITCompilation` 는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 메서드와 같은 콜백과 겹칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59764-110">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="59764-111">반환 된 열거형에는 필드에 대 한 값이 포함 됩니다 `COR_PRF_FUNCTION::reJitId` .</span><span class="sxs-lookup"><span data-stu-id="59764-111">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="59764-112">이 메서드가 대체 하는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 항상 0으로 설정 되므로 JIT 다시 컴파일된 id를 열거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59764-112">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="59764-113">`ICorProfilerInfo4::EnumJITedFunctions`이 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 올바르게 설정 되어 있으므로 JIT 다시 컴파일된 id를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="59764-113">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="59764-114">[ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드는 가비지 수집을 트리거할 수 있지만 [ICorProfilerInfo3:: EnumJITedFunctions 메서드](icorprofilerinfo3-enumjitedfunctions-method.md) 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59764-114">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="59764-115">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59764-115">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59764-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59764-116">Requirements</span></span>  

 <span data-ttu-id="59764-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59764-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59764-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59764-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59764-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59764-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59764-120">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59764-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59764-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59764-121">See also</span></span>

- [<span data-ttu-id="59764-122">EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="59764-122">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="59764-123">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59764-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="59764-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59764-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="59764-125">프로파일링</span><span class="sxs-lookup"><span data-stu-id="59764-125">Profiling</span></span>](index.md)
