---
title: ICorProfilerCallback4::ReJITError 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 46312aaf530e69f0e6a90e35515f1373d01b4340
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730242"
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="36c98-102">ICorProfilerCallback4::ReJITError 메서드</span><span class="sxs-lookup"><span data-stu-id="36c98-102">ICorProfilerCallback4::ReJITError Method</span></span>

<span data-ttu-id="36c98-103">JIT (just-in-time) 컴파일러에서 재컴파일을 처리할 때 오류가 발생 했음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c98-104">구문</span><span class="sxs-lookup"><span data-stu-id="36c98-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c98-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36c98-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="36c98-106">진행 `ModuleID` 실패 한 재컴파일을 시도한입니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="36c98-107">진행 `MethodDef` 실패 한 재컴파일을 시도한 메서드의입니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="36c98-108">진행 다시 컴파일하거나 다시 컴파일하도록 표시 되는 함수 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="36c98-109">이 값 `NULL` 은 오류가 발생 하는 경우 (예: 프로파일러에서 다시 컴파일할 메서드에 대해 잘못 된 메타 데이터 토큰을 지정 하는 경우)와 같은 방법으로 오류가 발생 한 경우에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="36c98-110">진행 오류의 특성을 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="36c98-111">값 목록은 상태 HRESULT 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36c98-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36c98-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="36c98-112">Return Value</span></span>  

 <span data-ttu-id="36c98-113">이 콜백의 반환 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="36c98-114">상태 HRESULTS</span><span class="sxs-lookup"><span data-stu-id="36c98-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="36c98-115">상태 배열 HRESULT</span><span class="sxs-lookup"><span data-stu-id="36c98-115">Status array HRESULT</span></span>|<span data-ttu-id="36c98-116">설명</span><span class="sxs-lookup"><span data-stu-id="36c98-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="36c98-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="36c98-117">E_INVALIDARG</span></span>|<span data-ttu-id="36c98-118">`moduleID`또는 `methodDef` 토큰이 인 `NULL` 경우</span><span class="sxs-lookup"><span data-stu-id="36c98-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="36c98-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="36c98-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="36c98-120">모듈은 아직 완전히 로드되지 않았거나 언로드되는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="36c98-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="36c98-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="36c98-122">지정 된 모듈이 동적으로 생성 된 경우 (예: `Reflection.Emit` )이 메서드에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="36c98-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="36c98-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="36c98-124">메서드는 수집 가능한 어셈블리로 인스턴스화되기 때문에 다시 컴파일할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="36c98-125">비 리플렉션 컨텍스트 (예:)에 정의 된 형식 및 함수를 수집 가능한 `List<MyCollectibleStruct>` 어셈블리로 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="36c98-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="36c98-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="36c98-127">지정 된 메서드를 JIT 다시 컴파일하도록 표시 하는 동안 CLR에 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="36c98-128">기타</span><span class="sxs-lookup"><span data-stu-id="36c98-128">Other</span></span>|<span data-ttu-id="36c98-129">운영 체제가 CLR의 제어 범위를 벗어난 오류를 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="36c98-130">예를 들어 메모리 페이지의 액세스 보호를 변경 하는 시스템 호출이 실패 하면 운영 체제 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36c98-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36c98-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36c98-131">Requirements</span></span>  

 <span data-ttu-id="36c98-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36c98-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c98-133">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36c98-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36c98-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36c98-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36c98-135">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c98-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c98-136">참조</span><span class="sxs-lookup"><span data-stu-id="36c98-136">See also</span></span>

- [<span data-ttu-id="36c98-137">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36c98-137">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="36c98-138">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36c98-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
