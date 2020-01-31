---
title: ICorDebugValue3::GetSize64 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 7ae06d825565faff70b0c8be2ccbee5228737e41
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791097"
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 메서드
이 [ICorDebugValue3](icordebugvalue3-interface.md) 개체의 크기 (바이트)를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 pSize  
 제한이 이 개체의 크기 (바이트)에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 값의 형식이 참조 형식이 면이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.  
  
 `ICorDebugValue3::GetSize` 메서드는 출력 매개 변수 형식의 [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) 메서드와 다릅니다. [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md)에서 출력 매개 변수는 `ULONG32`입니다. `ICorDebugValue3::GetSize`에서는 `ULONG64`입니다. 이렇게 하면 [ICorDebugValue3](icordebugvalue3-interface.md) 인터페이스가 2gb를 초과 하는 배열의 크기를 보고할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugValue3 인터페이스](icordebugvalue3-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
