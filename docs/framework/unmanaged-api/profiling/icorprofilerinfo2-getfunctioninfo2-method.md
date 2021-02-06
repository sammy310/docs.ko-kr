---
description: '자세히 알아보기: ICorProfilerInfo2:: GetFunctionInfo2 메서드'
title: ICorProfilerInfo2::GetFunctionInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type:
- apiref
ms.openlocfilehash: f0534a2e8cc8a9ce24f2c2b3deaade6215e15b5a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657075"
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="2f7c3-103">ICorProfilerInfo2::GetFunctionInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="2f7c3-103">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>

<span data-ttu-id="2f7c3-104">함수의 부모 클래스, 메타데이터 토큰 및 각 형식 인수 `ClassID`(있는 경우)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-104">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f7c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="2f7c3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f7c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f7c3-106">Parameters</span></span>  

 `funcId`  
 <span data-ttu-id="2f7c3-107">[in] 부모 클래스 및 기타 정보를 가져올 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-107">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="2f7c3-108">[in] 스택 프레임에 대한 정보를 가리키는 `COR_PRF_FRAME_INFO` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="2f7c3-109">[out] 함수의 부모 클래스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-109">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="2f7c3-110">[out] 함수의 부모 클래스가 정의된 모듈에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-110">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="2f7c3-111">[out] 함수의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-111">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="2f7c3-112">[in] `typeArgs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-112">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="2f7c3-113">[out] `ClassID` 값의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-113">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="2f7c3-114">[out] 각각 함수의 형식 인수 ID인 `ClassID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-114">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="2f7c3-115">메서드가 반환되면 `typeArgs`에 `ClassID` 값이 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-115">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f7c3-116">설명</span><span class="sxs-lookup"><span data-stu-id="2f7c3-116">Remarks</span></span>  

 <span data-ttu-id="2f7c3-117">프로파일러 코드는 [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) 를 호출 하 여 지정 된 모듈에 대 한 [메타 데이터](../metadata/index.md) 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-117">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="2f7c3-118">`pToken`에서 참조하는 위치로 반환되는 메타데이터 토큰을 사용하여 함수에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-118">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="2f7c3-119">`pClassId` 및 `typeArgs` 매개 변수를 통해 반환되는 클래스 ID 및 형식 인수는 다음 표와 같이 `frameInfo` 매개 변수에 전달되는 값에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-119">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="2f7c3-120">`frameInfo` 매개 변수의 값</span><span class="sxs-lookup"><span data-stu-id="2f7c3-120">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="2f7c3-121">결과</span><span class="sxs-lookup"><span data-stu-id="2f7c3-121">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="2f7c3-122">`FunctionEnter2` 콜백에서 가져온 `COR_PRF_FRAME_INFO` 값</span><span class="sxs-lookup"><span data-stu-id="2f7c3-122">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="2f7c3-123">`pClassId`에서 참조된 위치에 반환된 `ClassID` 및 `typeArgs` 배열에 반환된 모든 형식 인수가 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-123">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="2f7c3-124">`FunctionEnter2` 콜백 이외의 소스에서 가져온 `COR_PRF_FRAME_INFO`</span><span class="sxs-lookup"><span data-stu-id="2f7c3-124">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="2f7c3-125">정확한 `ClassID` 및 형식 인수를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-125">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="2f7c3-126">즉, `ClassID`가 null일 수도 있고 일부 형식 인수가 <xref:System.Object>로 반환될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-126">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="2f7c3-127">0</span><span class="sxs-lookup"><span data-stu-id="2f7c3-127">Zero</span></span>|<span data-ttu-id="2f7c3-128">정확한 `ClassID` 및 형식 인수를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-128">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="2f7c3-129">즉, `ClassID`가 null일 수도 있고 일부 형식 인수가 <xref:System.Object>로 반환될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-129">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="2f7c3-130">`GetFunctionInfo2`가 반환된 후 `typeArgs` 버퍼가 `ClassID` 값을 모두 포함할 수 있을 만큼 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-130">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="2f7c3-131">이렇게 하려면 `pcTypeArgs`가 가리키는 값을 `cTypeArgs` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-131">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="2f7c3-132">`pcTypeArgs`가 `cTypeArgs`를 `ClassID` 값의 크기로 나눈 값보다 큰 값을 가리키는 경우 더 큰 `pcTypeArgs` 버퍼를 할당하고 `cTypeArgs`를 더 큰 새 크기로 업데이트한 다음 `GetFunctionInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-132">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="2f7c3-133">또는 길이가 0인 `pcTypeArgs` 버퍼로 `GetFunctionInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-133">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2f7c3-134">그런 다음 버퍼 크기를 `pcTypeArgs`에서 반환된 값을 `ClassID` 값의 크기로 나눈 값으로 설정하고 `GetFunctionInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-134">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f7c3-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f7c3-135">Requirements</span></span>  

 <span data-ttu-id="2f7c3-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f7c3-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f7c3-137">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f7c3-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f7c3-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f7c3-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f7c3-139">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f7c3-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7c3-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f7c3-140">See also</span></span>

- [<span data-ttu-id="2f7c3-141">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f7c3-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2f7c3-142">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f7c3-142">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="2f7c3-143">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f7c3-143">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2f7c3-144">프로파일링</span><span class="sxs-lookup"><span data-stu-id="2f7c3-144">Profiling</span></span>](index.md)
