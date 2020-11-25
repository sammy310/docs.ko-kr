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
ms.openlocfilehash: 3717497ab6e72f0ce67f688813ee7264206e8c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727954"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters 메서드

<xref:System.Type>이 ICorDebugType가 참조 하는 클래스의 매개 변수를 포함 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppTyParEnum`  
 제한이 `ICorDebugTypeEnum` 형식의 매개 변수를 포함 하는의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `EnumerateTypeParameters` [ICorDebugType:: GetType](icordebugtype-gettype-method.md) 에서 반환 된 corelementtype 값이 ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR 또는 ELEMENT_TYPE_FNPTR 이면를 사용할 수 있습니다. 매개 변수 수와 해당 순서는 다음 유형에 따라 달라 집니다.  
  
- ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE:이 메서드가 반환 하는에 포함 된 형식 매개 변수의 수는 `ICorDebugTypeEnum` 해당 클래스에 대 한 정식 형식 매개 변수의 수에 따라 달라 집니다. 예를 들어, 형식이 인 경우는 `class Dict<String,int32>` `EnumerateTypeParameters` 및를 `ICorDebugTypeEnum` `String` 순서 대로 나타내는 개체를 포함 하는을 반환 합니다 `int32` .  
  
- ELEMENT_TYPE_FNPTR:에 포함 된 형식 매개 변수의 수는 `ICorDebugTypeEnum` 함수에서 허용 하는 인수 수보다 하나 큽니다. 에 포함 된 첫 번째 형식 매개 변수는 `ICorDebugTypeEnum` 함수의 반환 형식이 고, 후속 형식 매개 변수는 함수의 매개 변수입니다.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF 또는 ELEMENT_TYPE_PTR: 하나의 형식 매개 변수가 반환 됩니다. 예를 들어 형식이와 같은 배열 형식인 경우 `int32[]` `EnumerateTypeParameters` 는를 `ICorDebugTypeEnum` 나타내는 개체를 포함 하는을 반환 `int32` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
