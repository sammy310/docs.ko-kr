---
title: COR_PRF_HIGH_MONITOR 열거형
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175215"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="a74d8-102">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="a74d8-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="a74d8-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="a74d8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="a74d8-104">프로파일러가 로드할 때 [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드에 지정할 수 있는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 있는 플래그 외에 플래그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a74d8-105">구문</span><span class="sxs-lookup"><span data-stu-id="a74d8-105">Syntax</span></span>  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED |
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="a74d8-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a74d8-106">Members</span></span>  
  
|<span data-ttu-id="a74d8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a74d8-107">Member</span></span>|<span data-ttu-id="a74d8-108">Description</span><span class="sxs-lookup"><span data-stu-id="a74d8-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="a74d8-109">플래그가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="a74d8-110">CLR 어셈블리 참조 클로지 워크 중에 어셈블리 참조를 추가하기 위한 [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) 콜백을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="a74d8-111">[ICorProfilerCallback7::ModuleInMemorySymbols](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) 메모리 내 모듈과 연결된 심볼 스트림에 대한 업데이트 콜백을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="a74d8-112">동적 메서드가 가비지 수집 및 언로드된 시기를 나타내는 [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) 콜백을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="a74d8-113">.NET Core 3.0 이상 버전만: 프로파일러에 대해 [계층화 컴파일을](../../../core/whats-new/dotnet-core-3-0.md) 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="a74d8-114">.NET Core 3.0 이상 버전만: [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)에 비해 가벼운 GC 프로파일링 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="a74d8-115">[가비지컬렉션시작,](icorprofilercallback2-garbagecollectionstarted-method.md) [가비지컬렉션완료](icorprofilercallback2-garbagecollectionfinished-method.md)및 [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) 콜백만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="a74d8-116">플래그와 `COR_PRF_MONITOR_GC` 달리 `COR_PRF_HIGH_BASIC_GC` 동시 가비지 수집을 사용하지 않도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="a74d8-117">.NET Core 3.0 이상 버전만: [이동 참조](icorprofilercallback-movedreferences-method.md) 및 이동 [참조2](icorprofilercallback4-movedreferences2-method.md) 콜백을 사용하여 G를 압축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="a74d8-118">.NET Core 3.0 이상 버전만: [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)와 유사하지만 큰 개체 힙(LOH)에 대해서만 개체 할당에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="a74d8-119">프로필 향상 이미지가 필요한 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="a74d8-120">`COR_PRF_REQUIRE_PROFILE_IMAGE` [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 플래그에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="a74d8-121">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="a74d8-122">초기화 중에만 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="a74d8-123">다른 위치에서 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a74d8-124">설명</span><span class="sxs-lookup"><span data-stu-id="a74d8-124">Remarks</span></span>

<span data-ttu-id="a74d8-125">플래그는 `COR_PRF_HIGH_MONITOR` `pdwEventsHigh` [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 및 [ICorProfilerInfo5:SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드의 매개 변수와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="a74d8-126">.NET Framework 4.6.1부터 0에서 `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` 변경된 값(0x000000002)으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="a74d8-127">.NET Framework 4.7.2부터 시작하여 해당 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` 값이 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`에서 로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="a74d8-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE`는 초기화 중에만 설정할 수 있는 모든 플래그를 나타내는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="a74d8-129">다른 곳에서 이러한 플래그를 변경하려고 `HRESULT`하면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a74d8-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="a74d8-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a74d8-130">Requirements</span></span>

<span data-ttu-id="a74d8-131">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a74d8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="a74d8-132">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a74d8-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="a74d8-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a74d8-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="a74d8-134">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a74d8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74d8-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a74d8-135">See also</span></span>

- [<span data-ttu-id="a74d8-136">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a74d8-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="a74d8-137">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="a74d8-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="a74d8-138">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a74d8-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
