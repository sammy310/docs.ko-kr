---
title: ICorProfilerInfo2::GetArrayObjectInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: a1e321e141059ccf1da7292d28e7099418a5134e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727200"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="1ab47-102">ICorProfilerInfo2::GetArrayObjectInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="1ab47-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>

<span data-ttu-id="1ab47-103">배열 개체에 대 한 자세한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab47-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ab47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab47-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ab47-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="1ab47-106">진행 유효한 배열 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="1ab47-107">진행 배열의 순위 (차원의 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="1ab47-108">제한이 각각 배열의 차원 크기를 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="1ab47-109">제한이 각각 배열 차원의 하 한을 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="1ab47-110">제한이 C + + 규칙에 따라 배치 되는 배열에 대 한 원시 버퍼의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab47-111">설명</span><span class="sxs-lookup"><span data-stu-id="1ab47-111">Remarks</span></span>  

 <span data-ttu-id="1ab47-112">`pDimensionSizes`및은 `pDimensionLowerBounds` 병렬 배열 이므로 각 배열의 동일한 인덱스에 있는 요소는 동일한 엔터티의 특징입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab47-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab47-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ab47-113">Requirements</span></span>  

 <span data-ttu-id="1ab47-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ab47-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab47-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ab47-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ab47-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ab47-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ab47-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab47-118">참조</span><span class="sxs-lookup"><span data-stu-id="1ab47-118">See also</span></span>

- [<span data-ttu-id="1ab47-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ab47-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1ab47-120">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ab47-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
