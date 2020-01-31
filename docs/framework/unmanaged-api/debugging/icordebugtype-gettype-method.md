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
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791247"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType 메서드
이 ICorDebugType가 나타내는 CLR (공용 언어 런타임) <xref:System.Type>의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ty`  
 제한이 이 `ICorDebugType` 나타내는 CLR <xref:System.Type>를 나타내는 `CorElementType` 열거형의 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `ty` 값이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 경우 [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) 메서드를 호출 하 여 제네릭 형식에 대 한 인스턴스화되지 않은 형식을 가져올 수 있습니다. 그렇지 않으면 `ICorDebugType::GetClass`를 호출 하지 마세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
