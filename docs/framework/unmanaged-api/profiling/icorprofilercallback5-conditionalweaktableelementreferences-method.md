---
description: '자세히 알아보기: ICorProfilerCallback5:: ConditionalWeakTableElementReferences 메서드'
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
ms.openlocfilehash: ded43da029fe0b4c2a645823e62ca66b480f095c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760277"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a><span data-ttu-id="6d6bc-103">ICorProfilerCallback5::ConditionalWeakTableElementReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="6d6bc-103">ICorProfilerCallback5::ConditionalWeakTableElementReferences Method</span></span>

<span data-ttu-id="6d6bc-104">직접 멤버 필드 참조와 `ConditionalWeakTable` 종속성을 모두 사용하여 루트를 통해 참조되는 개체의 전이적 Closure를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-104">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>

## <a name="syntax"></a><span data-ttu-id="6d6bc-105">구문</span><span class="sxs-lookup"><span data-stu-id="6d6bc-105">Syntax</span></span>

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a><span data-ttu-id="6d6bc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d6bc-106">Parameters</span></span>

<span data-ttu-id="6d6bc-107">`cRootRefs` 진행 `keyRefIds`, `valueRefIds` 및 배열의 요소 수 `rootIds` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-107">`cRootRefs` [in] The number of elements in the `keyRefIds`, `valueRefIds`, and `rootIds` arrays.</span></span>

<span data-ttu-id="6d6bc-108">`keyRefIds` 진행 각각 `ObjectID` 종속 핸들 쌍의 기본 요소에 대 한를 포함 하는 개체 id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-108">`keyRefIds` [in] An array of object IDs, each of which contains the `ObjectID` for the primary element in the dependent handle pair.</span></span>

<span data-ttu-id="6d6bc-109">`valueRefIds` 진행 각각 `ObjectID` 종속 핸들 쌍의 보조 요소에 대 한를 포함 하는 개체 id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-109">`valueRefIds` [in] An array of object IDs, each of which contains the `ObjectID` for the secondary element in the dependent handle pair.</span></span> <span data-ttu-id="6d6bc-110">( `keyRefIds[i]` `valueRefIds[i]` 활성 상태를 유지 합니다.)</span><span class="sxs-lookup"><span data-stu-id="6d6bc-110">(`keyRefIds[i]` keeps `valueRefIds[i]` alive.)</span></span>

<span data-ttu-id="6d6bc-111">`rootIds` 진행 `GCHandleID` 가비지 컬렉션 루트에 대 한 추가 정보를 포함 하는 정수를 가리키는 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-111">`rootIds` [in] An array of `GCHandleID` values that point to an integer that contains additional information about the garbage collection root.</span></span>

<span data-ttu-id="6d6bc-112">콜백 자체가 진행되는 동안 `ObjectID` 메서드에서 반환되는 `ConditionalWeakTableElementReferences` 값은 유효하지 않습니다. 가비지 수집기가 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-112">None of the `ObjectID` values returned by the `ConditionalWeakTableElementReferences` method are valid during the callback itself, because the garbage collector may be in the process of moving objects from old to new locations.</span></span> <span data-ttu-id="6d6bc-113">그러므로 프로파일러는 `ConditionalWeakTableElementReferences` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-113">Therefore, profilers should not attempt to inspect objects during a `ConditionalWeakTableElementReferences` call.</span></span> <span data-ttu-id="6d6bc-114">`GarbageCollectionFinished` 시에는 모든 개체가 새 위치로 이동했으므로 검사를 수행해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-114">At `GarbageCollectionFinished`, all objects have been moved to their new locations, and inspection may be done.</span></span>

## <a name="example"></a><span data-ttu-id="6d6bc-115">예제</span><span class="sxs-lookup"><span data-stu-id="6d6bc-115">Example</span></span>

<span data-ttu-id="6d6bc-116">다음 코드 예제에서는 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 을 구현 하 고이 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-116">The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.</span></span>

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a><span data-ttu-id="6d6bc-117">설명</span><span class="sxs-lookup"><span data-stu-id="6d6bc-117">Remarks</span></span>

<span data-ttu-id="6d6bc-118">.NET Framework 4.5 이상 버전에 대 한 프로파일러는 [ICorProfilerCallback5](icorprofilercallback5-interface.md) 인터페이스를 구현 하 고 메서드로 지정 된 종속성을 기록 합니다 `ConditionalWeakTableElementReferences` .</span><span class="sxs-lookup"><span data-stu-id="6d6bc-118">A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method.</span></span> <span data-ttu-id="6d6bc-119">`ICorProfilerCallback5` 항목이 나타내는 라이브 개체 간의 전체 종속성 집합을 제공 합니다 `ConditionalWeakTable` .</span><span class="sxs-lookup"><span data-stu-id="6d6bc-119">`ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries.</span></span> <span data-ttu-id="6d6bc-120">이러한 종속성 및 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) 메서드로 지정 된 멤버 필드 참조를 사용 하면 관리 되는 프로파일러가 라이브 개체의 전체 개체 그래프를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-120">These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d6bc-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d6bc-121">Requirements</span></span>

<span data-ttu-id="6d6bc-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d6bc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6d6bc-123">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d6bc-123">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6d6bc-124">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6bc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6d6bc-125">참조</span><span class="sxs-lookup"><span data-stu-id="6d6bc-125">See also</span></span>

- [<span data-ttu-id="6d6bc-126">ICorProfilerCallback5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d6bc-126">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)
