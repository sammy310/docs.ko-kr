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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 310915ce84819a2a5a2d5e1f22356b61c16e7ec7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599015"
---
# <a name="corprfstatictype-enumeration"></a>COR_PRF_STATIC_TYPE 열거형
필드가 정적인지 여부와 정적인 경우 필드에 적용될 정적 품질을 나타냅니다. 비트 OR 연산을 사용 하 여 필드에 여러 개의 있음을 나타내기 위해 이러한 값을 결합할 수 있습니다 다른 정적 품질입니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|필드에는 응용 프로그램 도메인 정적입니다.|  
|`COR_PRF_FIELD_THREAD_STATIC`|필드는 스레드에 정적인입니다.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|필드에는 컨텍스트 정적입니다.|  
|`COR_PRF_FIELD_RVA_STATIC`|필드는 가상 RVA (상대 주소)-고정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
