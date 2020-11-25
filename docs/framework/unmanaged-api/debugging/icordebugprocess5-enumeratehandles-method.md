---
title: ICorDebugProcess5::EnumerateHandles 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 607847180cca039d4c71f26e446a17a14dc2fb9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724340"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles 메서드

프로세스의 개체 핸들에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>매개 변수  

 `types`  
 진행 컬렉션에 포함할 핸들의 형식을 지정 하는 [CorGCReferenceType](corgcreferencetype-enumeration.md) 값의 비트 조합입니다.  
  
 `ppENum`  
 제한이 가비지 수집 될 개체의 열거자 인 [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) 의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `EnumerateHandles` 는 핸들 테이블의 검사를 지 원하는 도우미 함수입니다. [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) 메서드와 유사 합니다. 단, 가비지 수집 되는 모든 개체를 사용 하 여 [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) 컬렉션을 채우지 않고 핸들 테이블의 핸들을 포함 하는 개체만 포함 합니다.  
  
 `types`매개 변수는 컬렉션에 포함할 핸들 형식을 지정 합니다. `types`[CorGCReferenceType](corgcreferencetype-enumeration.md) 열거형의 다음 세 가지 멤버 중 하나일 수 있습니다.  
  
- `CorHandleStrongOnly` (강력한 참조에만 해당).  
  
- `CorHandleWeakOnly` (약한 참조에만 해당).  
  
- `CorHandleAll` (모든 핸들).  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
