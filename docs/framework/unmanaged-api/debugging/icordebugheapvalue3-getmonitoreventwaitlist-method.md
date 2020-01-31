---
title: ICorDebugHeapValue3::GetMonitorEventWaitList 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 15900fab59d172ada67d8aefeab698e1b44f808e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794384"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList 메서드
모니터 잠금과 연결 된 이벤트에서 큐에 대기 중인 스레드의 순서 있는 목록을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppThreadEnum`  
 제한이 정렬 된 스레드 목록을 제공 하는 ICorDebugThreadEnum 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|The list is not empty.|  
|S_FALSE|목록이 비어 있습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>주의  
 목록의 첫 번째 스레드는 <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>에 대 한 다음 호출에 의해 해제 되는 첫 번째 스레드입니다. 다음 호출에서 목록에 있는 다음 스레드가 해제 되는 식입니다.  
  
 목록이 비어 있지 않으면이 메서드는 S_OK 반환 합니다. 목록이 비어 있으면 메서드는 S_FALSE을 반환 합니다. 이 경우 열거형은 비어 있지만 여전히 유효 합니다.  
  
 두 경우 모두 열거 인터페이스는 현재 동기화 된 상태의 기간 동안만 사용할 수 있습니다. 그러나 스레드가 종료 될 때까지 분배 된에서 스레드의 인터페이스를 사용할 수 있습니다.  
  
 `ppThreadEnum` 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.  
  
 모니터를 대기 중인 스레드가 있는지 확인할 수 없는 오류가 발생 하는 경우이 메서드는 실패를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
