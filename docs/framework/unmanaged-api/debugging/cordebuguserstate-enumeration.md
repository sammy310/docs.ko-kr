---
description: '다음에 대 한 자세한 정보: CorDebugUserState 열거형'
title: CorDebugUserState 열거형
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: c556e7943751fb8e159e3e0d0b9a71baf1f6b5b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661742"
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState 열거형

스레드의 사용자 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>구성원  
  
|값|설명|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|스레드의 종료를 요청 했습니다.|  
|`USER_SUSPEND_REQUESTED`|스레드의 일시 중단이 요청 되었습니다.|  
|`USER_BACKGROUND`|스레드가 백그라운드에서 실행 되 고 있습니다.|  
|`USER_UNSTARTED`|스레드가 실행을 시작 하지 않았습니다.|  
|`USER_STOPPED`|스레드가 종료 되었습니다.|  
|`USER_WAIT_SLEEP_JOIN`|스레드가 다른 스레드가 작업을 완료할 때까지 기다리고 있습니다.|  
|`USER_SUSPENDED`|스레드가 일시 중단되었습니다.|  
|`USER_UNSAFE_POINT`|스레드가 안전 하지 않은 지점에 있습니다. 즉, 스레드는 가비지 수집을 차단할 수 있는 실행 위치에 있습니다.<br /><br /> 안전 하지 않은 지점에서 디버그 이벤트를 디스패치할 수도 있지만 안전 하지 않은 지점에서 스레드를 일시 중단 하면 스레드가 다시 시작 될 때까지 교착 상태가 발생할 가능성이 높습니다. 안전 하 고 안전 하지 않은 지점은 JIT (just-in-time) 및 가비지 수집 구현에 따라 결정 됩니다.|  
|`USER_THREADPOOL`|스레드가 스레드 풀에서 가져온 경우|  
  
## <a name="remarks"></a>설명  

 스레드의 사용자 상태는 디버거에서 해당 스레드를 검사할 때 스레드에 포함 된 상태입니다. 스레드에는 사용자 상태의 조합이 있을 수 있습니다.  
  
 [ICorDebugThread:: GetUserState](icordebugthread-getuserstate-method.md) 메서드를 사용 하 여 스레드의 사용자 상태를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
