---
title: ICorDebugEval::CreateValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976254"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue 메서드
초기 값이 0 또는 null 인 지정 된 형식의 값을 만듭니다.  
  
 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다. 대신 [ICorDebugEval2:: CreateValueForType](icordebugeval2-createvaluefortype-method.md) 을 사용 하십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `elementType`  
 진행 값의 형식을 지정 하는 [Corelementtype](../metadata/corelementtype-enumeration.md) 열거형의 값입니다.  
  
 `pElementClass`  
 진행 형식이 기본 형식이 아닌 경우 값의 클래스를 지정 하는 [ICorDebugClass](icordebugclass-interface.md) 개체에 대 한 포인터입니다.  
  
 `ppValue`  
 제한이 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `CreateValue`함수 실행 `ICorDebugValue` 에서 사용 하는 용도로만 지정 된 형식의 개체를 만듭니다. 이 값 개체를 사용 하 여 사용자 상수를 매개 변수로 전달할 수 있습니다.  
  
 값의 형식이 기본 형식이 면 해당 초기 값은 0 또는 null입니다. [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) 를 사용 하 여 기본 형식 값을 설정 합니다.  
  
 의 `elementType` 값이 ELEMENT_TYPE_CLASS 이면 null 개체 참조를 나타내는 "ICorDebugReferenceValue" (에서 `ppValue`반환 됨)을 가져옵니다. 이 개체를 사용 하 여 개체 참조 매개 변수가 있는 함수 실행에 null을 전달할 수 있습니다. 를 모든 항목으로 `ICorDebugValue` 설정할 수는 없습니다. 항상 null로 유지 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고 항목

- [CreateValueForType 메서드](icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval 인터페이스](icordebugeval-interface.md)
