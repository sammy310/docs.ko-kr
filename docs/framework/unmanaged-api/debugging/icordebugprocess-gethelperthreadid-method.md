---
title: ICorDebugProcess::GetHelperThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: d38a59b23d47cbaf57dc21e121d56530a514d354
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128857"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID 메서드
디버거의 내부 도우미 스레드의 OS (운영 체제) 스레드 ID를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pThreadID`  
 제한이 디버거의 내부 도우미 스레드의 OS 스레드 ID에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 관리 및 관리 되지 않는 디버깅을 수행 하는 동안 디버거에서 지정한 중단점에 도달 하면 지정 된 ID를 가진 스레드가 계속 실행 되도록 하는 것이 디버거의 책임입니다. 디버거는 사용자 로부터이 스레드를 숨기려는 수도 있습니다. 프로세스에 도우미 스레드가 아직 없는 경우 `GetHelperThreadID` 메서드는 *`pThreadID`에서 0을 반환 합니다.  
  
 도우미 스레드의 스레드 ID는 시간이 지남에 따라 변경 될 수 있으므로 캐시할 수 없습니다. 모든 중지 이벤트에서 스레드 ID를 다시 쿼리해야 합니다.  
  
 디버거의 도우미 스레드의 스레드 ID는 모든 관리 되지 않는 [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 이벤트에서 올바릅니다. 따라서 디버거가 도우미 스레드의 스레드 id를 확인 하 고 사용자 로부터 숨길 수 있습니다. 관리 되지 않는 `ICorDebugManagedCallback::CreateThread` 이벤트 중에 도우미 스레드로 식별 되는 스레드는 관리 되는 사용자 코드를 실행 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug 있습니다. CorDebug .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
