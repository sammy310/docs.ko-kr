---
title: ICorDebugManagedCallback3::CustomNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209762"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>ICorDebugManagedCallback3::CustomNotification 메서드
사용자 지정 디버거 알림이 발생 했음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pThread`  
 진행 알림을 발생 시킨 스레드에 대 한 포인터입니다.  
  
 `pAppDomain`  
 진행 알림을 발생 시킨 스레드를 포함 하는 응용 프로그램 도메인에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) 메서드에 대 한 후속 호출에서는 메서드에 전달 된 스레드 개체를 검색 합니다 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> . [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) 메서드를 호출 하 여 스레드 개체의 형식을 이전에 사용 하도록 설정 해야 합니다. 디버거는 스레드 개체의 필드에서 유형별 매개 변수를 읽을 수 있으며 응답을 필드에 저장할 수 있습니다.  
  
 [ICorDebug](icordebug-interface.md) 인터페이스는 알림 또는 해당 콘텐츠 형식에 대 한 정책을 적용 하지 않으며, 알림의 의미 체계는 디버거, 응용 프로그램 및 .NET Framework 간의 계약을 엄격히 부과 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugManagedCallback3 인터페이스](icordebugmanagedcallback3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
