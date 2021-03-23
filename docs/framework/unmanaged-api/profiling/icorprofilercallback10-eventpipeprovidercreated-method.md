---
description: '자세히 알아보기: ICorProfilerCallback10:: EventPipeProviderCreated 메서드'
title: 'ICorProfilerCallback10:: EventPipeProviderCreated 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeProviderCreated
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4602438148a369f2a2321a2ec2e959cc375e37cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805586"
---
# <a name="icorprofilercallback10eventpipeprovidercreated-method"></a>ICorProfilerCallback10:: EventPipeProviderCreated 메서드

EventPipe 공급자가 만들어질 때마다 프로파일러에 알립니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeProviderCreated([in] EVENTPIPE_PROVIDER provider); 
```  
  
## <a name="parameters"></a>매개 변수

`provider` 진행 만든 공급자입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
- [ICorProfilerInfo12 EventPipeAddProviderToSession 메서드](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
