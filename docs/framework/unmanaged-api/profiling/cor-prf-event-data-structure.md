---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENT_DATA'
title: COR_PRF_EVENT_DATA 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENT_DATA
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 477f36476deb9c0d74e263703e36b134c91b5327
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805569"
---
# <a name="cor_prf_event_data-enumeration"></a>COR_PRF_EVENT_DATA 열거형

작성 중인 EventPipe 이벤트에 대 한 이벤트 데이터를 설명 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct
{
    UINT64 ptr;
    UINT32 size;
    UINT32 reserved;
} COR_PRF_EVENT_DATA;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ptr`|데이터에 대 한 포인터입니다.|  
|`size`|가 가리키는 데이터의 크기입니다 `ptr` .|  
|`reserved`|예약 된 구현 특정 필드입니다.|  
  
## <a name="remarks"></a>설명  

 `COR_PRF_EVENT_DATA`이 구조는 [ICorProfilerInfo12:: EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) 메서드에서 작성 중인 이벤트에 대 한 데이터 페이로드를 프로 비전 하는 데 사용 됩니다.
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md)
