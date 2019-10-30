---
title: ICorDebug::SetUnmanagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134041"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler 메서드
관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pCallback`  
 진행 관리 되지 않는 이벤트에 대 한 이벤트 처리기를 나타내는 [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체는 [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) 를 호출한 후 [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) 또는 [ICorDebug::D e버그 activeprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)를 호출 하기 전에 설정 해야 합니다. 그러나 레거시를 위해 첫 번째 네이티브 디버그 이벤트가 발생할 때까지 관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 설정할 필요가 없습니다. 특히 CREATE_SUSPENDED 플래그를 설정 `ICorDebug::CreateProcess` 경우 주 스레드를 다시 시작할 때까지 네이티브 디버그 이벤트를 발송할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
