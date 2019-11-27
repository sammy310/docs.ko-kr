---
title: ICorProfilerCallback::ObjectAllocated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445845"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated 메서드
힙에 있는 메모리가 개체에 할당 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `objectId`  
 진행 메모리가 할당 된 개체의 ID입니다.  
  
 `classId`  
 진행 개체가 인스턴스인 클래스의 ID입니다.  
  
## <a name="remarks"></a>주의  
 스택 또는 관리 되지 않는 메모리의 할당에 대해서는 `ObjectedAllocated` 메서드가 호출 되지 않습니다. `classId` 매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다. 프로파일러는 `ObjectAllocated` 콜백 직후 해당 클래스에 대 한 클래스 로드 콜백을 수신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassLoadStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
