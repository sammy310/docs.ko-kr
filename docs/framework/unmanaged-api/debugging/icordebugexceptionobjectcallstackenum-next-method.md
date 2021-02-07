---
description: '자세히 알아보기: ICorDebugExceptionObjectCallStackEnum:: Next 메서드'
title: ICorDebugExceptionObjectCallStackEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: df68eb6e4794d294fc39dd943065582dc52a58a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693319"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a>ICorDebugExceptionObjectCallStackEnum::Next 메서드

예외 개체의 호출 스택 정보를 포함 하는 지정 된 수의 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `celt`  
 진행 검색할 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스 수입니다.  
  
 `values`  
 제한이 각가 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 개체를 가리키는 포인터의 배열입니다.  
  
 `pceltFetched`  
 제한이 실제로 반환 된 [Cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) 인스턴스 수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugExceptionObjectCallStackEnum 인터페이스](icordebugexceptionobjectcallstackenum-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
