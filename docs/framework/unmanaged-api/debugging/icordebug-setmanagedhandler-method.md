---
title: ICorDebug::SetManagedHandler 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: 88a007654646ba42ebcaf1b42e002282a1040c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134059"
---
# <a name="icordebugsetmanagedhandler-method"></a>ICorDebug::SetManagedHandler 메서드
관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pCallback`  
 진행 이벤트 처리기 개체인 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `SetManagedHandler`를 만들 때 호출 해야 합니다.  
  
 `ICorDebugManagedCallback` 구현에 디버깅 중인 응용 프로그램에 대 한 디버깅 이벤트를 처리 하는 데 충분 한 인터페이스가 포함 되지 않은 경우 `SetManagedHandler` E_NOINTERFACE의 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
