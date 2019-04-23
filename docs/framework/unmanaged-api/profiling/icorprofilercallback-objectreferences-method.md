---
title: ICorProfilerCallback::ObjectReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1142b33f029708d93cc3b808dc6be2b2df5b0ee3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119251"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="12491-102">ICorProfilerCallback::ObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="12491-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="12491-103">지정된 된 개체에서 참조 되지 않는 메모리에서 개체에 대 한 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="12491-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12491-104">구문</span><span class="sxs-lookup"><span data-stu-id="12491-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="12491-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12491-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="12491-106">[in] 개체를 참조 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="12491-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="12491-107">[in] 지정된 된 개체의 인스턴스가 있는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="12491-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="12491-108">[in] 지정된 된 개체에서 참조 하는 개체 수 (의 요소 수를 `objectRefIds` 배열)입니다.</span><span class="sxs-lookup"><span data-stu-id="12491-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="12491-109">[in] 참조 되지 않는 개체의 Id 배열을 `objectId`합니다.</span><span class="sxs-lookup"><span data-stu-id="12491-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12491-110">설명</span><span class="sxs-lookup"><span data-stu-id="12491-110">Remarks</span></span>  
 <span data-ttu-id="12491-111">`ObjectReferences` 힙에 남아 있는 가비지 수집이 완료 된 후 각 개체에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12491-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="12491-112">프로파일러가이 콜백에서 오류를 반환 하는 경우 다음 가비지 수집 될 때까지이 콜백을 호출 하면 프로 파일링 서비스는 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12491-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="12491-113">합니다 `ObjectReferences` 콜백와 함께에서 사용할 수는 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 런타임에 대 한 완전 한 개체 참조 그래프를 만들 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="12491-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="12491-114">CLR (공용 언어 런타임) 하면 각 개체 참조 하 여 한 번만 보고 되는 `ObjectReferences` 메서드.</span><span class="sxs-lookup"><span data-stu-id="12491-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="12491-115">개체 Id가 반환한 `ObjectReferences` 가비지 컬렉션 개체를 이동 하는 중일 수 있으므로 자체를 콜백 하는 동안 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12491-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="12491-116">따라서 프로파일러 시도 하지 않아야 하는 동안 개체 검사는 `ObjectReferences` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="12491-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="12491-117">때 [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 호출 되는 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12491-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="12491-118">Null `ClassId` 나타내는 `objectId` 형식이 언로드하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="12491-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12491-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12491-119">Requirements</span></span>  
 <span data-ttu-id="12491-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12491-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12491-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12491-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12491-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12491-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12491-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12491-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12491-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="12491-124">See also</span></span>

- [<span data-ttu-id="12491-125">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12491-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
