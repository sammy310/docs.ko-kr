---
title: CorDebugBlockingReason 열거형
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672853"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason 열거형

지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`BLOCKING_NONE`|내부 전용입니다.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|스레드에서 개체에 대 한 모니터 잠금과 연결 된 임계 영역을 가져오려고 합니다. 일반적으로이는 또는 메서드 중 하나를 호출할 때 발생 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 합니다.|  
|`BLOCKING_MONITOR_EVENT`|스레드가 개체에 대 한 모니터 잠금과 연결 된 이벤트를 기다리고 있습니다. 일반적으로이는 메서드 중 하나를 호출할 때 발생 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` 합니다.|  
  
## <a name="remarks"></a>설명  

 `BLOCKING_MONITOR_CRITICAL_SECTION`또는 `BLOCKING_MONITOR_EVENT` 멤버가 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체에서 사용 되는 경우 `pBlockingObject` 구조체의 멤버는 입력 되는 개체를 나타내는 "ICorDebugValue" 인터페이스를 가리킵니다. [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) 인터페이스를 구현 하는 것도 보장 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 열거형](debugging-enumerations.md)
- [디버깅](index.md)
