---
title: ICorDebugType::GetFirstTypeParameter 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: da0097daea183c76f97f0b1966b313e1cb5a557b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379947"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a>ICorDebugType::GetFirstTypeParameter 메서드
<xref:System.Type>이가 나타내는 형식의 첫 번째 매개 변수를 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `value`  
 제한이 `ICorDebugType`첫 번째 매개 변수를 나타내는 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetFirstTypeParameter`형식에 대 한 추가 정보가 최대 하나의 형식 매개 변수를 포함 하는 경우를 호출할 수 있습니다. 특히 [ICorDebugType:: GetType](icordebugtype-gettype-method.md) 메서드로 표시 된 것 처럼 형식이 ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR 인 경우에도 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
