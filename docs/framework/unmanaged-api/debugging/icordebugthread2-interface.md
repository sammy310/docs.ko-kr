---
title: ICorDebugThread2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: fd4ad536d7d3df2b8f91f206459122cf083c8b9c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691138"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2 인터페이스

ICorDebugThread 인터페이스에 대 한 논리적 확장으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetActiveFunctions 메서드](icordebugthread2-getactivefunctions-method.md)|스레드의 프레임에 있는 활성 함수에 대 한 데이터를 포함 하는 COR_ACTIVE_FUNCTION 인스턴스의 배열을 가져옵니다.|  
|[GetConnectionID 메서드](icordebugthread2-getconnectionid-method.md)|이에 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2` .|  
|[GetTaskID 메서드](icordebugthread2-gettaskid-method.md)|이에 대 한 작업 식별자를 가져옵니다 `ICorDebugThread2` .|  
|[GetVolatileOSThreadID 메서드](icordebugthread2-getvolatileosthreadid-method.md)|이에 대 한 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2` .|  
|[InterceptCurrentException 메서드](icordebugthread2-interceptcurrentexception-method.md)|디버거가 스레드의 현재 예외를 가로챌 수 있도록 허용 합니다.|  
  
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
