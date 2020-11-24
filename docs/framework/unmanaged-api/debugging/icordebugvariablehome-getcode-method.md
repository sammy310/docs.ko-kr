---
title: 'ICorDebugVariableHome:: GetCode 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684228"
---
# <a name="icordebugvariablehomegetcode-method"></a>ICorDebugVariableHome:: GetCode 메서드

이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppCode`  
 제한이 이 [ICorDebugVariableHome](icordebugvariablehome-interface.md) 개체를 포함 하는 "ICorDebugCode" 인스턴스의 주소에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
