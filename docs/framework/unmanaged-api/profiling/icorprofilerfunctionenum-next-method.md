---
description: '자세히 알아보기: ICorProfilerFunctionEnum:: Next 메서드'
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
ms.openlocfilehash: ff525cfa4cc1ea1dee63b8bbd2e37eaf89fc3e74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737521"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="c5854-103">ICorProfilerFunctionEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="c5854-103">ICorProfilerFunctionEnum::Next Method</span></span>

<span data-ttu-id="c5854-104">시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 함수 컬렉션에서 지정된 개수의 연속 함수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-104">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5854-105">구문</span><span class="sxs-lookup"><span data-stu-id="c5854-105">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5854-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5854-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c5854-107">[in] 검색할 함수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-107">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="c5854-108">[out] 각각 검색된 함수를 나타내는 `COR_PRF_FUNCTION` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-108">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c5854-109">[out] `ids` 배열에 실제로 반환된 함수 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-109">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5854-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="c5854-110">Return Value</span></span>  

 <span data-ttu-id="c5854-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c5854-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5854-112">HRESULT</span></span>|<span data-ttu-id="c5854-113">설명</span><span class="sxs-lookup"><span data-stu-id="c5854-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5854-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5854-114">S_OK</span></span>|<span data-ttu-id="c5854-115">`celt` 요소가 반환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-115">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="c5854-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c5854-116">S_FALSE</span></span>|<span data-ttu-id="c5854-117">`celt`개 미만의 요소가 반환되었으며 이는 열거형이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5854-117">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5854-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5854-118">Requirements</span></span>  

 <span data-ttu-id="c5854-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5854-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5854-120">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5854-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5854-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5854-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5854-122">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5854-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5854-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5854-123">See also</span></span>

- [<span data-ttu-id="c5854-124">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5854-124">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="c5854-125">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5854-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
