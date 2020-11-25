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
ms.openlocfilehash: 9485e3ca657ab108d2bcc9d00b1c475f8ee3c086
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703956"
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
 진행 지정 된 개체에서 참조 하는 개체의 수입니다 (배열의 요소 수 `objectRefIds` ).  
  
 `objectRefIds`  
 진행 에서 참조 하는 개체의 Id 배열입니다 `objectId` .  
  
## <a name="remarks"></a>설명  

 `ObjectReferences`가비지 수집이 완료 된 후 힙에 남아 있는 각 개체에 대해 메서드가 호출 됩니다. 프로파일러가이 콜백에서 오류를 반환 하는 경우 프로 파일링 서비스는 다음 가비지 수집이 끝날 때까지이 콜백 호출을 중단 합니다.  
  
 `ObjectReferences`콜백은 [ICorProfilerCallback:: rootreferences](icorprofilercallback-rootreferences-method.md) 콜백과 함께 사용 하 여 런타임에 대 한 전체 개체 참조 그래프를 만들 수 있습니다. CLR (공용 언어 런타임)은 각 개체 참조가 메서드에 의해 한 번만 보고 되도록 합니다 `ObjectReferences` .  
  
 가비지 컬렉션이 개체를 이동 하는 중일 수 있기 때문에에서 반환 하는 개체 Id는 `ObjectReferences` 콜백 자체에서 유효 하지 않습니다. 따라서 프로파일러는 호출 하는 동안 개체 검사를 시도 하지 않아야 합니다 `ObjectReferences` . [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 가비지 수집이 완료 되 고 검사를 안전 하 게 수행할 수 있습니다.  
  
 Null은에 `ClassId` `objectId` 언로드되고 있는 형식이 있음을 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
