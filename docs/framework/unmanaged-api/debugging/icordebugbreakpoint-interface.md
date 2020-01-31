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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784371"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint 인터페이스

함수의 중단점 또는 값에 대 한 조사식을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Activate 메서드](icordebugbreakpoint-activate-method.md)|이 `ICorDebugBreakpoint`의 활성 상태를 설정 합니다.|  
|[IsActive 메서드](icordebugbreakpoint-isactive-method.md)|이 `ICorDebugBreakpoint` 활성화 되어 있는지 여부를 나타내는 값을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 중단점은 조건식을 직접 지원 하지 않습니다. 이러한 기능이 필요한 경우 디버거는 `ICorDebugBreakpoint`위에서 해당 기능을 구현 해야 합니다.  
  
 ICorDebugFunctionBreakpoint 인터페이스는 함수 내에서 중단점을 지원 하기 위해 `ICorDebugBreakpoint`를 확장 합니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
