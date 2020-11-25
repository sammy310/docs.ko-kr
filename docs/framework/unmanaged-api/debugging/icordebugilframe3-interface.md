---
title: ICorDebugILFrame3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: dab5329086971b9349deaf84535fa251744f3cf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724990"
---
# <a name="icordebugilframe3-interface"></a>ICorDebugILFrame3 인터페이스

함수의 반환 값을 캡슐화하는 메서드를 제공합니다. `ICorDebugILFrame3` 는 ICorDebugILFrame 및 ICorDebugILFrame2 인터페이스의 논리적 확장입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReturnValueForILOffset 메서드](icordebugilframe3-getreturnvalueforiloffset-method.md)|함수의 반환 값을 캡슐화 하는 ICorDebugValue 개체를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugCode3 인터페이스](icordebugcode3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
