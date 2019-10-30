---
title: ICorDebugThread4::GetBlockingObjects 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: e4d5582b7a3df16db58ea0ed001dcbffcdcaab79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122456"
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects 메서드
스레드 차단 정보를 제공 하는 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조의 순서가 지정 된 열거형을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppBlockingObjectEnum`  
 제한이 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조체의 정렬 된 열거에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 반환 된 열거형의 첫 번째 요소는 스레드를 차단 하는 첫 번째 구조체에 해당 합니다. 두 번째 요소는 첫 번째에서 차단 될 때 APC (비동기 프로시저 호출)를 실행 하는 동안 발생 한 차단 항목에 해당 합니다.  
  
 열거형은 현재 동기화 된 상태의 기간에 대해서만 유효 합니다.  
  
 디버기가 synchronized 상태에 있는 동안에는이 메서드를 호출 해야 합니다.  
  
 `ppBlockingObjectEnum` 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.  
  
 스레드가 차단 되 고 오류를 확인할 수 없는 경우 메서드는 실패를 나타내는 HRESULT를 반환 합니다. 그렇지 않으면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugThread4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
