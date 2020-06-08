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
ms.openlocfilehash: 2ce58113f40c8eb67a89b6ab6c9bb8f755975bd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499755"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="d2bb8-102">ICorProfilerCallback2::RootReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="d2bb8-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="d2bb8-103">가비지 수집이 발생 한 후 루트 참조에 대해 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="d2bb8-104">이 메서드는 [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 메서드를 확장 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-104">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bb8-105">구문</span><span class="sxs-lookup"><span data-stu-id="d2bb8-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2bb8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2bb8-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="d2bb8-107">진행 `rootRefIds`, `rootKinds` , `rootFlags` 및 배열의 요소 수 `rootIds` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="d2bb8-108">진행 각각 정적 개체 또는 스택의 개체를 참조 하는 개체 Id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="d2bb8-109">배열의 요소는 `rootKinds` 배열에서 해당 요소를 분류 하는 정보를 제공 `rootRefIds` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="d2bb8-110">진행 가비지 컬렉션 루트의 형식을 나타내는 [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-110">[in] An array of [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="d2bb8-111">진행 가비지 컬렉션 루트의 속성을 설명 하는 [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="d2bb8-112">진행 매개 변수의 값에 따라 가비지 컬렉션 루트에 대 한 추가 정보를 포함 하는 정수를 가리키는 UINT_PTR 값의 배열입니다 `rootKinds` .</span><span class="sxs-lookup"><span data-stu-id="d2bb8-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="d2bb8-113">루트의 형식이 스택이 면 해당 변수를 포함 하는 함수에 대 한 루트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="d2bb8-114">루트 ID가 0 이면 함수는 CLR의 내부에 있는 명명 되지 않은 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="d2bb8-115">루트의 형식이 핸들 인 경우 루트 ID는 가비지 수집 핸들의입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="d2bb8-116">다른 루트 형식의 경우 ID는 불투명 값 이므로 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2bb8-117">설명</span><span class="sxs-lookup"><span data-stu-id="d2bb8-117">Remarks</span></span>  
 <span data-ttu-id="d2bb8-118">`rootRefIds`,, `rootKinds` `rootFlags` 및 `rootIds` 배열은 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="d2bb8-119">즉,, `rootRefIds[i]` , `rootKinds[i]` `rootFlags[i]` 및는 `rootIds[i]` 모두 동일한 루트를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="d2bb8-120">`RootReferences`및 `RootReferences2` 는 모두 프로파일러에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="d2bb8-121">전달 된 정보는 `RootReferences2` 전달 되는의 상위 집합 이므로 프로파일러는 일반적으로 하나의 메서드 또는 다른 메서드를 구현 합니다 `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="d2bb8-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="d2bb8-122">의 항목이 0이 될 수 있습니다 `rootRefIds` .이는 해당 루트 참조가 null이 고 관리 되는 힙에서 개체를 참조 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="d2bb8-123">에서 반환 하는 개체 Id는 `RootReferences2` 가비지 컬렉션이 이전 주소에서 새 주소로 개체를 이동 하는 중일 수 있기 때문에 콜백 자체 중에는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="d2bb8-124">그러므로 프로파일러는 `RootReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="d2bb8-125">[ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 모든 개체가 새 위치로 이동 되었으며 안전 하 게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-125">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2bb8-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2bb8-126">Requirements</span></span>  
 <span data-ttu-id="d2bb8-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2bb8-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2bb8-128">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2bb8-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2bb8-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2bb8-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2bb8-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2bb8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bb8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2bb8-131">See also</span></span>

- [<span data-ttu-id="d2bb8-132">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2bb8-132">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d2bb8-133">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2bb8-133">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
