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
ms.openlocfilehash: fda234a6a280aeea1f497ad195d6d41efb6aa951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674346"
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
  
## <a name="remarks"></a>설명  

 `ObjectedAllocated`스택 또는 관리 되지 않는 메모리의 할당에 대해 메서드가 호출 되지 않습니다. `classId`매개 변수는 아직 로드 되지 않은 관리 코드의 클래스를 참조할 수 있습니다. 프로파일러는 콜백 직후 해당 클래스에 대 한 클래스 로드 콜백을 받게 됩니다 `ObjectAllocated` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ClassLoadStarted 메서드](icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished 메서드](icorprofilercallback-classloadfinished-method.md)
