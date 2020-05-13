---
title: ICorDebugProcess 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
ms.openlocfilehash: ab48efccc88787f099a182627777db95304cdc3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212076"
---
# <a name="icordebugprocess-interface"></a>ICorDebugProcess 인터페이스
관리 코드를 실행하는 프로세스를 나타냅니다. 이 인터페이스는 ICorDebugController의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ClearCurrentException 메서드](icordebugprocess-clearcurrentexception-method.md)|지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.|  
|[EnableLogMessages 메서드](icordebugprocess-enablelogmessages-method.md)|디버거로 로그 메시지 보내기를 사용 하거나 사용 하지 않도록 설정 합니다.|  
|[EnumerateAppDomains 메서드](icordebugprocess-enumerateappdomains-method.md)|프로세스의 모든 응용 프로그램 도메인을 열거 합니다.|  
|[EnumerateObjects 메서드](icordebugprocess-enumerateobjects-method.md)|구현되지 않았습니다.|  
|[GetHandle 메서드](icordebugprocess-gethandle-method.md)|프로세스에 대 한 핸들을 가져옵니다.|  
|[GetHelperThreadID 메서드](icordebugprocess-gethelperthreadid-method.md)|디버거의 내부 도우미 스레드에 대 한 OS (운영 체제) 스레드 ID를 가져옵니다.|  
|[GetID 메서드](icordebugprocess-getid-method.md)|프로세스의 OS (운영 체제) ID를 가져옵니다.|  
|[GetObject 메서드](icordebugprocess-getobject-method.md)|구현되지 않았습니다.|  
|[GetThread 메서드](icordebugprocess-getthread-method.md)|지정 된 OS 스레드 ID를 가진 ICorDebugThread 인스턴스를 가져옵니다.|  
|[GetThreadContext 메서드](icordebugprocess-getthreadcontext-method.md)|지정 된 스레드에 대 한 컨텍스트를 가져옵니다.|  
|[IsOSSuspended 메서드](icordebugprocess-isossuspended-method.md)|디버거가 프로세스를 중지 한 결과로 스레드가 일시 중단 되었는지 여부를 확인 합니다.|  
|[IsTransitionStub 메서드](icordebugprocess-istransitionstub-method.md)|관리 코드로의 전환을 유발 하는 스텁이 스텁 내에 있는지 여부를 확인 합니다.|  
|[ModifyLogSwitch 메서드](icordebugprocess-modifylogswitch-method.md)|지정 된 로그 스위치의 심각도 수준을 설정 합니다.|  
|[ReadMemory 메서드](icordebugprocess-readmemory-method.md)|프로세스에서 메모리를 읽습니다.|  
|[SetThreadContext 메서드](icordebugprocess-setthreadcontext-method.md)|지정 된 스레드에 대 한 컨텍스트를 설정 합니다.|  
|[ThreadForFiberCookie 메서드](icordebugprocess-threadforfibercookie-method.md)|사용되지 않습니다.|  
|[WriteMemory 메서드](icordebugprocess-writememory-method.md)|프로세스의 메모리 영역에 데이터를 씁니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebug 인터페이스](icordebug-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
