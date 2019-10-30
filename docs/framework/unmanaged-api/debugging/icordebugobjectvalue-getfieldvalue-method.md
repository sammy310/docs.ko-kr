---
title: ICorDebugObjectValue::GetFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095888"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue 메서드
이 개체 값에 대해 지정 된 클래스의 지정 된 필드 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pClass`  
 진행 필드 값을 가져올 클래스를 나타내는 "ICorDebugClass" 개체에 대 한 포인터입니다.  
  
 `fieldDef`  
 진행 필드를 설명 하는 메타 데이터를 참조 하는 `mdFieldDef` 토큰입니다.  
  
 `ppValue`  
 제한이 지정 된 필드의 값을 나타내는 "ICorDebugValue" 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `pClass` 매개 변수에 지정 된 클래스는 개체 값 클래스의 계층 구조에 있어야 하 고 필드는 해당 클래스의 필드 여야 합니다.  
  
 `GetFieldValue` 메서드는 제네릭 개체와 제네릭 클래스에 대해 계속 성공 합니다. 예를 들어 MyDictionary\<V >가 사전\<문자열, V >에서 상속 되 고 개체 값이 MyDictionary\<int32 > 형식인 경우, 사전 `ICorDebugClass` K\<에 대 한 > 개체를 전달 하면 V가 사전\<문자열, int32 >입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조
