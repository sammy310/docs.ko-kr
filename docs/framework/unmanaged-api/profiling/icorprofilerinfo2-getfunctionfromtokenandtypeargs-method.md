---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31fad9e82d0b93360f92676f6357c136ae60634a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771123"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="b33a8-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드</span><span class="sxs-lookup"><span data-stu-id="b33a8-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="b33a8-103">가져옵니다 합니다 `FunctionID` 클래스를 포함 하는 지정 된 메타 데이터 토큰을 사용 하 여 함수 및 `ClassID` 값의 형식 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="b33a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b33a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b33a8-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b33a8-106">[in] 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="b33a8-107">[in] `mdMethodDef` 함수를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="b33a8-108">[in] 함수의 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="b33a8-109">[in] 지정된 된 함수에 대 한 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="b33a8-110">이 값에는 제네릭이 아닌 함수에 대 한 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="b33a8-111">[in] 배열을 `ClassID` 각각는 함수의 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="b33a8-112">변수의 `typeArgs` NULL 일 수 `cTypeArgs` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="b33a8-113">[out] 에 대 한 포인터를 `FunctionID` 지정 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b33a8-114">설명</span><span class="sxs-lookup"><span data-stu-id="b33a8-114">Remarks</span></span>  
 <span data-ttu-id="b33a8-115">호출 된 `GetFunctionFromTokenAndTypeArgs` 메서드는 `mdMethodRef` 대신 메타 데이터는 `mdMethodDef` 메타 데이터 토큰에 예기치 않은 결과가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="b33a8-116">호출자가 해결 해야 합니다 `mdMethodRef` 에 `mdMethodDef` 전달 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="b33a8-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="b33a8-117">함수가 이미 로드 되어 있지 않으면 호출 `GetFunctionFromTokenAndTypeArgs` 발생 하는 여러 상황에서 위험한 작업 인 로드 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="b33a8-118">예를 들어 모듈이 나 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에 순환 로드를 시도할 때 무한 루프 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="b33a8-119">일반적으로 사용 `GetFunctionFromTokenAndTypeArgs` 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="b33a8-120">저장 해야 프로파일러 특정 함수에 대 한 이벤트에 관심이 있는 경우는 `ModuleID` 및 `mdMethodDef` 사용 하 여 해당 함수 [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 검사할 여부를 지정 된 `FunctionID` 는 원하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b33a8-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b33a8-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b33a8-121">Requirements</span></span>  
 <span data-ttu-id="b33a8-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b33a8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b33a8-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b33a8-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b33a8-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b33a8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b33a8-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b33a8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b33a8-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b33a8-126">See also</span></span>

- [<span data-ttu-id="b33a8-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b33a8-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b33a8-128">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b33a8-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
