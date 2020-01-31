---
title: ICorProfilerCallback2::GarbageCollectionStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865781"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted 메서드
가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cGenerations`  
 진행 `generationCollected` 배열에 있는 총 항목 수입니다.  
  
 `generationCollected`  
 진행 이 가비지 컬렉션에서 배열 인덱스에 해당 하는 세대를 수집 하는 경우 `true` 되는 부울 값의 배열입니다. 그렇지 않으면 `false`합니다.  
  
 배열은 생성을 나타내는 [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) 열거형 값으로 인덱싱됩니다.  
  
 `reason`  
 진행 가비지 컬렉션이 발생 한 이유를 나타내는 [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>주의  
 이 가비지 컬렉션과 관련 된 모든 콜백은 `GarbageCollectionStarted` 콜백과 해당 [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback 사이에서 발생 합니다. 이러한 콜백은 동일한 스레드에서 발생 하지 않아도 됩니다.  
  
 프로파일러에서 `GarbageCollectionStarted` 콜백 중에 원래 위치에서 개체를 검사 하는 것이 안전 합니다. `GarbageCollectionStarted`반환한 후에 가비지 수집기가 개체 이동을 시작 합니다. 프로파일러가이 콜백에서 반환 된 후 프로파일러는 `ICorProfilerCallback2::GarbageCollectionFinished` 콜백을 받을 때까지 모든 개체 Id가 유효 하지 않은 것으로 간주 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 인터페이스](icorprofilercallback2-interface.md)
