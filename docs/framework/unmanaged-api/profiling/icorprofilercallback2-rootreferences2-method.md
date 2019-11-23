---
title: ICorProfilerCallback2::RootReferences2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: dffd4365669da61f7b321110ad663c131ce591e6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439675"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="f129f-102">ICorProfilerCallback2::RootReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="f129f-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="f129f-103">Notifies the profiler about root references after a garbage collection has occurred.</span><span class="sxs-lookup"><span data-stu-id="f129f-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="f129f-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="f129f-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f129f-105">구문</span><span class="sxs-lookup"><span data-stu-id="f129f-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f129f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f129f-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="f129f-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span><span class="sxs-lookup"><span data-stu-id="f129f-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="f129f-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span><span class="sxs-lookup"><span data-stu-id="f129f-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="f129f-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span><span class="sxs-lookup"><span data-stu-id="f129f-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="f129f-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span><span class="sxs-lookup"><span data-stu-id="f129f-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="f129f-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span><span class="sxs-lookup"><span data-stu-id="f129f-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="f129f-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span><span class="sxs-lookup"><span data-stu-id="f129f-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="f129f-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span><span class="sxs-lookup"><span data-stu-id="f129f-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="f129f-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span><span class="sxs-lookup"><span data-stu-id="f129f-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="f129f-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span><span class="sxs-lookup"><span data-stu-id="f129f-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="f129f-116">For the other root types, the ID is an opaque value and should be ignored.</span><span class="sxs-lookup"><span data-stu-id="f129f-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f129f-117">주의</span><span class="sxs-lookup"><span data-stu-id="f129f-117">Remarks</span></span>  
 <span data-ttu-id="f129f-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span><span class="sxs-lookup"><span data-stu-id="f129f-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="f129f-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span><span class="sxs-lookup"><span data-stu-id="f129f-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="f129f-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span><span class="sxs-lookup"><span data-stu-id="f129f-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="f129f-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="f129f-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="f129f-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span><span class="sxs-lookup"><span data-stu-id="f129f-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="f129f-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span><span class="sxs-lookup"><span data-stu-id="f129f-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="f129f-124">그러므로 프로파일러는 `RootReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f129f-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="f129f-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span><span class="sxs-lookup"><span data-stu-id="f129f-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f129f-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f129f-126">Requirements</span></span>  
 <span data-ttu-id="f129f-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f129f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f129f-128">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f129f-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f129f-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f129f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f129f-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f129f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f129f-131">참조</span><span class="sxs-lookup"><span data-stu-id="f129f-131">See also</span></span>

- [<span data-ttu-id="f129f-132">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f129f-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f129f-133">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f129f-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
