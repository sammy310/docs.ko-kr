---
title: ICorProfilerCallback::RuntimeSuspendFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: e6c21e5ec9491e2ccade48a5019b284e333b5ead
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865937"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished 메서드
런타임이 모든 런타임 스레드의 일시 중단을 완료 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>주의  
 비관리 코드에 있는 모든 런타임 스레드는 런타임을 다시 시작 하려고 할 때까지 계속 실행할 수 있습니다. 이 시점에서 런타임이 재개 될 때까지 일시 중단 됩니다. 이는 런타임에 입력 하는 새 스레드에도 적용 됩니다. 런타임의 모든 스레드는 이미 인터럽트 가능 코드에 있는 경우 즉시 일시 중단 되거나, 인터럽트가 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 됩니다.  
  
 `RuntimeSuspendFinished` 콜백은 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 콜백과 동일한 스레드에서 수행 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [RuntimeSuspendAborted 메서드](icorprofilercallback-runtimesuspendaborted-method.md)
