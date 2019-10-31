---
title: ICorDebugValue::GetSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d6caa02333229bcd49f4c6ccf8b93265181a0b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137092"
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize 메서드
이 "ICorDebugValue" 개체의 크기 (바이트)를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pSize`  
 제한이 이 값 개체의 크기 (바이트)입니다.  
  
## <a name="remarks"></a>주의  
 값의 형식이 참조 형식인 경우이 메서드는 개체의 크기가 아니라 포인터의 크기를 반환 합니다.  
  
 `ICorDebugValue::GetSize` 메서드는 64 비트 플랫폼에서 4gb 보다 큰 개체에 대 한 `COR_E_OVERFLOW`을 반환 합니다. 4gb 보다 큰 개체에 대해 [ICorDebugValue3:: GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드를 대신 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [GetSize64 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
