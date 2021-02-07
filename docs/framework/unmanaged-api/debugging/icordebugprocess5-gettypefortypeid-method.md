---
description: '자세히 알아보기: ICorDebugProcess5:: GetTypeForTypeID 메서드'
title: ICorDebugProcess5::GetTypeForTypeID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: a18543b0afc867dc3796264ac1d08a775c73ca59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746375"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>ICorDebugProcess5::GetTypeForTypeID 메서드

형식 식별자를 ICorDebugType 값으로 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `id`  
 진행 유형 식별자입니다.  
  
 `ppType`  
 제한이 ICorDebugType 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 경우에 따라 형식 식별자를 반환 하는 메서드는 null 값을 반환할 수 있습니다 `COR_TYPEID` . 이 값이 인수로 전달 되 면 `id` `GetTypeForTypeID` 메서드가 실패 하 고이 반환 됩니다 `E_FAIL` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
