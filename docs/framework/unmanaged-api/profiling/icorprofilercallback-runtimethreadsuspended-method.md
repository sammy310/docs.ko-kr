---
title: ICorProfilerCallback::RuntimeThreadSuspended 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865872"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended 메서드
지정 된 스레드가 일시 중단 되었거나 일시 중단 됨을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadId`  
 진행 일시 중단 된 스레드의 ID입니다.  
  
## <a name="remarks"></a>주의  
 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 와 연결 된 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백 사이에 언제 든 `RuntimeThreadSuspended` 알림이 발생할 수 있습니다. [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 와 `RuntimeResumeStarted` 사이에 발생 하는 알림은 비관리 코드에서 실행 중이 고 런타임에 진입 될 때 일시 중단 된 스레드에 대 한 것입니다.  
  
 일반적으로이 콜백은 스레드가 일시 중단 된 후에만 발생 합니다. 그러나 현재 실행 중인 스레드 (이 콜백을 호출한 스레드가 일시 중단 된 스레드) 인 경우이 콜백은 스레드가 일시 중단 되기 직전에 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [RuntimeThreadResumed 메서드](icorprofilercallback-runtimethreadresumed-method.md)
