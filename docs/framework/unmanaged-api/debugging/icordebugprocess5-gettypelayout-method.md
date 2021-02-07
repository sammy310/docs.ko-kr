---
description: '자세히 알아보기: ICorDebugProcess5:: GetTypeLayout 메서드'
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
ms.openlocfilehash: d4496fa832b048dfc0bbe792aeb8fdcd460f5158
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746284"
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
  
## <a name="remarks"></a>설명  

 `ICorDebugProcess5::GetTypeLayout`메서드는 다양 한 [ICorDebugProcess5](icordebugprocess5-interface.md) 메서드에서 반환 하는 [COR_TYPEID](cor-typeid-structure.md)에 따라 개체에 대 한 정보를 제공 합니다. 이 정보는 메서드에 의해 채워지는 [COR_TYPE_LAYOUT](cor-type-layout-structure.md) 구조에 의해 제공 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [COR_TYPE_LAYOUT 구조체](cor-type-layout-structure.md)
- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
