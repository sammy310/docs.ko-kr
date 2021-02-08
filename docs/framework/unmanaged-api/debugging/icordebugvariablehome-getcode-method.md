---
description: '자세히 알아보기: ICorDebugVariableHome:: GetCode 메서드'
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
ms.openlocfilehash: e3ff96816e580fe3cd1cee782dc5bd4166f08a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794639"
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
  
## <a name="see-also"></a>참고 항목

- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
