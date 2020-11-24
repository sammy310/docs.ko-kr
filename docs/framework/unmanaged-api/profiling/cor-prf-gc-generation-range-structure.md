---
title: COR_PRF_GC_GENERATION_RANGE 구조체
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: a0ee2c9ce38272caef4960bfe5949c11083c12dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674933"
---
# <a name="cor_prf_gc_generation_range-structure"></a>COR_PRF_GC_GENERATION_RANGE 구조체

가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`generation`|메모리 블록이 속한 세대를 지정 하는 [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) 열거형의 값입니다.|  
|`rangeStart`|메모리 블록의 시작 위치를 지정 하는 개체의 ID입니다.|  
|`rangeLength`|메모리 블록에서 사용 되는 메모리의 양 (블록 내에 사용 되는 메모리 양)의 크기를 지정 하는 정수에 대 한 포인터입니다.|  
|`rangeLengthReserved`|메모리 블록의 크기를 지정 하는 정수에 대 한 포인터입니다. 즉, 블록에 예약 된 메모리의 양입니다.|  
  
## <a name="remarks"></a>설명  

 이 `rangeLength` 값은 구조체를 사용 하는 [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) 또는 [ICorProfilerInfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)모두 `COR_PRF_GC_GENERATION_RANGE` [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) 또는 [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 메서드에서 호출 되는 경우에만 정확 하 게 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 구조체](profiling-structures.md)
