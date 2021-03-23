---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PARAM_DESC'
title: COR_PRF_EVENTPIPE_PARAM_DESC 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_DESC
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: b23897580092cc9f3f887a21e86f7111fecd9f19
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805794"
---
# <a name="cor_prf_eventpipe_param_desc-enumeration"></a>COR_PRF_EVENTPIPE_PARAM_DESC 열거형

EventPipe 이벤트의 매개 변수 이름 및 유형을 설명 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct
{
    UINT32       type;
    UINT32       elementType;
    const WCHAR *name;
} COR_PRF_EVENTPIPE_PARAM_DESC;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`type`|매개 변수의 형식입니다.|  
|`elementType`|이 매개 변수가 배열 형식인 경우 요소 형식입니다.|  
|`name`|매개 변수의 이름을 포함 하는 와이드 문자열입니다.|  
  
## <a name="remarks"></a>설명  

 `COR_PRF_EVENTPIPE_PARAM_DESC`구조체는 [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) 메서드에서 정의 되는 이벤트의 매개 변수 형식을 정의 하는 데 사용 됩니다.
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md)
