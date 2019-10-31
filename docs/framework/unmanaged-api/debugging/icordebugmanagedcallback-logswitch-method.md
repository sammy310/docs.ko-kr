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
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130690"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch 메서드
디버깅/추적 스위치를 만들거나 수정 하거나 삭제 하기 위해 CLR (공용 언어 런타임) 관리 스레드가 <xref:System.Diagnostics.Switch> 클래스에서 메서드를 호출 했음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 디버깅/추적 스위치를 만들거나, 수정 하거나, 삭제 한 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `lLevel`  
 진행 이벤트 로그에 기록 된 설명 메시지의 심각도 수준을 나타내는 값입니다.  
  
 `ulReason`  
 진행 디버깅/추적 스위치에 대해 수행 된 작업을 나타내는 [Logswitchcallreason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) 열거형의 값입니다.  
  
 `pLogSwitchName`  
 진행 디버깅/추적 스위치의 이름에 대 한 포인터입니다.  
  
 `pParentName`  
 진행 디버깅/추적 스위치의 부모 이름에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
