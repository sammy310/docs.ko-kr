---
title: ICorDebugValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: b8d2e49031e59db0527de3c848d7d390095797bf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396787"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue 인터페이스
디버그 중인 프로세스의 값을 나타냅니다. 값은 읽기 또는 쓰기 값일 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](icordebugvalue-createbreakpoint-method.md)|현재 이 메서드는 구현되지 않습니다.|  
|[GetAddress 메서드](icordebugvalue-getaddress-method.md)|디버깅 중인이 개체의 주소를 가져옵니다 `ICorDebugValue` .|  
|[GetSize 메서드](icordebugvalue-getsize-method.md)|이 개체의 크기 (바이트)를 가져옵니다 `ICorDebugValue` .|  
|[GetType 메서드](icordebugvalue-gettype-method.md)|이 개체의 기본 형식을 가져옵니다 `ICorDebugValue` .|  
  
## <a name="remarks"></a>설명  
 일반적으로 값 개체의 소유권은 반환 될 때 전달 됩니다. 개체를 사용 하 여 작업이 완료 되 면 수신자는 개체에서 참조를 제거할 책임이 있습니다.  
  
 값이 검색 된 위치에 따라 프로세스가 다시 시작 된 후에는 값이 유효 하지 않을 수 있습니다. 따라서 일반적으로 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 메서드를 호출 하는 동안 값을 보유 하면 안 됩니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugValue3 인터페이스](icordebugvalue3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
