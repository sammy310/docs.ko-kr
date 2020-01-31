---
title: ICorDebugExceptionObjectCallStackEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782802"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum 인터페이스
예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다. 이 인터페이스는 ICorDebugEnum 인터페이스의 서브클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md)|예외 개체의 호출 스택에 대 한 정보를 포함 하는 지정 된 수의 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 `ICorDebugExceptionObjectCallStackEnum` 인터페이스는 ICorDebugEnum 인터페이스를 구현 합니다.  
  
 `ICorDebugExceptionObjectCallStackEnum` 인스턴스는 [ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) 메서드를 호출 하 여 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체로 채워집니다. [ICorDebugExceptionObjectCallStackEnum:: Next](icordebugexceptionobjectcallstackenum-next-method.md) 메서드를 호출 하 여 컬렉션의 호출 스택 항목을 열거할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
