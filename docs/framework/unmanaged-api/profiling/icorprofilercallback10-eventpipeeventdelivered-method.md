---
description: '자세히 알아보기: ICorProfilerCallback10:: EventPipeEventDelivered 메서드'
title: 'ICorProfilerCallback10:: EventPipeEventDelivered 메서드'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeEventDelivered
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7b2ca813d610c2b41d97d8cd76dac22ca38802d7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805638"
---
# <a name="icorprofilercallback10eventpipeeventdelivered-method"></a>ICorProfilerCallback10:: EventPipeEventDelivered 메서드

EventPipe 이벤트가 프로파일러의 현재 활성 세션에 전달 될 때마다 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
    HRESULT EventPipeEventDelivered(
        [in] EVENTPIPE_PROVIDER provider,
        [in] DWORD eventId,
        [in] DWORD eventVersion,
        [in] ULONG cbMetadataBlob,
        [in, size_is(cbMetadataBlob)] LPCBYTE metadataBlob,
        [in] ULONG cbEventData,
        [in, size_is(cbEventData)] LPCBYTE eventData,
        [in] LPCGUID pActivityId,
        [in] LPCGUID pRelatedActivityId,
        [in] ThreadID eventThread,
        [in] ULONG numStackFrames,
        [in, length_is(numStackFrames)] UINT_PTR stackFrames[]); 
```  
  
## <a name="parameters"></a>매개 변수

`provider` 진행 이 이벤트가 시작 된 공급자입니다.

`eventId` 진행 배달 되는 이벤트의 ID입니다.

`eventVersion` 진행 전달 되는 이벤트의 버전입니다.

`cbMetadataBlob` 진행 의 길이 (바이트)입니다 `metadataBlob` .

`metadataBlob` 진행 이벤트에 대 한 메타 데이터 blob에 대 한 포인터입니다.

`cbEventData` 진행 의 길이 (바이트)입니다 `eventData` .

`eventData` 진행 이벤트에 대 한 페이로드입니다.

`pActivityId` 진행 이벤트의 작업 ID 또는 NULL을 나타내는 GUID에 대 한 포인터입니다.

`pRelatedActivityId` 진행 이벤트의 관련 작업 ID 또는 NULL을 나타내는 GUID에 대 한 포인터입니다.

`eventThread` 진행 이벤트가 발생 한 스레드의 ID입니다.

`numStackFrames` 진행 배열의 요소 수 `stackFrames` 입니다.

`stackFrames` 진행 이벤트의 관리 되는 호출 스택을 나타내는 코드 주소 배열입니다.

## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.  
**헤더:** CorProf.idl, CorProf.h  
**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback10 인터페이스](icorprofilercallback10-interface.md)
- [ICorProfilerInfo12 인터페이스](icorprofilerinfo12-interface.md)
- [ICorProfilerInfo12 EventPipeStartSession 메서드](icorprofilerinfo12-eventpipestartsession-method.md)
