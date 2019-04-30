---
title: ICorProfilerInfo::IsArrayClass 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 350221ae205636cef82581f3fe11367006dd8b2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968079"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="b32c3-102">ICorProfilerInfo::IsArrayClass 메서드</span><span class="sxs-lookup"><span data-stu-id="b32c3-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="b32c3-103">지정된 된 클래스 배열 클래스 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b32c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="b32c3-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b32c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b32c3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b32c3-106">[in] 검사할 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="b32c3-107">[out] 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="b32c3-108">[out] 사용 가능한 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="b32c3-109">[out] 배열의 순위 (차원의 수)를 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b32c3-110">설명</span><span class="sxs-lookup"><span data-stu-id="b32c3-110">Remarks</span></span>  
 <span data-ttu-id="b32c3-111">지정된 된 클래스는 배열 클래스 경우의 `IsArrayClass` 메서드는 S_OK HRESULT 및 null이 아닌 출력 매개 변수 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="b32c3-112">그렇지 않으면 S_FALSE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32c3-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b32c3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b32c3-113">Requirements</span></span>  
 <span data-ttu-id="b32c3-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b32c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b32c3-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b32c3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b32c3-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b32c3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b32c3-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b32c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b32c3-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b32c3-118">See also</span></span>

- [<span data-ttu-id="b32c3-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b32c3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
