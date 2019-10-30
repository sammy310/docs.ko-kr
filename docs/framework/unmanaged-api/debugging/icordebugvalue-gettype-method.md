---
title: ICorDebugValue::GetType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137071"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType 메서드
이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pType`  
 제한이 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 개체가 복잡 한 런타임 형식이 면 해당 형식은 `ICorDebugValue` 인터페이스의 적절 한 서브 클래스를 통해 검사할 수 있습니다. 예를 들어 `ICorDebugValue`에서 상속 되는 "ICorDebugObjectValue"은 복합 형식을 나타냅니다.  
  
 `GetType` 및 [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 합니다. 둘 다 제네릭 인식 [ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) 메서드로 대체 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
