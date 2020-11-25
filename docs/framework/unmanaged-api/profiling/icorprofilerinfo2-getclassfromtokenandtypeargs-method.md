---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 62aad8339b34a4831211a45bd645906d73393d25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727148"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="b0c70-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드</span><span class="sxs-lookup"><span data-stu-id="b0c70-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>

<span data-ttu-id="b0c70-103">지정 된 `ClassID` 메타 데이터 토큰 및 `ClassID` 모든 형식 인수 값을 사용 하 여 형식의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c70-104">구문</span><span class="sxs-lookup"><span data-stu-id="b0c70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0c70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b0c70-105">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="b0c70-106">진행 형식이 있는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="b0c70-107">진행 `mdTypeDef` 형식을 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="b0c70-108">진행 지정 된 형식에 대 한 형식 매개 변수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="b0c70-109">제네릭이 아닌 형식에 대해서는이 값이 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="b0c70-110">진행 `ClassID` 각각 형식의 인수인 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="b0c70-111">`typeArgs`가 0으로 설정 된 경우 값은 NULL 일 수 있습니다 `cTypeArgs` .</span><span class="sxs-lookup"><span data-stu-id="b0c70-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="b0c70-112">제한이 지정 된 형식의에 대 한 포인터 `ClassID` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0c70-113">설명</span><span class="sxs-lookup"><span data-stu-id="b0c70-113">Remarks</span></span>  

 <span data-ttu-id="b0c70-114">`GetClassFromTokenAndTypeArgs`메타 데이터 토큰 대신를 사용 하 여 메서드를 호출 하면 `mdTypeRef` `mdTypeDef` 예기치 않은 결과가 발생할 수 있습니다 `mdTypeRef` . 호출자는 `mdTypeDef` 전달 될 때를로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="b0c70-115">형식이 아직 로드 되지 않은 경우를 호출 하면 `GetClassFromTokenAndTypeArgs` 많은 컨텍스트에서 위험한 작업 인 로드를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="b0c70-116">예를 들어 모듈이 나 기타 형식을 로드 하는 동안이 메서드를 호출 하면 런타임에서 순환적으로 자신 로드를 시도 하는 경우 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="b0c70-117">일반적으로는 사용 하지 `GetClassFromTokenAndTypeArgs` 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c70-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="b0c70-118">프로파일러가 특정 형식에 대 한 이벤트에 관심이 있는 경우 해당 형식의 및를 저장 하 `ModuleID` `mdTypeDef` 고, [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) 를 사용 하 여 지정 된가 원하는 형식의 인지 여부를 확인 해야 합니다 `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="b0c70-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0c70-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b0c70-119">Requirements</span></span>  

 <span data-ttu-id="b0c70-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c70-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c70-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0c70-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0c70-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0c70-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0c70-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c70-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c70-124">참조</span><span class="sxs-lookup"><span data-stu-id="b0c70-124">See also</span></span>

- [<span data-ttu-id="b0c70-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0c70-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b0c70-126">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0c70-126">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
