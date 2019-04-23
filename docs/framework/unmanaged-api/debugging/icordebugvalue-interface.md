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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227823"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue 인터페이스
디버깅 중인 프로세스에서 값을 나타냅니다. 읽기 또는 쓰기 값 값일 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|이 메서드가 현재 구현 되지 않습니다.|  
|[GetAddress 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|이 주소를 가져옵니다 `ICorDebugValue` 디버깅 중인 프로세스에 있는 개체입니다.|  
|[GetSize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue` 개체입니다.|  
|[GetType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|이 기본 형식을 가져옵니다 `ICorDebugValue` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 반환 될 때 값 개체의 소유권 전달 됩니다. 수신자는 개체를 사용 하 여 완료 되 면 개체에서 참조를 제거 하는 일을 담당 합니다.  
  
 값에서 검색 된 위치에 따라 값 남아 있을 수 없습니다 유효한 프로세스 다시 시작 된 후입니다. 따라서 일반적으로 해서는 안 됩니다 수 있는 값의 호출을 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugValue3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
