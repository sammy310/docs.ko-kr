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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64e362be57a96bbe0f61b964ab413234f30d0ed1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143782"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="bad21-102">ICorProfilerInfo2::GetObjectGeneration 메서드</span><span class="sxs-lookup"><span data-stu-id="bad21-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="bad21-103">지정된 된 개체를 포함 하는 힙 세그먼트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad21-104">구문</span><span class="sxs-lookup"><span data-stu-id="bad21-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bad21-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="bad21-106">[in] 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="bad21-107">[out] 에 대 한 포인터를 [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) 가비지 컬렉션 중인 세대 내의 메모리 범위 (즉, 블록)를 설명 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="bad21-108">이 범위 지정된 된 개체를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad21-109">설명</span><span class="sxs-lookup"><span data-stu-id="bad21-109">Remarks</span></span>  
 <span data-ttu-id="bad21-110">`GetObjectGeneration` 가비지 수집이 진행에서 중이지 제공한 모든 프로파일러 콜백에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="bad21-111">즉, 간에 발생 하는 작업을 제외한 모든 콜백에서 호출할 수 있습니다 [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) 하 고 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bad21-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad21-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bad21-112">Requirements</span></span>  
 <span data-ttu-id="bad21-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bad21-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad21-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bad21-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bad21-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bad21-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bad21-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="bad21-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bad21-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="bad21-117">See also</span></span>

- [<span data-ttu-id="bad21-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad21-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="bad21-119">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bad21-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
