---
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
ms.openlocfilehash: 5a7edc6045969861679d1b80c0563e99f48932cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680250"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="e019a-102">ICorProfilerInfo::GetClassFromObject 메서드</span><span class="sxs-lookup"><span data-stu-id="e019a-102">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="e019a-103">`ClassID`지정 된 개체의를 가져옵니다 `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="e019a-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e019a-104">구문</span><span class="sxs-lookup"><span data-stu-id="e019a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e019a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e019a-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="e019a-106">진행 를 가져올 개체의 ID입니다 `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="e019a-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="e019a-107">제한이 반환 된에 대 한 포인터 `ClassID` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e019a-108">설명</span><span class="sxs-lookup"><span data-stu-id="e019a-108">Remarks</span></span>  

 <span data-ttu-id="e019a-109">Null은에 `pClassId` `objectId` 언로드되고 있는 형식이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e019a-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e019a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e019a-110">Requirements</span></span>  

 <span data-ttu-id="e019a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e019a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e019a-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e019a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e019a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e019a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e019a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e019a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e019a-115">참조</span><span class="sxs-lookup"><span data-stu-id="e019a-115">See also</span></span>

- [<span data-ttu-id="e019a-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e019a-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
