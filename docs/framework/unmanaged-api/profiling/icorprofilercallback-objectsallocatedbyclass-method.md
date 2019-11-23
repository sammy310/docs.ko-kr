---
title: ICorProfilerCallback::ObjectsAllocatedByClass 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445863"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="b481b-102">ICorProfilerCallback::ObjectsAllocatedByClass 메서드</span><span class="sxs-lookup"><span data-stu-id="b481b-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="b481b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b481b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b481b-104">구문</span><span class="sxs-lookup"><span data-stu-id="b481b-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b481b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b481b-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="b481b-106">[in] The size of the `classIds` and `cObjects` arrays.</span><span class="sxs-lookup"><span data-stu-id="b481b-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="b481b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span><span class="sxs-lookup"><span data-stu-id="b481b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="b481b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span><span class="sxs-lookup"><span data-stu-id="b481b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b481b-109">주의</span><span class="sxs-lookup"><span data-stu-id="b481b-109">Remarks</span></span>  
 <span data-ttu-id="b481b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span><span class="sxs-lookup"><span data-stu-id="b481b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="b481b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span><span class="sxs-lookup"><span data-stu-id="b481b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="b481b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span><span class="sxs-lookup"><span data-stu-id="b481b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="b481b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span><span class="sxs-lookup"><span data-stu-id="b481b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="b481b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span><span class="sxs-lookup"><span data-stu-id="b481b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="b481b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="b481b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="b481b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span><span class="sxs-lookup"><span data-stu-id="b481b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b481b-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b481b-117">Requirements</span></span>  
 <span data-ttu-id="b481b-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b481b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b481b-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b481b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b481b-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b481b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b481b-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b481b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b481b-122">참조</span><span class="sxs-lookup"><span data-stu-id="b481b-122">See also</span></span>

- [<span data-ttu-id="b481b-123">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b481b-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
