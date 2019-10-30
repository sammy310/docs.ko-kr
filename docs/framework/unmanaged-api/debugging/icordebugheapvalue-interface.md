---
title: ICorDebugHeapValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 4f87065fc4a3d80a8363f3ae2fbb76c29f3d9b96
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138412"
---
# <a name="icordebugheapvalue-interface"></a>ICorDebugHeapValue 인터페이스

CLR (공용 언어 런타임) 가비지 수집기에 의해 수집 된 개체를 나타내는 "ICorDebugValue"의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateRelocBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|구현되지 않았습니다.|  
|[IsValid 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|이 `ICorDebugHeapValue` 나타내는 개체가 유효한 지 또는 가비지 수집기에 의해 회수 되었는지 여부를 나타내는 값을 가져옵니다. 이 메서드는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
