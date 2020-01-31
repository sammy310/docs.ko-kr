---
title: ICorDebugThread4::HadUnhandledException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: f558a4c94afeb69f58605958ddcb91e4be772c39
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791344"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException 메서드
스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppBlockingObjectEnum`  
 제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 정렬 된 열거 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|스레드의 생성 후에 처리 되지 않은 예외가 발생 했습니다.|  
|S_FALSE|스레드에 처리 되지 않은 예외가 발생 한 적이 없습니다.|  
  
## <a name="remarks"></a>주의  
 이 메서드는 스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다. 처리 되지 않은 예외 콜백이 트리거하거나 네이티브 JIT 연결이 시작 될 때이 메서드는 S_OK 반환 하도록 보장 됩니다. [ICorDebugThread 예외](icordebugthread-getcurrentexception-method.md) 메서드에서 처리 되지 않은 예외를 반환 한다는 보장이 없습니다. 그러나 처리 되지 않은 예외 콜백을 가져온 후 또는 네이티브 JIT 연결에 프로세스를 아직 계속 하지 않은 경우에는이 작업을 수행할 수 있습니다. 또한 네이티브 JIT 연결이 트리거되는 동안 처리 되지 않은 예외가 있는 스레드가 둘 이상 있을 수 있습니다. 이러한 경우 JIT 연결을 트리거한 예외를 확인할 수 있는 방법이 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugThread4 인터페이스](icordebugthread4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
