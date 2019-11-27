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
ms.openlocfilehash: 4f8cfd912a3d6f66f5f2586a8942c7ce9bd52a63
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445893"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="3c40d-102">ICorProfilerCallback::ObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3c40d-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="3c40d-103">지정 된 개체에서 참조 되는 메모리의 개체에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c40d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c40d-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c40d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c40d-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="3c40d-106">진행 개체를 참조 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="3c40d-107">진행 지정 된 개체가 인스턴스인 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="3c40d-108">진행 지정 된 개체에서 참조 하는 개체 수 (`objectRefIds` 배열의 요소 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="3c40d-109">진행 `objectId`에서 참조 하는 개체의 Id 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c40d-110">설명</span><span class="sxs-lookup"><span data-stu-id="3c40d-110">Remarks</span></span>  
 <span data-ttu-id="3c40d-111">`ObjectReferences` 메서드는 가비지 수집이 완료 된 후 힙에 남아 있는 각 개체에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="3c40d-112">프로파일러가이 콜백에서 오류를 반환 하는 경우 프로 파일링 서비스는 다음 가비지 수집이 끝날 때까지이 콜백 호출을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="3c40d-113">[ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 콜백과 함께 `ObjectReferences` 콜백을 사용 하 여 런타임에 대 한 전체 개체 참조 그래프를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="3c40d-114">CLR (공용 언어 런타임)은 각 개체 참조가 `ObjectReferences` 메서드에서 한 번만 보고 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="3c40d-115">가비지 컬렉션이 개체를 이동 하는 중일 수 있기 때문에 `ObjectReferences`에 의해 반환 되는 개체 Id는 콜백 자체에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="3c40d-116">따라서 프로파일러는 `ObjectReferences` 호출 중에 개체 검사를 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="3c40d-117">[ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="3c40d-118">Null `ClassId`은 `objectId`의 형식이 언로드되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c40d-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c40d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c40d-119">Requirements</span></span>  
 <span data-ttu-id="3c40d-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c40d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c40d-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c40d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c40d-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c40d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c40d-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c40d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c40d-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c40d-124">See also</span></span>

- [<span data-ttu-id="3c40d-125">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c40d-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
