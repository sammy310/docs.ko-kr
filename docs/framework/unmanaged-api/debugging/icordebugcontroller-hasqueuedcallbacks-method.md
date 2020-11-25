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
ms.openlocfilehash: bd623f8bee2feafebe80c0c7513bcfb33d6ad367
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707908"
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
 제한이 `true` 현재 지정 된 스레드에 대해 관리 되는 콜백이 현재 대기 중인 경우에는 값에 대 한 포인터이 고, 그렇지 않으면 `false` 입니다.  
  
 매개 변수에 null이 지정 된 경우는 `pThread` `HasQueuedCallbacks` `true` 스레드에 대해 현재 대기 중인 관리 되는 콜백이 있으면를 반환 합니다.  
  
## <a name="remarks"></a>설명  

 콜백은 한 번에 하나씩 디스패치 될 때마다 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 가 호출 됩니다. 디버거는 동시에 발생 하는 여러 디버깅 이벤트를 보고 하려는 경우이 플래그를 확인할 수 있습니다.  
  
 디버깅 이벤트가 큐에 대기 되는 경우 이미 발생 했으므로 디버거가 디버기 상태를 확인할 수 있도록 전체 큐를 드레이닝 해야 합니다. 를 호출 `ICorDebugController::Continue` 하 여 큐를 드레이닝 합니다. 예를 들어, 큐에 스레드 *x* 에 대 한 두 개의 디버깅 이벤트가 포함 된 경우 디버거는 첫 번째 디버깅 이벤트 후에 스레드 *x* 를 일시 중단 하 고를 호출한 다음 스레드 `ICorDebugController::Continue` *x* 에 대 한 두 번째 디버깅 이벤트는 스레드가 일시 중단 된 경우에도 디스패치 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
