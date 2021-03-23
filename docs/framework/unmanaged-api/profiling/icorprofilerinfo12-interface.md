---
description: '자세히 알아보기: ICorProfilerInfo12 인터페이스'
title: ICorProfilerInfo12 인터페이스
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a8b91eba686478c3e825ae15d6ae95bd0ffad944
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805729"
---
# <a name="icorprofilerinfo12-interface"></a>ICorProfilerInfo12 인터페이스

 EventPipe 세션, 이벤트 및 공급자를 만드는 메서드를 제공 하는 [ICorProfilerInfo11](icorprofilerinfo11-interface.md) 의 서브 클래스입니다.
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EventPipeStartSession 메서드](icorprofilerinfo12-eventpipestartsession-method.md)|프로파일러 EventPipe 세션을 시작 합니다.|
|[EventPipeAddProviderToSession 메서드](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)|기존 EventPipe 세션에 공급자를 추가 합니다.|
|[EventPipeStopSession 메서드](icorprofilerinfo12-eventpipestopsession-method.md)|EventPipe 세션을 중지 합니다.|
|[EventPipeCreateProvider 메서드](icorprofilerinfo12-eventpipecreateprovider-method.md)|EventPipe 공급자를 만듭니다.|  
|[EventPipeGetProviderInfo 메서드](icorprofilerinfo12-eventpipegetproviderinfo-method.md)|ID에서 EventPipe 공급자의 이름을 가져옵니다.|
|[EventPipeDefineEvent 메서드](icorprofilerinfo12-eventpipedefineevent-method.md)|기존 EventPipe 공급자에서 이벤트를 정의 합니다.|  
|[EventPipeWriteEvent 메서드](icorprofilerinfo12-eventpipewriteevent-method.md)|EventPipe 이벤트를 씁니다.|
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  

## <a name="see-also"></a>참조

- [EventPipe 개요](../../../core/diagnostics/eventpipe.md)
- [잘 알려진 EventProviders](../../../core/diagnostics/well-known-event-providers.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
