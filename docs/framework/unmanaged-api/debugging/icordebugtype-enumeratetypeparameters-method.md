---
title: ICorDebugType::EnumerateTypeParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791308"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters 메서드
이 ICorDebugType에서 참조 하는 클래스의 <xref:System.Type> 매개 변수를 포함 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppTyParEnum`  
 제한이 형식의 매개 변수를 포함 하는 `ICorDebugTypeEnum`의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 [ICorDebugType:: GetType](icordebugtype-gettype-method.md) 에서 반환 된 corelementtype 값이 ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR 또는 ELEMENT_TYPE_FNPTR 인 경우 `EnumerateTypeParameters`를 사용할 수 있습니다. 매개 변수 수와 해당 순서는 다음 유형에 따라 달라 집니다.  
  
- ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE:이 메서드가 반환 하는 `ICorDebugTypeEnum`에 포함 된 형식 매개 변수의 수는 해당 클래스에 대 한 형식 매개 변수의 수에 따라 달라 집니다. 예를 들어 형식이 `class Dict<String,int32>`이면 `EnumerateTypeParameters`는 `String`를 나타내는 개체와 순서 대로 `int32`를 포함 하는 `ICorDebugTypeEnum` 반환 합니다.  
  
- ELEMENT_TYPE_FNPTR: `ICorDebugTypeEnum`에 포함 된 형식 매개 변수의 수는 함수에서 허용 하는 인수 수보다 하나 큽니다. `ICorDebugTypeEnum`에 포함 된 첫 번째 형식 매개 변수는 함수의 반환 형식이 고 후속 형식 매개 변수는 함수의 매개 변수입니다.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR: 하나의 형식 매개 변수가 반환 됩니다. 예를 들어 형식이 `int32[]`와 같은 배열 형식인 경우`EnumerateTypeParameters`는 `int32`를 나타내는 개체를 포함 하는 `ICorDebugTypeEnum` 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
