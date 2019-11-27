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
ms.openlocfilehash: 41021a524142afe34727584265aee578e31a64b3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433217"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="c2a2c-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드</span><span class="sxs-lookup"><span data-stu-id="c2a2c-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="c2a2c-103">지정 된 메타 데이터 토큰, 포함 하는 클래스 및 형식 인수의 `ClassID` 값을 사용 하 여 함수의 `FunctionID`를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2a2c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a2c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2a2c-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c2a2c-106">진행 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="c2a2c-107">진행 함수를 참조 하는 `mdMethodDef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="c2a2c-108">진행 함수를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c2a2c-109">진행 지정 된 함수에 대 한 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="c2a2c-110">제네릭이 아닌 함수의 경우이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c2a2c-111">진행 각각 함수의 인수인 `ClassID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="c2a2c-112">`cTypeArgs`가 0으로 설정 된 경우 `typeArgs`의 값은 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="c2a2c-113">제한이 지정 된 함수의 `FunctionID`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a2c-114">설명</span><span class="sxs-lookup"><span data-stu-id="c2a2c-114">Remarks</span></span>  
 <span data-ttu-id="c2a2c-115">`mdMethodDef` 메타 데이터 토큰 대신 `mdMethodRef` 메타 데이터를 사용 하 여 `GetFunctionFromTokenAndTypeArgs` 메서드를 호출 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="c2a2c-116">호출자는 `mdMethodRef`를 전달할 때 `mdMethodDef`를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="c2a2c-117">함수가 아직 로드 되지 않은 경우 `GetFunctionFromTokenAndTypeArgs`를 호출 하면 로드가 발생 하며이는 많은 컨텍스트에서 위험한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="c2a2c-118">예를 들어 모듈이 나 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에서 순환적으로 자신 로드를 시도 하는 경우 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="c2a2c-119">일반적으로 `GetFunctionFromTokenAndTypeArgs`는 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="c2a2c-120">프로파일러가 특정 함수에 대 한 이벤트에 관심이 있는 경우 해당 함수의 `ModuleID` 및 `mdMethodDef`을 저장 하 고, [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 를 사용 하 여 지정 된 `FunctionID`이 원하는 함수의 함수 인지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a2c-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2a2c-121">Requirements</span></span>  
 <span data-ttu-id="c2a2c-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a2c-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2a2c-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2a2c-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a2c-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a2c-125">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a2c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a2c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2a2c-126">See also</span></span>

- [<span data-ttu-id="c2a2c-127">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2a2c-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c2a2c-128">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2a2c-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
