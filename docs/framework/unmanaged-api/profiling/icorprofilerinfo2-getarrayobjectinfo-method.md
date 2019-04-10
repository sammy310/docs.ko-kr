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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5276c69da05cedcd3195a09da12ddc5b2d0fed67
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201275"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="becb2-102">ICorProfilerInfo2::GetArrayObjectInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="becb2-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="becb2-103">배열 개체에 대 한 자세한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="becb2-104">구문</span><span class="sxs-lookup"><span data-stu-id="becb2-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="becb2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="becb2-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="becb2-106">[in] ID는 유효한 배열 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="becb2-107">[in] 배열의 순위 (차원의 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="becb2-108">[out] 각 배열 차원의 크기를 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="becb2-109">[out] 배열 차원의 바인딩된 아래쪽을 나타내는 각 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="becb2-110">[out] 에 따라 배치 되는 배열에 대해 원시 버퍼의 주소에 대 한 포인터를 C++ 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="becb2-111">설명</span><span class="sxs-lookup"><span data-stu-id="becb2-111">Remarks</span></span>  
 <span data-ttu-id="becb2-112">합니다 `pDimensionSizes` 고 `pDimensionLowerBounds` 병렬 배열 되므로 각 배열에 있는 동일한 인덱스에 있는 요소는 동일한 엔터티의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="becb2-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="becb2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="becb2-113">Requirements</span></span>  
 <span data-ttu-id="becb2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="becb2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="becb2-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="becb2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="becb2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="becb2-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="becb2-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="becb2-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="becb2-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="becb2-118">See also</span></span>

- [<span data-ttu-id="becb2-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="becb2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="becb2-120">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="becb2-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
