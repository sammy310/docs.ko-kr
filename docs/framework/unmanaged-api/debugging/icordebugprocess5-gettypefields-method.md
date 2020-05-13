---
title: ICorDebugProcess5::GetTypeFields 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: a2c7f7b722abac6acf71d3b64276862441695a5f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212791"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields 메서드
형식에 속하는 필드에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `id`  
 진행 필드 정보를 검색할 형식의 식별자입니다.  
  
 `celt`  
 진행 필드 정보를 검색할 [COR_FIELD](cor-field-structure.md) 개체의 수입니다.  
  
 `fields`  
 제한이 형식에 속하는 필드에 대 한 정보를 제공 하는 [COR_FIELD](cor-field-structure.md) 개체의 배열입니다.  
  
 `pceltNeeded`  
 제한이 에 포함 된 [COR_FIELD](cor-field-structure.md) 개체 수에 대 한 포인터입니다 `fields` .  
  
## <a name="remarks"></a>설명  
 `celt`매개 변수는 메서드가 필드 정보를 채우는 데 사용 하는 필드의 수를 지정 합니다 `fields` .이 필드의 값은 필드의 값에 해당 해야 합니다 `COR_TYPE_LAYOUT::numFields` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
