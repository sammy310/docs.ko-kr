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
ms.openlocfilehash: 2608f91a7c5baa935e48fbe58ad4d14aaaad1f0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722507"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="ded05-102">ICorProfilerInfo::IsArrayClass 메서드</span><span class="sxs-lookup"><span data-stu-id="ded05-102">ICorProfilerInfo::IsArrayClass Method</span></span>

<span data-ttu-id="ded05-103">지정 된 클래스가 배열 클래스 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded05-104">구문</span><span class="sxs-lookup"><span data-stu-id="ded05-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ded05-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ded05-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="ded05-106">진행 검사할 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="ded05-107">제한이 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="ded05-108">제한이 사용할 수 있는 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="ded05-109">제한이 배열의 차수 (차원 수)를 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ded05-110">설명</span><span class="sxs-lookup"><span data-stu-id="ded05-110">Remarks</span></span>  

 <span data-ttu-id="ded05-111">지정 된 클래스가 배열 클래스인 경우 메서드는 null이 `IsArrayClass` 아닌 모든 출력 매개 변수에 대 한 S_OK HRESULT 및 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="ded05-112">그렇지 않으면 S_FALSE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded05-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ded05-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ded05-113">Requirements</span></span>  

 <span data-ttu-id="ded05-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ded05-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded05-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ded05-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ded05-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ded05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ded05-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded05-118">참조</span><span class="sxs-lookup"><span data-stu-id="ded05-118">See also</span></span>

- [<span data-ttu-id="ded05-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ded05-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
