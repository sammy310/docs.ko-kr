---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PARAM_TYPE'
title: COR_PRF_EVENTPIPE_PARAM_TYPE 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_TYPE
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 29aed86e4a991598d038a60ae086e77e25df24bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805781"
---
# <a name="cor_prf_eventpipe_param_type-enumeration"></a>COR_PRF_EVENTPIPE_PARAM_TYPE 열거형

EventPipe 이벤트의 매개 변수 형식을 설명 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_OBJECT = 1,
    COR_PRF_EVENTPIPE_BOOLEAN = 3,
    COR_PRF_EVENTPIPE_CHAR = 4,
    COR_PRF_EVENTPIPE_SBYTE = 5,
    COR_PRF_EVENTPIPE_BYTE = 6,
    COR_PRF_EVENTPIPE_INT16 = 7,
    COR_PRF_EVENTPIPE_UINT16 = 8,
    COR_PRF_EVENTPIPE_INT32 = 9,
    COR_PRF_EVENTPIPE_UINT32 = 10,
    COR_PRF_EVENTPIPE_INT64 = 11,
    COR_PRF_EVENTPIPE_UINT64 = 12,
    COR_PRF_EVENTPIPE_SINGLE = 13,
    COR_PRF_EVENTPIPE_DOUBLE = 14,
    COR_PRF_EVENTPIPE_DECIMAL = 15,
    COR_PRF_EVENTPIPE_DATETIME = 16,
    COR_PRF_EVENTPIPE_GUID = 17,
    COR_PRF_EVENTPIPE_STRING = 18,
    COR_PRF_EVENTPIPE_ARRAY = 19,
} COR_PRF_EVENTPIPE_PARAM_TYPE;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_OBJECT`|매개 변수 형식은 자체 설명 개체입니다.|
|`COR_PRF_EVENTPIPE_BOOLEAN`|매개 변수 형식은 부울입니다.|
|`COR_PRF_EVENTPIPE_CHAR`|매개 변수 형식은 16 비트 와이드 문자입니다.|
|`COR_PRF_EVENTPIPE_SBYTE`|매개 변수 형식은 부호 있는 8 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_BYTE`|매개 변수 형식이 부호 없는 8 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_INT16`|매개 변수 형식은 부호 있는 16 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_UINT16`|매개 변수 형식이 부호 없는 16 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_INT32`|매개 변수 형식은 부호 있는 32 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_UINT32`|매개 변수 형식이 부호 없는 32 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_INT64`|매개 변수 형식은 부호 있는 64 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_UINT64`|매개 변수 형식이 부호 없는 64 비트 정수입니다.|
|`COR_PRF_EVENTPIPE_SINGLE`|매개 변수 형식은 32 비트 부동 소수점 숫자입니다.|
|`COR_PRF_EVENTPIPE_DOUBLE`|매개 변수 형식은 64 비트 부동 소수점 숫자입니다.|
|`COR_PRF_EVENTPIPE_DECIMAL`|매개 변수 형식은 128 비트 부동 소수점 숫자입니다.|
|`COR_PRF_EVENTPIPE_DATETIME`|매개 변수 형식은 직렬화 된 DataTime 구조체입니다.|
|`COR_PRF_EVENTPIPE_GUID`|매개 변수 유형은 GUID입니다.|
|`COR_PRF_EVENTPIPE_STRING`|매개 변수 형식은 16 비트 null로 끝나는 와이드 문자열입니다.|
|`COR_PRF_EVENTPIPE_ARRAY`|매개 변수 형식은 위의 형식 중 하나의 배열입니다.|
  
## <a name="remarks"></a>설명  

 `COR_PRF_EVENTPIPE_PARAM_TYPE`열거형은 [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) 구조에서 매개 변수의 형식을 나타내는 데 사용 됩니다.
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
