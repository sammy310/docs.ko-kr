---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeStopSession 메서드'
title: 'ICorProfilerInfo12:: EventPipeStopSession 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeStopSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c1b104f63755bcec52a113be7e2aa9af76ecd34e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805716"
---
# <a name="icorprofilerinfo12eventpipestopsession-method"></a>ICorProfilerInfo12:: EventPipeStopSession 메서드

EventPipe 세션을 중지 하 여 이후 이벤트가 세션에 기록 되는 것을 방지 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeStopSession(
        [in] EVENTPIPE_SESSION session);
```  
  
## <a name="parameters"></a>매개 변수

`session` 진행 중지할 세션의 ID입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
