---
title: ICorProfilerFunctionEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
ms.openlocfilehash: 76e0fe011769217f3cecb40c8d2ba83904b26706
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669232"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="70ec5-102">ICorProfilerFunctionEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="70ec5-102">ICorProfilerFunctionEnum::Next Method</span></span>

<span data-ttu-id="70ec5-103">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 함수 컬렉션에서 지정된 개수의 연속 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ec5-104">구문</span><span class="sxs-lookup"><span data-stu-id="70ec5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70ec5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70ec5-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="70ec5-106">[in] 검색할 함수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="70ec5-107">[out] 각각 검색된 함수를 나타내는 `COR_PRF_FUNCTION` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="70ec5-108">[out] `ids` 배열에 실제로 반환된 함수 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70ec5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="70ec5-109">Return Value</span></span>  

 <span data-ttu-id="70ec5-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="70ec5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70ec5-111">HRESULT</span></span>|<span data-ttu-id="70ec5-112">설명</span><span class="sxs-lookup"><span data-stu-id="70ec5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70ec5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="70ec5-113">S_OK</span></span>|<span data-ttu-id="70ec5-114">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="70ec5-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="70ec5-115">S_FALSE</span></span>|<span data-ttu-id="70ec5-116">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70ec5-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70ec5-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70ec5-117">Requirements</span></span>  

 <span data-ttu-id="70ec5-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ec5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70ec5-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70ec5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70ec5-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70ec5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70ec5-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70ec5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ec5-122">참조</span><span class="sxs-lookup"><span data-stu-id="70ec5-122">See also</span></span>

- [<span data-ttu-id="70ec5-123">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70ec5-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="70ec5-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="70ec5-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
