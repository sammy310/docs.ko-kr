---
title: ICorDebugStackWalk 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378900"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk 인터페이스
스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetContext 메서드](icordebugstackwalk-getcontext-method.md)|개체의 현재 프레임에 대 한 컨텍스트를 반환 합니다 `ICorDebugStackWalk` .|  
|[SetContext 메서드](icordebugstackwalk-setcontext-method.md)|`ICorDebugStackWalk`개체의 현재 컨텍스트를 스레드의 유효한 컨텍스트로 설정 합니다.|  
|[Next 메서드](icordebugstackwalk-next-method.md)|개체를 `ICorDebugStackWalk` 다음 프레임으로 이동 합니다.|  
|[GetFrame 메서드](icordebugstackwalk-getframe-method.md)|개체의 현재 프레임을 가져옵니다 `ICorDebugStackWalk` .|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
