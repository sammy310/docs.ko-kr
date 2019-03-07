---
title: ICorDebugThread::SetDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499695"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState 메서드
이 ICorDebugThread 디버깅 상태를 설명 하는 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `state`  
 [in] 이 스레드에 대 한 디버깅 상태를 지정 하는 CorDebugThreadState 열거형 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  
 `SetDebugState` 스레드의 현재 디버그 상태를 설정 합니다. ("현재 디버그 상태" 상태를 나타내는 디버그 프로세스가 계속 될 실제 현재 상태가 아니라 경우입니다.) 이 일반적인 값은 THREAD_RUNNING입니다. 디버거만 스레드 디버그 상태에 영향을 줄 수 있습니다. 디버그 상태 수행할 마지막 간에 계속 되 면 여러 통해 THREAD_SUSPENDed 계속 스레드를 유지 하려는 경우 한 번에 설정할 하 고 이후에 없는 걱정할 수 있도록 합니다. 스레드를 일시 중단 및 재개 하는 프로세스는 일반적으로 그럴 가능성은 있지만 교착 상태에 발생할 수 있습니다. 스레드 및 프로세스를 내장 품질 이며 의도적인입니다. 비동기적으로 디버거를 중단 하 고는 스레드는 교착 상태를 다시 시작할 수 있습니다. 스레드의 사용자 상태 USER_UNSAFE_POINT를 포함 하는 경우 스레드는 GC (가비지 수집)를 차단할 수 있습니다. 즉, 일시 중단 된 스레드 확률이 훨씬 더 높은 교착 상태를 일으킵니다. 이 이벤트 이미 큐에 대기 하는 디버그를 영향을 주지 않습니다. 디버거가 전체 이벤트 큐를 드레이닝 해야 하므로 (호출한 [icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 중단 또는 스레드를 다시 시작 하기 전에 합니다. 그렇지 않으면 이미 일시 중단 된 것으로 간주 된 스레드에서 이벤트가 발생할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
