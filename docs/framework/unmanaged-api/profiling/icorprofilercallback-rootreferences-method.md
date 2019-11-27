---
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
ms.openlocfilehash: 9c96cacf508ef5c056a1ff4469247393fdfb9e9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444466"
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
 진행 `rootRefIds` 배열에 있는 참조의 수입니다.  
  
 `rootRefIds`  
 진행 스택의 개체 또는 정적 개체를 참조 하는 개체 Id의 배열입니다.  
  
## <a name="remarks"></a>주의  
 `RootReferences` 및 [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 를 모두 호출 하 여 프로파일러에 알립니다. `RootReferences2` 전달 된 정보는 `RootReferences`전달 된 상위 집합 이므로 프로파일러는 일반적으로 하나 또는 다른 하나를 구현 하지만 둘 다 구현 하지는 않습니다.  
  
 `rootRefIds` 배열에 null 개체를 포함할 수 있습니다. 예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에 의해 루트로 처리 되며 항상 보고 됩니다.  
  
 가비지 수집은 이전 주소에서 새 주소로 개체를 이동 하는 중일 수 있기 때문에 `RootReferences`에서 반환 하는 개체 Id는 콜백 자체에서 유효 하지 않습니다. 따라서 프로파일러는 `RootReferences` 호출 중에 개체 검사를 시도 하지 않아야 합니다. [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 를 호출 하면 모든 개체가 새 위치로 이동 되었으며 안전 하 게 검사할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
