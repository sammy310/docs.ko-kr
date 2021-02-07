---
description: '자세히 알아보기: ICorProfilerInfo2:: GetArrayObjectInfo 메서드'
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
ms.openlocfilehash: 1427ad696f73d90a2a07698c71456571fb14ee70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760539"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="23161-103">ICorProfilerInfo2::GetArrayObjectInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="23161-103">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>

<span data-ttu-id="23161-104">배열 개체에 대 한 자세한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23161-104">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23161-105">구문</span><span class="sxs-lookup"><span data-stu-id="23161-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23161-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23161-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="23161-107">진행 유효한 배열 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-107">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="23161-108">진행 배열의 순위 (차원의 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-108">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="23161-109">제한이 각각 배열의 차원 크기를 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-109">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="23161-110">제한이 각각 배열 차원의 하 한을 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-110">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="23161-111">제한이 C + + 규칙에 따라 배치 되는 배열에 대 한 원시 버퍼의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-111">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23161-112">설명</span><span class="sxs-lookup"><span data-stu-id="23161-112">Remarks</span></span>  

 <span data-ttu-id="23161-113">`pDimensionSizes`및은 `pDimensionLowerBounds` 병렬 배열 이므로 각 배열의 동일한 인덱스에 있는 요소는 동일한 엔터티의 특징입니다.</span><span class="sxs-lookup"><span data-stu-id="23161-113">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23161-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23161-114">Requirements</span></span>  

 <span data-ttu-id="23161-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23161-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23161-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23161-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23161-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23161-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23161-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23161-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23161-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23161-119">See also</span></span>

- [<span data-ttu-id="23161-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23161-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="23161-121">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23161-121">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
