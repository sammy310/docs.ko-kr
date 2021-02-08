---
description: '자세히 알아보기: ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs 메서드'
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
ms.openlocfilehash: 4b4bb8631a5f33c939666af68226b19d2e4d666d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799037"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="e6e4e-103">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs 메서드</span><span class="sxs-lookup"><span data-stu-id="e6e4e-103">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="e6e4e-104">지정 된 `FunctionID` 메타 데이터 토큰, 클래스 포함, `ClassID` 모든 형식 인수 값을 사용 하 여 함수의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-104">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6e4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="e6e4e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6e4e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e6e4e-106">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="e6e4e-107">진행 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-107">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="e6e4e-108">진행 `mdMethodDef` 함수를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-108">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="e6e4e-109">진행 함수를 포함 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-109">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="e6e4e-110">진행 지정 된 함수에 대 한 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-110">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="e6e4e-111">제네릭이 아닌 함수의 경우이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-111">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="e6e4e-112">진행 `ClassID` 각각 함수의 인수인 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-112">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="e6e4e-113">`typeArgs`가 0으로 설정 된 경우 값은 NULL 일 수 있습니다 `cTypeArgs` .</span><span class="sxs-lookup"><span data-stu-id="e6e4e-113">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="e6e4e-114">제한이 지정 된 함수의에 대 한 포인터 `FunctionID` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-114">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6e4e-115">설명</span><span class="sxs-lookup"><span data-stu-id="e6e4e-115">Remarks</span></span>  

 <span data-ttu-id="e6e4e-116">`GetFunctionFromTokenAndTypeArgs`메타 데이터 토큰 대신 메타 데이터를 사용 하 여 메서드를 호출 `mdMethodRef` `mdMethodDef` 하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-116">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="e6e4e-117">호출자는를 `mdMethodRef` 전달할 때를로 확인 해야 합니다 `mdMethodDef` .</span><span class="sxs-lookup"><span data-stu-id="e6e4e-117">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="e6e4e-118">함수가 아직 로드 되지 않은 경우를 호출 하면 `GetFunctionFromTokenAndTypeArgs` 로드가 발생 하며,이는 많은 컨텍스트에서 위험한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-118">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="e6e4e-119">예를 들어 모듈이 나 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에서 순환적으로 자신 로드를 시도 하는 경우 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-119">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="e6e4e-120">일반적으로는 사용 하지 `GetFunctionFromTokenAndTypeArgs` 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-120">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="e6e4e-121">프로파일러가 특정 함수에 대 한 이벤트에 관심이 있는 경우 해당 함수의 및를 저장 하 `ModuleID` `mdMethodDef` 고 [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 를 사용 하 여 지정 된가 원하는 함수의 인지 여부를 확인 해야 합니다. `FunctionID`</span><span class="sxs-lookup"><span data-stu-id="e6e4e-121">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6e4e-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6e4e-122">Requirements</span></span>  

 <span data-ttu-id="e6e4e-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6e4e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6e4e-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6e4e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6e4e-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6e4e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6e4e-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e4e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e4e-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6e4e-127">See also</span></span>

- [<span data-ttu-id="e6e4e-128">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6e4e-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e6e4e-129">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6e4e-129">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
