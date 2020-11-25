---
title: ICorDebugExceptionDebugEvent::GetFlags 메서드
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 02a20b54b7fecc711bda010c6916fe036cf20dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729605"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a>ICorDebugExceptionDebugEvent::GetFlags 메서드

예외를 가로챌 수 있는지 여부를 나타내는 플래그를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pdwFlags`  
 제한이 예외를 가로챌 수 있는지 여부를 나타내는 [Cordebugexceptionflags](cordebugexceptionflags-enumeration.md) 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugExceptionDebugEvent 인터페이스](icordebugexceptiondebugevent-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
