---
title: ICorDebugProcess5::EnumerateGCReferences 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178614"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences 메서드
프로세스에서 가비지 수집되는 모든 개체에 대해 열거기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `enumerateWeakReferences`  
 【인】 약한 참조도 여과할지 여부를 나타내는 부울 값입니다. 이 경우 `enumerateWeakReferences` `ppEnum` 열거형에는 강력한 참조와 약한 참조가 모두 포함됩니다. `true` 있는 `enumerateWeakReferences` `false`경우 열거형에는 강력한 참조만 포함됩니다.  
  
 `ppEnum`  
 【아웃】 개체가 가비지 수집되는 열거형인 [ICorDebugGCReferenceEnum의](icordebuggcreferenceenum-interface.md) 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프로세스에서 관리되는 개체에 대한 전체 루팅 체인을 확인하는 방법을 제공하며 개체가 아직 살아 있는 이유를 확인하는 데 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
