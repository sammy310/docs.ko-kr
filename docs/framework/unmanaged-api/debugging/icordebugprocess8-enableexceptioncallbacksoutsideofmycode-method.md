---
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: b6bfd258f35f19719be5e5169a1edc22a358371c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123381"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
[.NET Framework 4.6 이상 버전에서 지원 됨]  
  
 특정 형식의 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>주의  
 `enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:  
  
- DEBUG_EXCEPTION_FIRST_CHANCE 예외로 인해 디버거에 대 한 콜백이 발생 하지 않습니다.  
  
- 예외가 사용자 코드로 이스케이프 되지 않은 경우 (즉, 예외 원본에서 예외 처리기로의 경로에 JustMyCode 또는 JMC로 표시 된 메서드가 없는 경우) DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외로 인해 디버거에 대 한 콜백이 발생 하지 않습니다.  
  
 `enableExceptionsOutsideOfJMC` 의 기본값은 `true`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess8 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
