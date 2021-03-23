---
description: '자세히 알아보기: ICorProfilerCallback10 인터페이스'
title: ICorProfilerCallback10 인터페이스
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d9091dc81307e2dcb83e74154a8217dffaa1e7a2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805651"
---
# <a name="icorprofilercallback10-interface"></a>ICorProfilerCallback10 인터페이스

 EventPipe 이벤트가 프로파일러의 현재 활성 세션에 전달 되었음을 프로파일러에 알리는 콜백 메서드를 제공 하는 [ICorProfilerCallback9](icorprofilercallback9-interface.md) 의 서브 클래스입니다.
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EventPipeEventDelivered 메서드](icorprofilercallback10-eventpipeeventdelivered-method.md)|프로파일러에서 연 세션에 EventPipe 이벤트가 전달 되었음을 프로파일러에 알립니다.|
|[EventPipeProviderCreated 메서드](icorprofilercallback10-eventpipeprovidercreated-method.md)|프로파일러가 EventPipe 공급자를 만들었음을 알리기 때문에 프로파일러가 해당 공급자의 세션을 추가할 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  

## <a name="see-also"></a>참조

- [EventPipe 개요](../../../core/diagnostics/eventpipe.md)
- [잘 알려진 EventProviders](../../../core/diagnostics/well-known-event-providers.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo12 인터페이스](ICorProfilerInfo12-interface.md)
- [ICorProfilerInfo12 EventPipeStartSession 메서드](ICorProfilerInfo12-eventpipestartsession-method.md)
- [ICorProfilerInfo12 EventPipeStopSession 메서드](ICorProfilerInfo12-eventpipestopsession-method.md)
