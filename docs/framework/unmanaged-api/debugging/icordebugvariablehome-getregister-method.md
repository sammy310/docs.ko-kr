---
title: 'ICorDebugVariableHome:: GetRegister 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790985"
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome:: GetRegister 메서드
`VLT_REGISTER`위치 형식의 변수와 `VLT_REGISTER_RELATIVE`위치 형식의 변수에 대 한 기본 레지스터를 포함 하는 레지스터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pRegister`  
 제한이 `VLT_REGISTER`위치 형식이 있는 변수의 등록을 나타내는 CorDebugRegister 열거형 값과 위치 형식이 `VLT_REGISTER_RELATIVE`인 변수에 대 한 기본 레지스터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드는 다음 값을 반환 합니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|변수가 `pRegister` 인수로 표시 된 레지스터에 있습니다.|  
|`E_FAIL`|변수가 레지스터 또는 레지스터 상대 위치에 있지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참조

- [VariableLocationType 열거형](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome 인터페이스](icordebugvariablehome-interface.md)
