---
title: ICorDebugManagedCallback::ExitProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130782"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess 메서드
프로세스가 종료 되었음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pProcess`  
 진행 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `ExitProcess` 이벤트는 계속할 수 없습니다. 프로세스가 중지 된 상태로 표시 되는 동안이 이벤트는 다른 이벤트에 대해 비동기적으로 실행 될 수 있습니다. 이러한 문제는 일반적으로 일부 외부 force로 인해 중지 되는 동안 프로세스가 종료 되는 경우에 발생할 수 있습니다.  
  
 CLR (공용 언어 런타임)에서 이미 관리 되는 콜백을 디스패치할 경우이 이벤트는 해당 콜백이 반환 될 때까지 지연 됩니다.  
  
 `ExitProcess` 이벤트는 종료 시 호출 되도록 보장 되는 유일한 exit/unload 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
