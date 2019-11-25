---
title: COR_PRF_HIGH_MONITOR 열거형
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: fc0251624738a06d1be7081ebd099e97f7278a15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283134"
---
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR 열거형

[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
프로파일러가 로드될 때 [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 메서드에 대해 지정할 수 있는 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 열거형에 포함된 플래그 이외의 플래그를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|플래그가 설정되지 않았습니다.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|CLR 어셈블리 참조 closure 워커 중에 어셈블리 참조를 추가하기 위한 [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 콜백을 제어합니다.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|메모리 내 모듈과 연결 된 기호 스트림에 대 한 업데이트에 대 한 [ICorProfilerCallback7:: Moduleinmemorysymbol](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) 을 제어 합니다.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|동적 메서드를 가비지 수집 및 언로드할 때를 나타내는 [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) 콜백을 제어 합니다. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET Core 3.0 이상 버전에만 해당: 프로파일러에 대해 [계층화 된 컴파일을](../../../core/whats-new/dotnet-core-3-0.md) 사용 하지 않도록 설정 합니다.|
|`COR_PRF_HIGH_BASIC_GC`|.NET Core 3.0 이상 버전에만 해당: [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)에 비해 간단한 GC 프로 파일링 옵션을 제공 합니다. [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)및 [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) 콜백만 제어 합니다. `COR_PRF_MONITOR_GC` 플래그와 달리 `COR_PRF_HIGH_BASIC_GC`는 동시 가비지 수집을 사용 하지 않도록 설정 하지 않습니다.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET Core 3.0 이상 버전에만 해당: [Movedreferences](icorprofilercallback-movedreferences-method.md) 및 [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) 콜백을 사용 하 여 gc를 압축 합니다.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3.0 이상 버전에만 해당: [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)와 유사 하지만 LOH (large object heap)의 개체 할당에 대 한 정보를 제공 합니다.|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|프로필 향상 이미지가 필요한 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다. `COR_PRF_REQUIRE_PROFILE_IMAGE`COR_PRF_MONITOR[ 열거형의 ](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 플래그에 해당합니다.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|초기화 중에만 설정할 수 있는 모든 `COR_PRF_HIGH_MONITOR` 플래그를 나타냅니다. 다른 위치에서 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.|  
  
## <a name="remarks"></a>설명

`COR_PRF_HIGH_MONITOR` 플래그는`pdwEventsHigh`ICorProfilerInfo5::GetEventMask2[ 및 ](icorprofilerinfo5-geteventmask2-method.md)ICorProfilerInfo5::SetEventMask2[ 메서드의 ](icorprofilerinfo5-seteventmask2-method.md) 매개 변수와 함께 사용됩니다.  
  
.NET Framework 4.6.1부터 `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`의 값이 0에서 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002)로 변경 되었습니다. .NET Framework 4.7.2부터 해당 값이 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`에서 `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`로 변경 되었습니다.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE`는 초기화 중에만 설정할 수 있는 모든 플래그를 나타내는 비트 마스크로 사용 됩니다. 다른 곳에서 이러한 플래그를 변경 하려고 하면 `HRESULT`오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
**헤더:** CorProf.idl, CorProf.h  
  
**라이브러리:** CorGuids.lib  
  
**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [COR_PRF_MONITOR 열거형](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
