---
title: ICorProfilerInfo2::GetObjectGeneration 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: 4ba404692bef84c0522a799c61f07eac341eaab4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703852"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="40f8c-102">ICorProfilerInfo2::GetObjectGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="40f8c-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>

<span data-ttu-id="40f8c-103">지정 된 개체를 포함 하는 힙의 세그먼트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="40f8c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40f8c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40f8c-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="40f8c-106">진행 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="40f8c-107">제한이 가비지 수집이 수행 되는 세대 내의 메모리 범위 (즉, 블록)를 설명 하는 [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="40f8c-108">이 범위에는 지정 된 개체가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40f8c-109">설명</span><span class="sxs-lookup"><span data-stu-id="40f8c-109">Remarks</span></span>  

 <span data-ttu-id="40f8c-110">`GetObjectGeneration`가비지 수집이 진행 되 고 있지 않은 경우 모든 프로파일러 콜백에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="40f8c-111">즉, [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) 및 [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)간에 발생 하는 것을 제외 하 고 모든 콜백에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40f8c-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f8c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40f8c-112">Requirements</span></span>  

 <span data-ttu-id="40f8c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40f8c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f8c-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40f8c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40f8c-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40f8c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40f8c-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f8c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f8c-117">참조</span><span class="sxs-lookup"><span data-stu-id="40f8c-117">See also</span></span>

- [<span data-ttu-id="40f8c-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40f8c-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="40f8c-119">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40f8c-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
