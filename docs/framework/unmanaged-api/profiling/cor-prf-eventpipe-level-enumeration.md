---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_LEVEL'
title: COR_PRF_EVENTPIPE_LEVEL 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_LEVEL
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: da8211da1a9bb6262b078c5e56bee1d0c1f9342e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805820"
---
# <a name="cor_prf_eventpipe_level-enumeration"></a>COR_PRF_EVENTPIPE_LEVEL 열거형

EventPipe 이벤트의 수준을 설명 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_LOGALWAYS = 0,
    COR_PRF_EVENTPIPE_CRITICAL = 1,
    COR_PRF_EVENTPIPE_ERROR = 2,
    COR_PRF_EVENTPIPE_WARNING = 3,
    COR_PRF_EVENTPIPE_INFORMATIONAL = 4,
    COR_PRF_EVENTPIPE_VERBOSE = 5
} COR_PRF_EVENTPIPE_LEVEL;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_LOGALWAYS`|이벤트는 항상 로깅됩니다.|
|`COR_PRF_EVENTPIPE_CRITICAL`|이벤트는 중요 한 메시지를 나타냅니다.|
|`COR_PRF_EVENTPIPE_ERROR`|이벤트는 오류 메시지를 나타냅니다.|
|`COR_PRF_EVENTPIPE_WARNING`|이벤트는 경고 메시지를 나타냅니다.|
|`COR_PRF_EVENTPIPE_INFORMATIONAL`|이벤트는 정보 메시지를 나타냅니다.|
|`COR_PRF_EVENTPIPE_VERBOSE`|이벤트는 자세한 정보 메시지를 나타냅니다.|
  
## <a name="remarks"></a>설명  

 `COR_PRF_EVENTPIPE_LEVEL`열거형은 [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) 메서드에서 정의 되는 이벤트의 수준을 나타내는 데 사용 됩니다.
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md)
