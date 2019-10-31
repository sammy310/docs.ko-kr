---
title: ICorDebugMutableDataTarget 인터페이스
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: 682e927388d3392d970338314f97d46c9e57e760
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139331"
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget 인터페이스
[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스를 확장 하 여 변경 가능한 데이터 대상을 지원 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ContinueStatusChanged 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|지정된 스레드에서 해결되지 않은 디버그 이벤트의 연속 상태를 변경합니다.|  
|[SetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.|  
|[WriteVirtual 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|대상 프로세스 주소 공간에 메모리를 씁니다.|  
  
## <a name="remarks"></a>주의  
 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스에 대 한이 확장은 대상 프로세스를 수정 하려는 디버깅 도구에 의해 구현 될 수 있습니다. 예를 들어 라이브 침입 디버깅을 수행 합니다.  
  
 이러한 모든 메서드는 이 인터페이스를 구현하지 않거나 해당 메서드 호출에 실패해도 손실되는 핵심 검사 기반 디버깅 기능이 없다는 점에서 선택적입니다.  이러한 메서드의 모든 실패 `HRESULT`는 ICorDebug 메서드 호출의 `HRESULT`로 전파됩니다.  
  
 단일 ICorDebug 메서드 호출에서 여러 변경이 발생할 수 있으며, 관련 변경이 트랜잭션 방식으로 적용(전체 적용되거나 적용 안 함)되게 하는 메커니즘은 없습니다.  즉, 동일한 ICorDebug 호출에 대한 다른 변경이 성공한 후 특정 변경이 실패할 경우 대상 프로세스가 불일치 상태로 남겨지고 디버깅이 불안정해질 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
