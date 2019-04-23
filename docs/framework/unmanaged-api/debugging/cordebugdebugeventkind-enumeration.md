---
title: CorDebugDebugEventKind 열거형
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127176"
---
# <a name="cordebugdebugeventkind-enumeration"></a>CorDebugDebugEventKind 열거형
정보를 가져올 디코딩되는 이벤트의 형식을 나타내는 합니다 [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|모듈 로드 이벤트입니다.|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|모듈 언로드 이벤트입니다.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|첫째 예외입니다.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|첫째 사용자 예외입니다.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|`catch` 처리기가 있는 예외입니다.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|처리되지 않은 예외입니다.|  
  
## <a name="remarks"></a>설명  
 멤버는 `CorDebugDebugEventKind` 열거형이 호출 하 여 반환 합니다 [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) 메서드.  
  
> [!NOTE]
>  이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
