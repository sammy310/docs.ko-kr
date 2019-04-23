---
title: CorDebugBlockingObject 구조체
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143223"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 구조체
스레드가 차단 되는 특정 이유와 스레드를 차단 하는 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pBlockingObject`|스레드를 차단 하는 개체입니다. 이 개체는 현재 동기화 된 상태의 기간에만 유효 합니다. 예상할 수 있는 경우 두 스레드가 동일한 동기화 된 상태 내에서 동일한 개체에서 차단 되는 [icordebugvalue:: Getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) 동일한 값을 반환 하는 방법입니다. 그러나 인터페이스 수도 있고 해당 포인터 되지 않을 수 있습니다.|  
|`dwTimeout`|차단 작업 전에 시간을 밀리초 단위로 시간 초과 또는 무한 시간 초과 되지 않음을 나타내는 값을 됩니다. 시간 제한 값은 남아 있는 시간이 아닌 차단 작업에 대 한 총 기간을 지정 합니다.|  
|`blockingReason`|이 개체에 스레드가 차단 되는 이유입니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
