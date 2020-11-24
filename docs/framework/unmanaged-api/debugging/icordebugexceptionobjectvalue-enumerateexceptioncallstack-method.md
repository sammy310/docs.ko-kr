---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 101151469e2eece20afe289c9d95387ce6dc7c6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672125"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack 메서드

예외 개체에 포함 된 호출 스택에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 ppCallStackEnum  
 제한이 관리 되는 예외 개체에 대 한 스택 추적 열거자 인 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 호출 스택 정보를 사용할 수 없는 경우 메서드는을 반환 하 `S_OK` 고 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) 는 길이가 0 인 유효한 열거자입니다. 메서드가 스택 추적 정보를 검색할 수 없는 경우 반환 값은이 `E_FAIL` 고 열거자가 반환 되지 않습니다.  
  
 [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) 개체는 `_stackTrace` exception 개체의 필드에서 스택 추적 데이터를 디코딩하는 역할을 담당 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugExceptionObjectValue 인터페이스](icordebugexceptionobjectvalue-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
