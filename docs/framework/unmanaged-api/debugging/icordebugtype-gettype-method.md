---
title: ICorDebugType::GetType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379920"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType 메서드
이 ICorDebugType로 표시 되는 CLR (공용 언어 런타임)의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ty`  
 제한이 `CorElementType`이가 나타내는 CLR을 나타내는 열거형의 값에 대 한 포인터입니다 <xref:System.Type> `ICorDebugType` .  
  
## <a name="remarks"></a>설명  
 의 값 `ty` 이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 경우 [ICorDebugType:: getclass](icordebugtype-getclass-method.md) 메서드를 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다. 그렇지 않으면를 호출 하지 않습니다 `ICorDebugType::GetClass` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
