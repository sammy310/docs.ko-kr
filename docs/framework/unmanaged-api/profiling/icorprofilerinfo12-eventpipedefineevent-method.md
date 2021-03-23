---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeDefineEvent 메서드'
title: 'ICorProfilerInfo12:: EventPipeDefineEvent 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeDefineEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 845f7f26dce7aa0f4b7d895b9f04cc89e7ac7192
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805755"
---
# <a name="icorprofilerinfo12eventpipedefineevent-method"></a>ICorProfilerInfo12:: EventPipeDefineEvent 메서드

기존 공급자의 EventPipe 이벤트를 정의 합니다. 이 공급자는 다른 수신기가 받을 수 있는 EventPipe 이벤트를 작성 하는 데 사용할 수 있습니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeDefineEvent(
                [in] EVENTPIPE_PROVIDER     provider,
                [in, string] const WCHAR   *eventName,
                [in] UINT32                 eventID,
                [in] UINT64                 keywords,
                [in] UINT32                 eventVersion,
                [in] UINT32                 level,
                [in] UINT8                  opcode,
                [in] BOOL                   needStack,
                [in] UINT32                 cParamDescs,
                [in, size_is(cParamDescs)]
                     COR_PRF_EVENTPIPE_PARAM_DESC pParamDescs[],
                [out] EVENTPIPE_EVENT      *pEvent);
```  
  
## <a name="parameters"></a>매개 변수

`provider` 진행 이벤트를 정의할 공급자의 ID입니다.

`eventName` 진행 이벤트 이름을 포함 하는 null로 끝나는 와이드 문자열에 대 한 포인터입니다.

`eventID` 진행 정의 되는 이벤트의 ID입니다.

`keywords` 진행 정의 되는 이벤트의 키워드입니다.

`eventVersion` 진행 정의 되는 이벤트의 버전입니다.

`level` 진행 정의 되는 이벤트의 수준입니다.

`opcode` 진행 정의 되는 이벤트의 opcode입니다.

`needStack` 진행 `BOOL` 이 이벤트가 발생 될 때마다 관리 되는 스택을 수집 해야 하는지 여부를 나타내는입니다.

`cParamDescs` 진행 의 매개 변수 개수입니다 `pParamDescs` .

`pParamDescs` 진행 `COR_PRF_EVENTPIPE_PARAM_DESC` 정의 되는 이벤트에 대 한 매개 변수 형식을 정의 하는 배열입니다.

`pEvent` 제한이 함수가 반환 될 때 정의 되는 이벤트의 ID로 채워질 호출자 제공 포인터입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [EventPipe 개요](../../../core/diagnostics/eventpipe.md)
- [잘 알려진 EventProviders](../../../core/diagnostics/well-known-event-providers.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
- [COR_PRF_EVENTPIPE_PARAM_DESC 구조체](cor-prf-eventpipe-param-desc-structure.md)
