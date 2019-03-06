---
title: ICorProfilerCallback::RuntimeSuspendStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f07cd585ab800394569b97d103e292a5d8f36f20
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466755"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted 메서드
런타임에서 모든 런타임 스레드를 일시 중단 하 려 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>매개 변수  
 `suspendReason`  
 [in] 값을 [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) 일시 중단 이유를 나타내는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 비관리 코드에 있는 모든 런타임 스레드 런타임을 다시 입력 하려고 할 때까지 계속 실행 될 수 있습니다. 이때 이러한도 일시 중단 됩니다 런타임을 다시 시작 될 때까지. 이 런타임에 입력 하는 새 스레드에도 적용 됩니다. 런타임의 모든 스레드는 즉시 일시 중단 되거나 인터럽트 가능한 코드에 포함 되어 있습니다 하거나 중단할 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeSuspendAborted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [RuntimeSuspendFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
