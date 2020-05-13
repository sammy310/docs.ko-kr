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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207584"
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
 진행 `mdFieldDef`필드를 설명 하는 메타 데이터를 참조 하는 토큰입니다.  
  
 `ppValue`  
 제한이 지정 된 필드의 값을 나타내는 "ICorDebugValue" 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 매개 변수에 지정 된 클래스는 `pClass` 개체 값의 클래스 계층 구조에 있어야 하 고 필드는 해당 클래스의 필드 여야 합니다.  
  
 `GetFieldValue`메서드는 제네릭 개체 및 제네릭 클래스에 대해 여전히 성공 합니다. 예를 들어 MyDictionary \< v> \< 가 사전 문자열, V>에서 상속 되 고 개체 값이 mydictionary> int32 형식이 면, \< V>는 사전 `ICorDebugClass` \< 문자열 int32>의 필드를 성공적으로 가져옵니다 \< .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목
