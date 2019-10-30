---
title: ICorDebugProcess::ClearCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 37a7d8fa4439d52db3cddfff22ac6580b19af58a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128907"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>ICorDebugProcess::ClearCurrentException 메서드
지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadID`  
 진행 현재 관리 되지 않는 예외를 지울 스레드의 ID입니다.  
  
## <a name="remarks"></a>주의  
 스레드가 디버기에서 무시 해야 하는 관리 되지 않는 예외를 보고 한 경우 [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 를 호출 하기 전에이 메서드를 호출 합니다. 그러면 지정 된 스레드의 IB (대역 외) 및 OOB (대역 외) 이벤트가 모두 지워집니다. 모든 OOB 중단점과 단일 단계 예외는 자동으로 지워집니다.  
  
 [ICorDebugThread2:: InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) 를 사용 하 여 스레드에서 현재 관리 되는 예외를 가로챌 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
