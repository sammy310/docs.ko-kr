---
title: ICorProfilerCallback::RemotingClientInvocationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2722497db5622dee4adcfd9381837477b89a8f63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206579"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished 메서드
클라이언트에서 원격 호출이 완료 될 때까지 실행 된 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>설명  
 동기 원격 호출 되었으면 서버에서 완료 될 때까지 실행할 수도 했습니다. 원격 호출이 비동기 인 경우 회신을 여전히 예상 되는 호출 처리 될 때입니다. 에 대 한 호출으로 발생 하는 응답을 예상 되 면 [icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 추가로 호출 하 고 `RemotingClientInvocationFinished` 필요한 보조 처리 하는 비동기 호출을 나타냅니다.  
  
 각 콜백의 다음 쌍 동일한 스레드에서 발생 합니다.  
  
-   `RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [Icorprofilercallback:: Remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) 고 [icorprofilercallback:: Remotingclientinvocationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [Icorprofilercallback:: Remotingserverinvocationreturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) 고 [icorprofilercallback:: Remotingserversendingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 원격 콜백 사용 하 여 다음 문제를 파악 해야 합니다.  
  
-   클라이언트에서 호출 되 고 서버에서 실행 되는 함수에 대 한 알림을 올바르게 수신 되지 않습니다 있도록 remoting 함수 실행 API 프로파일러에 의해 반영 되지 않습니다. 프록시 개체를 통해 발생 하는 실제 호출 프로파일러, 특정 함수는 JIT 컴파일 되었지만 사용 되지는 않습니다 나타납니다.  
  
-   프로파일러는 비동기 원격 서비스 이벤트에 대 한 정확한 알림을 받지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
