---
description: '자세히 알아보기: ICorProfilerInfo:: GetILToNativeMapping 메서드'
title: ICorProfilerInfo::GetILToNativeMapping 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: ce3473365eb98beca4d2e9116251200d7539e4c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647390"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="7be16-103">ICorProfilerInfo::GetILToNativeMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="7be16-103">ICorProfilerInfo::GetILToNativeMapping Method</span></span>

<span data-ttu-id="7be16-104">지정된 함수에 포함된 코드에 대한 MSIL(Microsoft Intermediate Language) 오프셋과 네이티브 오프셋 간의 맵을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-104">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be16-105">구문</span><span class="sxs-lookup"><span data-stu-id="7be16-105">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be16-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7be16-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="7be16-107">[in] 코드를 포함하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-107">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="7be16-108">[in] `map` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-108">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="7be16-109">[out] 사용 가능한 COR_DEBUG_IL_TO_NATIVE_MAP 구조체의 총수입니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-109">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="7be16-110">[out] 각각 오프셋을 지정하는 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-110">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="7be16-111">`GetILToNativeMapping` 메서드가 반환되면 `map`에 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체가 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-111">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be16-112">설명</span><span class="sxs-lookup"><span data-stu-id="7be16-112">Remarks</span></span>  

 <span data-ttu-id="7be16-113">`GetILToNativeMapping` 메서드는 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체의 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-113">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="7be16-114">특정 범위의 네이티브 지침이 프롤로그와 같은 특정 코드 영역에 해당 하는 것을 전달 하기 위해 배열의 항목은 해당 `ilOffset` 필드를 [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) 열거형의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-114">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="7be16-115">`GetILToNativeMapping`가 반환된 후 `map` 버퍼가 모든 `COR_DEBUG_IL_TO_NATIVE_MAP` 구조체를 포함하기에 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-115">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="7be16-116">이렇게 하려면 `cMap` 값을 `pcMap` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-116">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="7be16-117">`COR_DEBUG_IL_TO_NATIVE_MAP` 구조체의 크기를 곱한 `pcMap` 값이 `cMap`보다 크면 더 큰 `map` 버퍼를 할당하고 `cMap`를 더 큰 새 크기로 업데이트한 다음 `GetILToNativeMapping`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-117">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="7be16-118">또는 길이가 0인 `map` 버퍼로 `GetILToNativeMapping`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-118">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="7be16-119">그런 다음 버퍼 크기를 `pcMap`에 반환된 값으로 설정하고 `GetILToNativeMapping`을 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7be16-119">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be16-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7be16-120">Requirements</span></span>  

 <span data-ttu-id="7be16-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7be16-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be16-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7be16-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7be16-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be16-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be16-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be16-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be16-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7be16-125">See also</span></span>

- [<span data-ttu-id="7be16-126">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7be16-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7be16-127">GetILToNativeMapping2 메서드</span><span class="sxs-lookup"><span data-stu-id="7be16-127">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="7be16-128">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7be16-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7be16-129">프로파일링</span><span class="sxs-lookup"><span data-stu-id="7be16-129">Profiling</span></span>](index.md)
