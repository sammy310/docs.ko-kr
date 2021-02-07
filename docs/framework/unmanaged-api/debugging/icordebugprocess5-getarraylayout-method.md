---
description: '자세히 알아보기: ICorDebugProcess5:: GetArrayLayout 메서드'
title: ICorDebugProcess5::GetArrayLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: c82b296da3a367f5307240225a560af67a56c866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746401"
---
# <a name="icordebugprocess5getarraylayout-method"></a>ICorDebugProcess5::GetArrayLayout 메서드

배열 형식의 레이아웃에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>매개 변수  

 `id`  
 진행 레이아웃이 필요한 배열을 지정 하는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.  
  
 `pLayout`  
 제한이 메모리의 배열 레이아웃에 대 한 정보를 포함 하는 [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
