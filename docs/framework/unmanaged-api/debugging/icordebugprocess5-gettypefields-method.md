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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c2725c62105e92996bb2d8e79e8ff504904e9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948722"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields 메서드
형식에 속하는 필드에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `id`  
 [in] 식별자 인 필드 정보를 검색할 형식입니다.  
  
 `celt`  
 [in] 수가 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 필드 정보를 검색할 개체입니다.  
  
 `fields`  
 [out] 배열을 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 형식에 속하는 필드에 대 한 정보를 제공 하는 개체입니다.  
  
 `pceltNeeded`  
 [out] 개수에 대 한 포인터 [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) 에 포함 된 개체 `fields`합니다.  
  
## <a name="remarks"></a>설명  
 `celt` 필드를 채우는 메서드를 사용 하 여 필드 정보를 가져올 수를 지정 하는 매개 변수 `fields`의 값과 일치 해야 합니다 `COR_TYPE_LAYOUT::numFields` 필드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugProcess5 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
