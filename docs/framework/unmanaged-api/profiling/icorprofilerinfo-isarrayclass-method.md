---
description: '자세히 알아보기: ICorProfilerInfo:: IsArrayClass 메서드'
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
ms.openlocfilehash: 1eee0b834c63c3cfe15bd08776214ca8b2ba3f69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687235"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="3f486-103">ICorProfilerInfo::IsArrayClass 메서드</span><span class="sxs-lookup"><span data-stu-id="3f486-103">ICorProfilerInfo::IsArrayClass Method</span></span>

<span data-ttu-id="3f486-104">지정 된 클래스가 배열 클래스 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-104">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f486-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f486-105">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f486-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f486-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="3f486-107">진행 검사할 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-107">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="3f486-108">제한이 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-108">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="3f486-109">제한이 사용할 수 있는 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-109">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="3f486-110">제한이 배열의 차수 (차원 수)를 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-110">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f486-111">설명</span><span class="sxs-lookup"><span data-stu-id="3f486-111">Remarks</span></span>  

 <span data-ttu-id="3f486-112">지정 된 클래스가 배열 클래스인 경우 메서드는 null이 `IsArrayClass` 아닌 모든 출력 매개 변수에 대 한 S_OK HRESULT 및 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-112">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="3f486-113">그렇지 않으면 S_FALSE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f486-113">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f486-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f486-114">Requirements</span></span>  

 <span data-ttu-id="3f486-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f486-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f486-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f486-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f486-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f486-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f486-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f486-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f486-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f486-119">See also</span></span>

- [<span data-ttu-id="3f486-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f486-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
