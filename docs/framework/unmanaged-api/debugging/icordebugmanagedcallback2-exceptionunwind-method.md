---
title: ICorDebugManagedCallback2::ExceptionUnwind 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: fa317e1217ac0a9ca46bfeb312446534b1fca63a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131557"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>ICorDebugManagedCallback2::ExceptionUnwind 메서드
예외 해제 프로세스 중에 상태 알림을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAppDomain`  
 진행 예외가 throw 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `dwEventType`  
 진행 해제 단계에서 콜백이 신호를 받는 이벤트를 지정 하는 CorDebugExceptionUnwindCallbackType 열거형의 값입니다.  
  
 `dwFlags`  
 진행 예외에 대 한 추가 정보를 지정 하는 [Cordebugexceptionflags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>주의  
 `ExceptionUnwind`는 예외 처리 프로세스의 해제 단계 중에 다양 한 지점에서 호출 됩니다. 단일 예외를 해제 하는 동안 `ExceptionUnwind`를 두 번 이상 호출할 수 있습니다.  
  
 `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED 인 경우 명령 포인터는 예외를 발생 시킨 명령의 이전 시퀀스 위치 (이전에 몇 가지 명령 일 수 있음)에서 스레드의 리프 프레임에 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
