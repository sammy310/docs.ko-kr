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
ms.openlocfilehash: c3120a0dd859f581e6356fc260043cb83250ae9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724834"
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
 진행 메서드가 `IInspectable` RCW (런타임 호출 가능 래퍼)에 의해 캐시 된 인터페이스 (인터페이스) 또는 모든 COM 인터페이스만 Windows 런타임 반환 하는지 여부를 나타내는 값입니다.  
  
 `celt`  
 진행 주소를 검색할 개체의 수입니다.  
  
 `pceltFetched`  
 제한이 `CORDB_ADDRESS` 에 실제로 반환 된 값 수에 대 한 포인터 `ptrs` 입니다.  
  
 `ptrs`  
 `CORDB_ADDRESS`캐시 된 인터페이스 개체의 주소를 포함 하는 값 배열의 시작 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugComObjectValue 인터페이스](icordebugcomobjectvalue-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
