---
title: ICorDebugRegisterSet2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: c04bb3a7584fcb783af929e87713dbec67ad705f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712326"
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2 인터페이스

64 개 이상의 레지스터가 있는 하드웨어 플랫폼에 대 한 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 인터페이스의 기능을 확장 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRegisters 메서드](icordebugregisterset2-getregisters-method.md)|비트 마스크로 지정 된 각 레지스터의 값 (현재 코드를 실행 중인 컴퓨터)을 가져옵니다.|  
|[GetRegistersAvailable 메서드](icordebugregisterset2-getregistersavailable-method.md)|사용 가능한 레지스터의 비트맵을 제공 하는 바이트 배열을 가져옵니다.|  
|[SetRegisters 메서드](icordebugregisterset2-setregisters-method.md)|.NET Framework 버전 2.0에서 구현 되지 않았습니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
