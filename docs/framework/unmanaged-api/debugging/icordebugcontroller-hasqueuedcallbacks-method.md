---
title: ICorDebugController::HasQueuedCallbacks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125394"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks 메서드
지정 된 스레드에 대해 관리 되는 콜백이 현재 대기 중인지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pThread`  
 진행 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.  
  
 `pbQueued`  
 제한이 현재 지정 된 스레드에 대해 관리 되는 콜백이 현재 큐에 대기 중인 경우 `true` 되는 값에 대 한 포인터입니다. 그렇지 않으면 `false`합니다.  
  
 `pThread` 매개 변수에 대해 null이 지정 된 경우 현재 스레드에 대해 대기 중인 관리 되는 콜백이 있으면 `HasQueuedCallbacks` `true` 반환 됩니다.  
  
## <a name="remarks"></a>주의  
 콜백은 한 번에 하나씩 디스패치 될 때마다 [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 가 호출 됩니다. 디버거는 동시에 발생 하는 여러 디버깅 이벤트를 보고 하려는 경우이 플래그를 확인할 수 있습니다.  
  
 디버깅 이벤트가 큐에 대기 되는 경우 이미 발생 했으므로 디버거가 디버기 상태를 확인할 수 있도록 전체 큐를 드레이닝 해야 합니다. `ICorDebugController::Continue`를 호출 하 여 큐를 드레이닝 합니다. 예를 들어, 큐에 스레드 *x*에 대 한 두 개의 디버깅 이벤트가 포함 되어 있고 디버거가 첫 번째 디버깅 이벤트 후에 스레드 *x* 를 일시 중단 한 다음 `ICorDebugController::Continue`를 호출 하는 경우, 스레드 *x* 에 대 한 두 번째 디버깅 이벤트는 스레드가 일시 중단 되었습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
