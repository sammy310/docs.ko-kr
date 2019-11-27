---
title: COR_PRF_STATIC_TYPE 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 40efe81f72a2043503bf521e3e47dad1a7f4530c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448443"
---
# <a name="cor_prf_static_type-enumeration"></a>COR_PRF_STATIC_TYPE 열거형
필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다. 비트 OR 연산을 사용 하 여 이러한 값을 결합 하 여 필드에 여러 다른 정적 품질이 있음을 나타낼 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|필드가 static이 아닙니다.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|응용 프로그램 도메인-정적 필드입니다.|  
|`COR_PRF_FIELD_THREAD_STATIC`|이 필드는 스레드 정적 필드입니다.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|정적 필드입니다.|  
|`COR_PRF_FIELD_RVA_STATIC`|RVA (상대 가상 주소)-정적 필드입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
