---
title: ICorDebugManagedCallback::LogSwitch 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a011485453999b9d764716356eebb2a5462f7bb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078839"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch 메서드
공용 언어 런타임 (CLR) 관리 되는 스레드에서의 메서드를 호출에 디버거에 알립니다는 <xref:System.Diagnostics.Switch> 클래스를 만들기, 수정 또는 디버깅/추적 스위치를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>매개 변수  
 `PAppDomain`  
 [in] ICorDebugAppDomain 개체 생성, 수정 또는 디버깅/추적 스위치를 삭제 하는 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 포인터입니다.  
  
 `pThread`  
 [in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `lLevel`  
 [in] 이벤트 로그에 기록 된 설명이 포함 된 메시지의 심각도 나타내는 값입니다.  
  
 `ulReason`  
 [in] 값을 [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) 디버깅/추적 스위치에서 수행할 작업을 나타내는 열거형입니다.  
  
 `pLogSwitchName`  
 [in] 디버깅/추적 스위치의 이름에 대 한 포인터입니다.  
  
 `pParentName`  
 [in] 디버깅/추적 스위치의 부모 이름에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
