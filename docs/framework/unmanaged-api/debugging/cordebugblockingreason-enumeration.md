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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54652727b4684d71068a19eb5eeb2e862f413f25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215081"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason 열거형
지정된 개체에서 스레드가 차단될 수 있는 이유를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`BLOCKING_MONITOR_CRITICAL_SECTION`|스레드 개체에 대 한 모니터 잠금과 사용 하 여 연결 하는 중요 섹션을 획득 하려고 합니다. 일반적으로이 경우 중 하나를 호출 합니다 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 메서드.|  
|`BLOCKING_MONITOR_EVENT`|개체에 대 한 모니터 잠금과 연관 된 이벤트에 대 한 스레드를 기다리고 있습니다. 일반적으로 이런 중 하나를 호출 하는 경우는 <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` 메서드.|  
  
## <a name="remarks"></a>설명  
 경우는 `BLOCKING_MONITOR_CRITICAL_SECTION` 또는 `BLOCKING_MONITOR_EVENT` 멤버는를 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조는 `pBlockingObject` 구조 가리킵니다 입력 중인 개체를 나타내는 "ICorDebugValue" 인터페이스 멤버 . 구현도 반드시 합니다 [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
