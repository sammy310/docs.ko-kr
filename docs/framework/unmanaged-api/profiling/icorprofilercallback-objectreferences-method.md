---
description: '자세히 알아보기: ICorProfilerCallback:: ObjectReferences 메서드'
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
ms.openlocfilehash: 55ea6fae87ecb6534af322fc9d5055c8a247f37a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745114"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="a0784-103">ICorProfilerCallback::ObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="a0784-103">ICorProfilerCallback::ObjectReferences Method</span></span>

<span data-ttu-id="a0784-104">지정 된 개체에서 참조 되는 메모리의 개체에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-104">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0784-105">구문</span><span class="sxs-lookup"><span data-stu-id="a0784-105">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0784-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0784-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="a0784-107">진행 개체를 참조 하는 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-107">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="a0784-108">진행 지정 된 개체가 인스턴스인 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-108">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="a0784-109">진행 지정 된 개체에서 참조 하는 개체의 수입니다 (배열의 요소 수 `objectRefIds` ).</span><span class="sxs-lookup"><span data-stu-id="a0784-109">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="a0784-110">진행 에서 참조 하는 개체의 Id 배열입니다 `objectId` .</span><span class="sxs-lookup"><span data-stu-id="a0784-110">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0784-111">설명</span><span class="sxs-lookup"><span data-stu-id="a0784-111">Remarks</span></span>  

 <span data-ttu-id="a0784-112">`ObjectReferences`가비지 수집이 완료 된 후 힙에 남아 있는 각 개체에 대해 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-112">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="a0784-113">프로파일러가이 콜백에서 오류를 반환 하는 경우 프로 파일링 서비스는 다음 가비지 수집이 끝날 때까지이 콜백 호출을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-113">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="a0784-114">`ObjectReferences`콜백은 [ICorProfilerCallback:: rootreferences](icorprofilercallback-rootreferences-method.md) 콜백과 함께 사용 하 여 런타임에 대 한 전체 개체 참조 그래프를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-114">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="a0784-115">CLR (공용 언어 런타임)은 각 개체 참조가 메서드에 의해 한 번만 보고 되도록 합니다 `ObjectReferences` .</span><span class="sxs-lookup"><span data-stu-id="a0784-115">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="a0784-116">가비지 컬렉션이 개체를 이동 하는 중일 수 있기 때문에에서 반환 하는 개체 Id는 `ObjectReferences` 콜백 자체에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-116">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="a0784-117">따라서 프로파일러는 호출 하는 동안 개체 검사를 시도 하지 않아야 합니다 `ObjectReferences` .</span><span class="sxs-lookup"><span data-stu-id="a0784-117">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="a0784-118">[ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-118">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="a0784-119">Null은에 `ClassId` `objectId` 언로드되고 있는 형식이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0784-119">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0784-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0784-120">Requirements</span></span>  

 <span data-ttu-id="a0784-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0784-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0784-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0784-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0784-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0784-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0784-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0784-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0784-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0784-125">See also</span></span>

- [<span data-ttu-id="a0784-126">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0784-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
