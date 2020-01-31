---
title: ICorDebugComObjectValue::GetCachedInterfacePointers 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783958"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers 메서드
현재 RCW (런타임 호출 가능 래퍼)에 캐시 된 원시 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bIInspectableOnly`  
 진행 메서드가 RCW (런타임 호출 가능 래퍼)에 의해 캐시 되는 Windows 런타임 인터페이스 (`IInspectable` 인터페이스) 또는 모든 COM 인터페이스만 반환할지 여부를 나타내는 값입니다.  
  
 `celt`  
 진행 주소를 검색할 개체의 수입니다.  
  
 `pceltFetched`  
 제한이 `ptrs`에서 실제로 반환 된 `CORDB_ADDRESS` 값 수에 대 한 포인터입니다.  
  
 `ptrs`  
 캐시 된 인터페이스 개체의 주소를 포함 하는 `CORDB_ADDRESS` 값 배열의 시작 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugComObjectValue 인터페이스](icordebugcomobjectvalue-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
