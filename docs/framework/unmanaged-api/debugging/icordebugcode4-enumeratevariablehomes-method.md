---
description: '자세히 알아보기: ICorDebugCode4:: EnumerateVariableHomes 메서드'
title: 'ICorDebugCode4:: EnumerateVariableHomes 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 58f5f9063cd22356efd3a77ece9fb43b6b4c1062
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710961"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a>ICorDebugCode4:: EnumerateVariableHomes 메서드

함수의 지역 변수 및 인수에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppEnum`  
 함수의 지역 변수 및 인수에 대 한 열거자 인 [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface 개체는 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 열거할 수 있도록 하는 "ICorDebugEnum" 인터페이스에서 파생 된 표준 열거자입니다. 함수의 다른 지점에 다른 홈이 있는 경우 컬렉션은 동일한 슬롯 또는 인수 인덱스에 대해 여러 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugCode4 인터페이스](icordebugcode4-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
