---
description: '자세히 알아보기: ICorProfilerCallback:: RootReferences 메서드'
title: ICorProfilerCallback::RootReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: e09434c425784e646c9856693abdfd4ac0d49273
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788867"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences 메서드

가비지 수집 후 루트 참조에 대 한 정보를 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>매개 변수  

 `cRootRefs`  
 진행 배열에 있는 참조의 수 `rootRefIds` 입니다.  
  
 `rootRefIds`  
 진행 스택의 개체 또는 정적 개체를 참조 하는 개체 Id의 배열입니다.  
  
## <a name="remarks"></a>설명  

 `RootReferences`및 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 를 모두 호출 하 여 프로파일러에 알립니다. 일반적으로 전달 되는 정보는 `RootReferences2` 전달 되는의 상위 집합 이므로 프로파일러는 일반적으로 하나 또는 다른 하나를 구현 `RootReferences` 합니다.  
  
 `rootRefIds`배열에 null 개체가 포함 될 수 있습니다. 예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에 의해 루트로 처리 되며 항상 보고 됩니다.  
  
 에서 반환 하는 개체 Id는 `RootReferences` 가비지 컬렉션이 이전 주소에서 새 주소로 개체를 이동 하는 중일 수 있기 때문에 콜백 자체 중에는 유효 하지 않습니다. 따라서 프로파일러는 호출 하는 동안 개체 검사를 시도 하지 않아야 합니다 `RootReferences` . [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 모든 개체가 새 위치로 이동 되었으며 안전 하 게 검사할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
