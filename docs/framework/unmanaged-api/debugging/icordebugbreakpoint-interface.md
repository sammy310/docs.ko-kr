---
title: ICorDebugBreakpoint 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a68e061c6def61746ee65f8a25818f8dbcd785b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159733"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint 인터페이스

함수 또는 값에 대 한 조사식 위치에서 중단점을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Activate 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|이 활성 상태를 설정 `ICorDebugBreakpoint`합니다.|  
|[IsActive 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|나타내는 값을 가져옵니다 여부를이 `ICorDebugBreakpoint` 활성화 되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 중단점 조건 식을 직접 지원 하지 않습니다. 이러한 기능을 원하는 경우 디버거를 구현 해야 위에 `ICorDebugBreakpoint`합니다.  
  
 ICorDebugFunctionBreakpoint 인터페이스 확장 `ICorDebugBreakpoint` 함수 내에서 중단점을 지원 하도록 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
