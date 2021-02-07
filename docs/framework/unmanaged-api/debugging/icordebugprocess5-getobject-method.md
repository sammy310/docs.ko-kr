---
description: '자세히 알아보기: ICorDebugProcess5:: GetObject 메서드'
title: ICorDebugProcess5::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: 4e295e1afc19cc5b9ca763b04b05097d48f0302c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746362"
---
# <a name="icordebugprocess5getobject-method"></a>ICorDebugProcess5::GetObject 메서드

개체 주소를 "ICorDebugObjectValue" 개체로 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `addr`  
 진행 개체 주소입니다.  
  
 `ppObject`  
 제한이 "ICorDebugObjectValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `addr`가 유효한 관리 되는 개체를 가리키지 않는 경우이 `GetObject` 메서드는를 반환 `E_FAIL` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
