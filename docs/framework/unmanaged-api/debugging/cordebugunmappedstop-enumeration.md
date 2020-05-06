---
title: CorDebugUnmappedStop 열거형
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: 772f1f0dee260ad3752b2f89e5fbe0d6bc27b87b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795653"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop 열거형
스텝퍼에 의해 코드 실행에서 중지를 트리거할 수 있는 매핑되지 않은 코드 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`STOP_NONE`|모든 형식의 매핑되지 않은 코드에서 중지 하지 마십시오.|  
|`STOP_PROLOG`|프롤로그 코드에서를 중지 합니다.|  
|`STOP_EPILOG`|에필로그 코드에서 중지 합니다.|  
|`STOP_NO_MAPPING_INFO`|매핑 정보가 없는 코드에서를 중지 합니다.|  
|`STOP_OTHER_UNMAPPED`|프롤로그, 에필로그, 매핑되지 않음 정보 또는 관리 되지 않는 범주에 맞지 않는 매핑되지 않은 코드에서 중지 합니다.|  
|`STOP_UNMANAGED`|비관리 코드에서 중지 합니다. 이 값은 interop 디버깅에만 사용할 수 있습니다.|  
|`STOP_ALL`|매핑되지 않은 모든 형식의 코드에서 중지 합니다.|  
  
## <a name="remarks"></a>설명  
 [ICorDebugStepper:: SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) 메서드를 사용 하 여 스텝 퍼가 중지 될 매핑되지 않은 코드를 지정 하는 플래그를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
