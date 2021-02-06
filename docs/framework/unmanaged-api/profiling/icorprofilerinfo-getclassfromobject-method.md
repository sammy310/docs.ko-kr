---
description: '자세히 알아보기: ICorProfilerInfo:: GetClassFromObject 메서드'
title: ICorProfilerInfo::GetClassFromObject 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 1c0224137c839d167263eefb17e3ae0b3ac29ef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647806"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="754ac-103">ICorProfilerInfo::GetClassFromObject 메서드</span><span class="sxs-lookup"><span data-stu-id="754ac-103">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="754ac-104">`ClassID`지정 된 개체의를 가져옵니다 `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="754ac-104">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754ac-105">구문</span><span class="sxs-lookup"><span data-stu-id="754ac-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="754ac-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="754ac-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="754ac-107">진행 를 가져올 개체의 ID입니다 `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="754ac-107">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="754ac-108">제한이 반환 된에 대 한 포인터 `ClassID` 입니다.</span><span class="sxs-lookup"><span data-stu-id="754ac-108">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="754ac-109">설명</span><span class="sxs-lookup"><span data-stu-id="754ac-109">Remarks</span></span>  

 <span data-ttu-id="754ac-110">Null은에 `pClassId` `objectId` 언로드되고 있는 형식이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="754ac-110">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754ac-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="754ac-111">Requirements</span></span>  

 <span data-ttu-id="754ac-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="754ac-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754ac-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="754ac-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="754ac-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="754ac-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="754ac-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754ac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754ac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="754ac-116">See also</span></span>

- [<span data-ttu-id="754ac-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="754ac-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
