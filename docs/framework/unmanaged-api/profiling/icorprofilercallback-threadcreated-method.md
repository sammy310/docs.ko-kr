---
title: ICorProfilerCallback::ThreadCreated 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 72b074d1794a6039060cbd84aabb0bc0155c154e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717278"
---
# <a name="icorprofilercallbackthreadcreated-method"></a>ICorProfilerCallback::ThreadCreated 메서드

스레드가 생성 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a>매개 변수  

 `threadId`  
 진행 만들어진 스레드의 ID입니다.  
  
## <a name="remarks"></a>설명  

 `threadId`값이 즉시 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ThreadDestroyed 메서드](icorprofilercallback-threaddestroyed-method.md)
