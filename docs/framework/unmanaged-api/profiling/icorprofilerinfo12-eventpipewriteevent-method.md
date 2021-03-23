---
description: '자세히 알아보기: ICorProfilerInfo12:: EventPipeWriteEvent 메서드'
title: 'ICorProfilerInfo12:: EventPipeWriteEvent 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeWriteEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a0a06ff0fa1c936518586834f4dfc73810ef0e44
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805742"
---
# <a name="icorprofilerinfo12eventpipewriteevent-method"></a>ICorProfilerInfo12:: EventPipeWriteEvent 메서드

이 이벤트를 사용 하도록 설정한 모든 수신기에 EventPipe 이벤트를 씁니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeWriteEvent(
                [in] EVENTPIPE_EVENT    event,
                [in] UINT32             cData,
                [in, size_is(cData)]
                     COR_PRF_EVENT_DATA data[],
                [in] LPCGUID            pActivityId,
                [in] LPCGUID            pRelatedActivityId);
```  
  
## <a name="parameters"></a>매개 변수

`event` 진행 쓰여지는 이벤트의 ID입니다.

`cData` 진행 의 요소 수 `data` 입니다.

`data` 진행 `COR_PRF_EVENT_DATA` 이벤트 인수를 포함 하는의 배열입니다.

`pActivityId` 진행 이벤트의 작업 ID를 지정 하는 GUID에 대 한 포인터입니다.

`pRelatedActivityId` 진행 이벤트의 관련 작업 ID를 지정 하는 GUID에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
- [COR_PRF_EVENT_DATA 구조체](cor-prf-event-data-structure.md)
