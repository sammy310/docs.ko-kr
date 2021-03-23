---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드'
title: 'ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeGetProviderInfo
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7bc7ffe1c31e88dc1c65f1670f9bd179e732abfe
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805703"
---
# <a name="icorprofilerinfo12eventpipegetproviderinfo-method"></a>ICorProfilerInfo12:: EventPipeGetProviderInfo 메서드

프로파일러에서 다른 EventPipe 수신기가 받을 이벤트를 작성 하는 데 사용할 수 있는 EventPipe 공급자를 만듭니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeGetProviderInfo(
                [in] EVENTPIPE_PROVIDER provider,
                [in]  ULONG      cchName,
                [out] ULONG      *pcchName,
                [out, annotation("_Out_writes_to_(cchName, *pcchName)")]
                      WCHAR      providerName[]);
```  
  
## <a name="parameters"></a>매개 변수

`provider` 진행 이름을 제공할 공급자의 ID입니다.

`cchName` 진행 의 크기 (문자) `providerName` 입니다.

`pcchName` 제한이 의 총 문자 길이에 대 한 포인터 `providerName` 입니다.

`providerName` 제한이 호출자가 와이드 문자 버퍼를 제공 했습니다. 함수가 반환 될 때 버퍼에는 공급자 이름이 포함 됩니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [EventPipe 개요](../../../core/diagnostics/eventpipe.md)
- [잘 알려진 EventProviders](../../../core/diagnostics/well-known-event-providers.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
