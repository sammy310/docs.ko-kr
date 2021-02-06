---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_HIGH_MONITOR'
title: COR_PRF_HIGH_MONITOR 열거형
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 800bad21af96d8bbdf73f2af799f474f11294705
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648768"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="1a350-103">COR_PRF_HIGH_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="1a350-103">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="1a350-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="1a350-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="1a350-105">프로파일러에서 로드할 때 [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드에 지정할 수 있는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형에 있는 플래그 외에도 플래그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-105">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a350-106">구문</span><span class="sxs-lookup"><span data-stu-id="1a350-106">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="1a350-107">구성원</span><span class="sxs-lookup"><span data-stu-id="1a350-107">Members</span></span>  
  
|<span data-ttu-id="1a350-108">멤버</span><span class="sxs-lookup"><span data-stu-id="1a350-108">Member</span></span>|<span data-ttu-id="1a350-109">설명</span><span class="sxs-lookup"><span data-stu-id="1a350-109">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="1a350-110">플래그가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-110">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="1a350-111">CLR 어셈블리 참조 클로저 연습 중에 어셈블리 참조를 추가 하기 위한 [ICorProfilerCallback6:: GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-111">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="1a350-112">메모리 내 모듈과 연결 된 기호 스트림에 대 한 업데이트에 대 한 [ICorProfilerCallback7:: Moduleinmemorysymbol](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) 을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-112">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="1a350-113">동적 메서드를 가비지 수집 및 언로드할 때를 나타내는 [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) 콜백을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-113">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="1a350-114">.NET Core 3.0 이상 버전에만 해당: 프로파일러에 대해 [계층화 된 컴파일을](../../../core/whats-new/dotnet-core-3-0.md) 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-114">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="1a350-115">.NET Core 3.0 이상 버전에만 해당:와 비교할 수 있는 간단한 GC 프로 파일링 옵션을 제공 [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-115">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="1a350-116">[GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)및 [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) 콜백만 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-116">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="1a350-117">플래그와 달리는 `COR_PRF_MONITOR_GC` `COR_PRF_HIGH_BASIC_GC` 동시 가비지 수집을 사용 하지 않도록 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-117">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="1a350-118">.NET Core 3.0 이상 버전에만 해당: [Movedreferences](icorprofilercallback-movedreferences-method.md) 및 [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) 콜백을 사용 하 여 gc를 압축 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-118">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="1a350-119">.NET Core 3.0 이상 버전에만 해당:와 비슷하지만 [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md) LOH (large object heap)의 개체 할당에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-119">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="1a350-120">프로필 향상 이미지가 필요한 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-120">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="1a350-121">`COR_PRF_REQUIRE_PROFILE_IMAGE` [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 플래그에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-121">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="1a350-122">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="1a350-123">초기화 중에만 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-123">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="1a350-124">다른 위치에서 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-124">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a350-125">설명</span><span class="sxs-lookup"><span data-stu-id="1a350-125">Remarks</span></span>

<span data-ttu-id="1a350-126">`COR_PRF_HIGH_MONITOR`플래그는 `pdwEventsHigh` [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) 및 [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드의 매개 변수와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-126">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="1a350-127">.NET Framework 4.6.1 부터는의 값이 `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` 0에서 (0x00000002)로 변경 되었습니다 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` .</span><span class="sxs-lookup"><span data-stu-id="1a350-127">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="1a350-128">.NET Framework 4.7.2부터 값이에서로 변경 되었습니다 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS` .</span><span class="sxs-lookup"><span data-stu-id="1a350-128">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="1a350-129">`COR_PRF_HIGH_MONITOR_IMMUTABLE` 는 초기화 중에만 설정할 수 있는 모든 플래그를 나타내는 비트 마스크로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-129">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="1a350-130">다른 곳에서 이러한 플래그를 변경 하려고 하면 오류가 발생 `HRESULT` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a350-130">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1a350-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a350-131">Requirements</span></span>

<span data-ttu-id="1a350-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a350-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="1a350-133">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a350-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="1a350-134">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a350-134">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="1a350-135">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a350-135">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a350-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a350-136">See also</span></span>

- [<span data-ttu-id="1a350-137">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="1a350-137">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="1a350-138">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="1a350-138">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="1a350-139">ICorProfilerInfo5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a350-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
