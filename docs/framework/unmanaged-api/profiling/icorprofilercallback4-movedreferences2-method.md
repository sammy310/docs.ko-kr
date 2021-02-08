---
description: '자세히 알아보기: ICorProfilerCallback4:: MovedReferences2 메서드'
title: ICorProfilerCallback4::MovedReferences2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 37bd1c91866a583bf4ba04e3e532d0efe5a11fc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788737"
---
# <a name="icorprofilercallback4movedreferences2-method"></a>ICorProfilerCallback4::MovedReferences2 메서드

압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고하려고 호출됩니다. 프로파일러에서 [ICorProfilerCallback4](icorprofilercallback4-interface.md) 인터페이스를 구현 하는 경우이 메서드가 호출 됩니다. 이 콜백은 [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) 메서드를 대체 합니다 .이 메서드는 길이가 ULONG에서 표현할 수 있는 값을 초과 하는 더 큰 개체 범위를 보고할 수 있기 때문입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>매개 변수  

 `cMovedObjectIDRanges`  
 [in] 압축 가비지 컬렉션 후에 이동된 연속 개체 블록 수입니다. 즉, `cMovedObjectIDRanges` 값은 `oldObjectIDRangeStart`, `newObjectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 총 크기입니다.  
  
 `MovedReferences2`의 다음 세 인수는 병렬 배열입니다. 즉, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` 및 `cObjectIDRangeLength[i]`는 모두 단일 연속 개체 블록과 관련이 있습니다.  
  
 `oldObjectIDRangeStart`  
 [in] 메모리에서 연속 라이브 개체 블록의 이전(가비지 수집 전) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.  
  
 `newObjectIDRangeStart`  
 [in] 메모리에서 연속 라이브 개체 블록의 새(가비지 컬렉션 후) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.  
  
 `cObjectIDRangeLength`  
 [in] 메모리의 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.  
  
 크기는 `oldObjectIDRangeStart` 및 `newObjectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.  
  
## <a name="remarks"></a>설명  

 압축 가비지 수집기는 데드 개체가 사용한 메모리를 회수하고 확보된 공간을 압축합니다. 따라서 라이브 개체가 힙 내에서 이동될 수 있고 이전 알림으로 분산된 `ObjectID` 값이 변경될 수 있습니다.  
  
 기존 `ObjectID` 값(`oldObjectID`)이 다음 범위 내에 있다고 가정합니다.  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 이 경우 범위 시작부터 개체 시작까지 오프셋은 다음과 같습니다.  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 다음 범위에 있는 `i` 값에 대해  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 새 `ObjectID`를 다음과 같이 계산할 수 있습니다.  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + ( `oldObjectID` – `oldObjectIDRangeStart[i]` )  
  
 콜백 자체가 진행되는 동안 `MovedReferences2`를 통해 전달된 `ObjectID` 값은 유효하지 않습니다. 가비지 수집기가 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다. 그러므로 프로파일러는 `MovedReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다. [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback은 모든 개체가 새 위치로 이동 되었으며 검사를 수행할 수 있음을 나타냅니다.  
  
 프로파일러가 [ICorProfilerCallback](icorprofilercallback-interface.md) 및 [ICorProfilerCallback4](icorprofilercallback4-interface.md) 인터페이스를 둘 다 구현 하는 경우 메서드가 `MovedReferences2` [ICorProfilerCallback:: movedreferences](icorprofilercallback-movedreferences-method.md) 메서드 앞에 호출 되지만 `MovedReferences2` 메서드가 성공적으로 반환 되는 경우에만 메서드가 호출 됩니다. 프로파일러는 두 번째 메서드 호출을 방지하기 위해 `MovedReferences2` 메서드에서 실패를 나타내는 HRESULT를 반환할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [MovedReferences 메서드](icorprofilercallback-movedreferences-method.md)
- [ICorProfilerCallback4 인터페이스](icorprofilercallback4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
