---
title: LoggingLevelEnum 열거형
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 389edbeb746fbeaf60d88bf9ee2a3a0731822e55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672021"
---
# <a name="logginglevelenum-enumeration"></a>LoggingLevelEnum 열거형

관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`LTraceLevel0`|메시지는 추적 수준 0입니다.|  
|`LTraceLevel1`|메시지는 추적 수준 1입니다.|  
|`LTraceLevel2`|메시지는 추적 수준 2입니다.|  
|`LTraceLevel3`|메시지는 추적 수준 3입니다.|  
|`LTraceLevel4`|메시지는 추적 수준 4입니다.|  
|`LStatusLevel0`|메시지의 상태 수준은 0입니다.|  
|`LStatusLevel1`|메시지는 상태 수준 1입니다.|  
|`LStatusLevel2`|메시지는 상태 수준 2입니다.|  
|`LStatusLevel3`|메시지는 상태 수준 3입니다.|  
|`LStatusLevel4`|메시지는 상태 수준 4입니다.|  
|`LWarningLevel`|메시지는 경고 수준입니다.|  
|`LErrorLevel`|메시지는 오류 수준입니다.|  
|`LPanicLevel`|메시지는 비상 수준입니다.|  
  
## <a name="remarks"></a>설명  

 CLR (공용 언어 런타임)은 [ICorDebugManagedCallback:: LogMessage](icordebugmanagedcallback-logmessage-method.md) 메서드를 호출 하 여 관리 되는 스레드가 이벤트를 기록 했음을 디버거에 알립니다. CLR은 열거형 값을 전달 `LoggingLevelEnum` 하 여 관리 되는 스레드가 이벤트 로그에 기록 하는 메시지의 심각도 수준을 표시 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- <xref:System.Diagnostics.EventLog>
- [디버깅 열거형](debugging-enumerations.md)
