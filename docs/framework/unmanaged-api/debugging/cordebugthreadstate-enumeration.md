---
title: CorDebugThreadState 열거형
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 69a8aabd1d79bb9bb4248259c99124ce50677600
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789241"
---
# <a name="cordebugthreadstate-enumeration"></a>CorDebugThreadState 열거형
디버깅을 위한 스레드 상태를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`THREAD_RUN`|디버그 이벤트가 발생 하지 않는 한 스레드는 자유롭게 실행 됩니다.|  
|`THREAD_SUSPEND`|스레드를 실행할 수 없습니다.|  
  
## <a name="remarks"></a>주의  
 디버거는 `CorDebugThreadState` 열거를 사용 하 여 스레드의 실행을 제어 합니다. [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) 또는 [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) 메서드를 사용 하 여 스레드 상태를 설정할 수 있습니다.  
  
 [호스팅 API](../../../../docs/framework/unmanaged-api/hosting/index.md) 에 제공 된 콜백에서 메시지 펌프를 사용할 수 있으므로 중단 된 상태가 필요 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
