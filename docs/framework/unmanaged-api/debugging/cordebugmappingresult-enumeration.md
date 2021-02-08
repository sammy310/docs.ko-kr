---
description: '자세히 알아보기: CorDebugMappingResult 열거형'
title: CorDebugMappingResult 열거형
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: 03454e2fbfa8fabca89805ea51a6cfba27aa792f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801594"
---
# <a name="cordebugmappingresult-enumeration"></a>CorDebugMappingResult 열거형

IP(명령 포인터)의 값을 가져온 방법에 대한 세부 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`MAPPING_PROLOG`|네이티브 코드는 프롤로그에 있으므로 IP의 값은 0입니다.|  
|`MAPPING_EPILOG`|네이티브 코드는 에필로그에 있으므로 IP의 값은 메서드의 마지막 명령의 주소입니다.|  
|`MAPPING_NO_INFO`|메서드에 대 한 매핑 정보를 사용할 수 없으므로 IP의 값은 0입니다.|  
|`MAPPING_UNMAPPED_ADDRESS`|메서드에 대 한 매핑 정보가 있지만 현재 주소를 MSIL (Microsoft 중간 언어) 코드에 매핑할 수 없습니다. IP의 값은 0입니다.|  
|`MAPPING_EXACT`|메서드가 MSIL 코드에 정확히 매핑 되었거나 프레임이 해석 되었으므로 IP 값은 정확 합니다.|  
|`MAPPING_APPROXIMATE`|메서드가 성공적으로 매핑 되었지만 IP의 값이 근사값이 될 수 있습니다.|  
  
## <a name="remarks"></a>설명  

 [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) 메서드를 사용 하 여 명령 포인터의 값을 가져올 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
