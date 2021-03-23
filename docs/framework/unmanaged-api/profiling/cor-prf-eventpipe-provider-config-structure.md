---
description: '다음에 대 한 자세한 정보: 열거형 COR_PRF_EVENTPIPE_PROVIDER_CONFIG'
title: COR_PRF_EVENTPIPE_PROVIDER_CONFIG 열거형
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PROVIDER_CONFIG
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2a7a5e720e9468b44e6504d24a3b9ad836e13693
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805846"
---
# <a name="cor_prf_eventpipe_provider_config-enumeration"></a>COR_PRF_EVENTPIPE_PROVIDER_CONFIG 열거형

EventPipe 공급자를 구성 하는 데 필요한 필드에 대해 설명 합니다.
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct
{
    const WCHAR* providerName;
    UINT64       keywords;
    UINT32       loggingLevel;
    const WCHAR* filterData;
} COR_PRF_EVENTPIPE_PROVIDER_CONFIG;
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`providerName`|사용할 공급자의 이름입니다.|  
|`keywords`|공급자에서 사용할 수 있는 키워드입니다.|  
|`loggingLevel`|공급자에서 사용할 수 있는 수준입니다.|  
|`filterData`|공급자를 사용 하도록 설정할 때 사용할 filterdata를 포함 하는 와이드 문자열입니다.|  
  
## <a name="remarks"></a>설명  

 `COR_PRF_EVENTPIPE_PROVIDER_CONFIG`이 구조는 [ICorProfilerInfo12:: EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) 메서드에서 세션에 추가 되는 공급자에 대 한 구성을 나타내는 데 사용 됩니다.
  
## <a name="requirements"></a>요구 사항  

**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.
**헤더:** Corprof.idl, Corprof.idl **.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
- [ICorProfilerInfo12::EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
