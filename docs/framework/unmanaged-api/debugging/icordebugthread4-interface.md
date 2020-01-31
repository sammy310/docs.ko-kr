---
title: ICorDebugThread4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 0bb25d060853abb20316a344bae3755b2f8b4dc7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791331"
---
# <a name="icordebugthread4-interface"></a>ICorDebugThread4 인터페이스
스레드 차단 정보를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBlockingObjects 메서드](icordebugthread4-getblockingobjects-method.md)|스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.|  
|[HadUnhandledException 메서드](icordebugthread4-hadunhandledexception-method.md)|스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.|  
|[GetCurrentCustomDebuggerNotification 메서드](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|현재 스레드의 현재 [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) 개체를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 ICorDebugThread, ICorDebugThread2 및 [ICorDebugThread3](icordebugthread3-interface.md) 인터페이스를 논리적으로 확장 한 것입니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
