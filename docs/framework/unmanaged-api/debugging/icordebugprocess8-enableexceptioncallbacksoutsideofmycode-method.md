---
description: '자세히 알아보기: ICorDebugProcess8:: EnableExceptionCallbacksOutsideOfMyCode 메서드'
title: ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: a85c9d62e5fb62fe620f0901509afa5a03504d4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691278"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드

[.NET Framework 4.6 이상 버전에서 지원 됨]  
  
 특정 형식의 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 예외 콜백을 사용 하거나 사용 하지 않도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>설명  

 `enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:  
  
- DEBUG_EXCEPTION_FIRST_CHANCE 예외로 인해 디버거 콜백이 발생하지 않습니다.  
  
- 예외가 사용자 코드로 이스케이프되지 않는 경우(즉, 예외 출처에서 예외 처리기로의 경로에 JustMyCode 또는 JMC로 표시된 메서드가 없음) DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외로 인해 디버거 콜백이 발생하지 않습니다.  
  
 `enableExceptionsOutsideOfJMC` 의 기본값은 `true`입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess8 인터페이스](icordebugprocess8-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
