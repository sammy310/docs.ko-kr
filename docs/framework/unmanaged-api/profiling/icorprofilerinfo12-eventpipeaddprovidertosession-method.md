---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드'
title: 'ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeAddProviderToSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 70654660c496211c20459ef9ba37dfbd96b829b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805690"
---
# <a name="icorprofilerinfo12eventpipeaddprovidertosession-method"></a>ICorProfilerInfo12:: EventPipeAddProviderToSession 메서드

기존 EventPipe 세션에 공급자를 추가 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeAddProviderToSession(
        [in] EVENTPIPE_SESSION                 session,
        [in] COR_PRF_EVENTPIPE_PROVIDER_CONFIG providerConfig);
```  
  
## <a name="parameters"></a>매개 변수

`session` 진행 공급자를 추가할 세션의 ID입니다.

`providerConfig` 진행 `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` 세션에 추가할 공급자를 설명 하는입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [EventPipe 개요](../../../core/diagnostics/eventpipe.md)
- [잘 알려진 EventProviders](../../../core/diagnostics/well-known-event-providers.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
- [COR_PRF_EVENTPIPE_PROVIDER_CONFIG 구조체](cor-prf-eventpipe-provider-config-structure.md)
