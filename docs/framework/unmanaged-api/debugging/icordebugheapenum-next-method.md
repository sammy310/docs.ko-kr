---
title: ICorDebugHeapEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 1beb69bfaad9acb9c269ad8becb81bea64edb6a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138465"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next 메서드
관리 되는 힙의 개체에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 개체 수입니다.  
  
 개체  
 제한이 각각 관리 되는 힙의 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체를 가리키는 포인터의 배열입니다.  
  
 pceltFetched  
 제한이 `objects`에서 실제로 반환 된 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체 수에 대 한 포인터입니다. `celt`가 1이면 이 값은 `null`일 수 있습니다.  
  
## <a name="remarks"></a>주의  
 `COR_HEAPOBJECT.type` 필드는 중첩된 참조 수가 계산되는 COM 인터페이스의 식별자입니다. 이 참조는 `ICorDebugHeapEnum::Next` 호출자가 해제해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugHeapEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
