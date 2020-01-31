---
title: ICorProfilerCallback::ObjectReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866093"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences 메서드
지정 된 개체에서 참조 되는 메모리의 개체에 대해 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 진행 개체를 참조 하는 개체의 ID입니다.  
  
 `classId`  
 진행 지정 된 개체가 인스턴스인 클래스의 ID입니다.  
  
 `cObjectRefs`  
 진행 지정 된 개체에서 참조 하는 개체 수 (`objectRefIds` 배열의 요소 수)입니다.  
  
 `objectRefIds`  
 진행 `objectId`에서 참조 하는 개체의 Id 배열입니다.  
  
## <a name="remarks"></a>주의  
 `ObjectReferences` 메서드는 가비지 수집이 완료 된 후 힙에 남아 있는 각 개체에 대해 호출 됩니다. 프로파일러가이 콜백에서 오류를 반환 하는 경우 프로 파일링 서비스는 다음 가비지 수집이 끝날 때까지이 콜백 호출을 중단 합니다.  
  
 [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 콜백과 함께 `ObjectReferences` 콜백을 사용 하 여 런타임에 대 한 전체 개체 참조 그래프를 만들 수 있습니다. CLR (공용 언어 런타임)은 각 개체 참조가 `ObjectReferences` 메서드에서 한 번만 보고 되도록 합니다.  
  
 가비지 컬렉션이 개체를 이동 하는 중일 수 있기 때문에 `ObjectReferences`에 의해 반환 되는 개체 Id는 콜백 자체에서 유효 하지 않습니다. 따라서 프로파일러는 `ObjectReferences` 호출 중에 개체 검사를 시도 하지 않아야 합니다. [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.  
  
 Null `ClassId`은 `objectId`의 형식이 언로드되고 있음을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
