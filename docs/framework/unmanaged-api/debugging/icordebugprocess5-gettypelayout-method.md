---
title: ICorDebugProcess5::GetTypeLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792306"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout 메서드
형식 식별자를 기반으로 메모리에 있는 개체의 레이아웃에 대 한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>매개 변수  
 `id`  
 진행 레이아웃이 필요한 형식을 지정 하는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.  
  
 `pLayout`  
 제한이 메모리에 있는 개체의 레이아웃에 대 한 정보를 포함 하는 [COR_TYPE_LAYOUT](cor-type-layout-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `ICorDebugProcess5::GetTypeLayout` 메서드는 여러 다른 [ICorDebugProcess5](icordebugprocess5-interface.md) 메서드에서 반환 되는 [COR_TYPEID](cor-typeid-structure.md)를 기반으로 하는 개체에 대 한 정보를 제공 합니다. 이 정보는 메서드에 의해 채워지는 [COR_TYPE_LAYOUT](cor-type-layout-structure.md) 구조에 의해 제공 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [COR_TYPE_LAYOUT 구조체](cor-type-layout-structure.md)
- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
