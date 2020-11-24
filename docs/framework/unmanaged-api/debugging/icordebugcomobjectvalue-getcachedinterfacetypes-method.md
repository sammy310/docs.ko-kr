---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: f5f0f11683043f1c287dd3ca3071830bcfb46502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677559"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>ICorDebugComObjectValue::GetCachedInterfaceTypes 메서드

현재 개체가 캐스팅 되었거나로 사용 된 인터페이스 형식에 대 한 열거자를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>매개 변수  

 `bIInspectableOnly`  
 진행 메서드가 `IInspectable` RCW (런타임 호출 가능 래퍼)가 캐시 하는 Windows 런타임 인터페이스 (인터페이스) 또는 모든 COM 인터페이스만 반환 하는지 여부를 나타내는 값입니다.  
  
 `ppInterfacesEnum`  
 제한이 에 따라 필터링 된 캐시 된 인터페이스 형식을 나타내는 ICorDebugType 개체에 대 한 액세스를 제공 하는 ICorDebugTypeEnum 열거자의 주소에 대 한 포인터입니다 `bIInspectableOnly` .  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugComObjectValue 인터페이스](icordebugcomobjectvalue-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
