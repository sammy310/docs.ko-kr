---
title: ICorDebugManagedCallback2::MDANotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: 09a410f54ddf07c9a5f6bb7dd34f2aaf266e0734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704580"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification 메서드

코드 실행이 디버깅 중인 응용 프로그램에서 MDA (관리 디버깅 도우미)를 발견 한 알림을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pController`  
 진행 MDA가 발생 한 프로세스 또는 응용 프로그램 도메인을 노출 하는 ICorDebugController 인터페이스에 대 한 포인터입니다.  
  
 디버거는 컨트롤러의 프로세스 또는 응용 프로그램 도메인에 대 한 가정을 하지 않아야 합니다. 하지만 항상 인터페이스를 쿼리하여 결정을 내릴 수 있습니다.  
  
 `pThread`  
 진행 디버그 이벤트가 발생 한 관리 되는 스레드를 노출 하는 ICorDebugThread 인터페이스에 대 한 포인터입니다.  
  
 MDA가 관리 되지 않는 스레드에서 발생 한 경우의 값은 `pThread` null입니다.  
  
 MDA 개체 자체에서 OS (운영 체제) 스레드 ID를 가져와야 합니다.  
  
 `pMDA`  
 진행 MDA 정보를 노출 하는 [ICorDebugMDA](icordebugmda-interface.md) 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 MDA는 추론 경고 이며, 디버깅 중인 응용 프로그램의 실행을 계속 하기 위해 [ICorDebugController::](icordebugcontroller-continue-method.md) 를 호출 하는 경우를 제외 하 고 명시적 디버거 작업이 필요 하지 않습니다.  
  
 CLR (공용 언어 런타임)은 언제 든 지 어떤 mda가 발생 하는지, 어느 시점에서 어떤 데이터가 지정 된 MDA에 있는지를 확인할 수 있습니다. 따라서 디버거는 특정 MDA 패턴이 필요한 기능을 빌드하지 않아야 합니다.  
  
 Mda가 발생 한 후 mda가 큐에 대기 되 고 즉시 실행 될 수 있습니다. 런타임에서 mda를 발생 시킬 때 mda를 실행 하는 대신 MDA를 실행 하는 안전한 지점에 도달할 때까지 대기 해야 하는 경우이 문제가 발생할 수 있습니다. 또한 런타임은 대기 중인 콜백 집합 하나에서 많은 Mda를 실행할 수 있습니다 ("연결" 이벤트 작업과 유사).  
  
 디버거는 콜백에서 반환 된 직후 인스턴스에 대 한 참조를 해제 `ICorDebugMDA` 하 여 `MDANotification` CLR이 MDA에서 사용 하는 메모리를 재활용할 수 있도록 해야 합니다. 인스턴스를 해제 하면 많은 Mda가 발생 하는 경우 성능이 향상 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [관리 디버깅 도우미를 사용하여 오류 진단](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2 인터페이스](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
