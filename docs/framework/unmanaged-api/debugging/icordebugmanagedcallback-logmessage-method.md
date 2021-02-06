---
description: '자세히 알아보기: ICorDebugManagedCallback:: LogMessage 메서드'
title: ICorDebugManagedCallback::LogMessage 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 199f1f5dca7889a62ef351b4a2731fdb360768d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660520"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>ICorDebugManagedCallback::LogMessage 메서드

CLR (공용 언어 런타임) 관리 스레드가 클래스의 메서드를 호출 하 여 이벤트를 기록 한다고 디버거에 알립니다 <xref:System.Diagnostics.EventLog> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pAppDomain`  
 진행 이벤트를 기록한 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `lLevel`  
 진행 이벤트 로그에 기록 된 설명 메시지의 심각도 수준을 나타내는 [LoggingLevelEnum](logginglevelenum-enumeration.md) 열거형의 값입니다.  
  
 `pLogSwitchName`  
 진행 추적 스위치의 이름에 대 한 포인터입니다.  
  
 `pMessage`  
 진행 이벤트 로그에 기록 된 메시지에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
