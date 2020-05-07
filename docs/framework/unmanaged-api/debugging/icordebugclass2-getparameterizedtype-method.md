---
title: ICorDebugClass2::GetParameterizedType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 329bcee441b395982a8a8b539c0a938fa8170b14
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894051"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType 메서드
이 클래스에 대 한 형식 선언을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `elementType`  
 진행 이 클래스의 요소 형식을 지정 하는 CorElementType 열거형의 값입니다 .이 ICorDebugClass2이 값 형식을 나타내는 경우이 값을 ELEMENT_TYPE_VALUETYPE 설정 합니다. 이이 `ICorDebugClass2` 복합 형식을 나타내는 경우이 값을 ELEMENT_TYPE_CLASS 설정 합니다.  
  
 `nTypeArgs`  
 진행 형식이 제네릭인 경우 형식 매개 변수의 수입니다. 형식 매개 변수 (있는 경우)의 수는 클래스에 필요한 수와 일치 해야 합니다.  
  
 `ppTypeArgs`  
 진행 각각 형식 매개 변수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다. 제네릭이 아닌 클래스의 경우이 값은 null입니다.  
  
 `ppType`  
 제한이 형식 선언을 나타내는 `ICorDebugType` 개체의 주소에 대 한 포인터입니다. 이 개체는 관리 코드의 <xref:System.Type> 개체와 동일 합니다.  
  
## <a name="remarks"></a>설명  
 클래스가 제네릭이 아닌 경우 즉, 형식 매개 변수가 `GetParameterizedType` 없는 경우에는 클래스에 해당 하는 런타임 형식 개체를 가져옵니다. `elementType` 클래스가 값 형식인 경우 ELEMENT_TYPE_VALUETYPE 클래스에 대 한 올바른 요소 형식으로 설정 해야 합니다. 그렇지 않으면 ELEMENT_TYPE_CLASS 합니다.  
  
 클래스에서 형식 매개 변수를 허용 하는 경우 `ArrayList<T>`(예:)를 `GetParameterizedType` 사용 하 여와 `ArrayList<int>`같은 인스턴스화된 형식에 대 한 형식 개체를 생성할 수 있습니다.  
  
## <a name="background-information"></a>배경 정보  
 .NET Framework 버전 1.0 및 1.1에서 메타 데이터의 모든 형식은 실행 중인 프로세스의 형식에 직접 매핑될 수 있습니다. 따라서 메타 데이터 형식과 런타임 형식은 실행 중인 프로세스에서 단일 표현을 갖습니다. 그러나 메타 데이터의 한 제네릭 형식은 실행 중인 프로세스에서 형식의 여러 인스턴스에 매핑될 수 있습니다. 예를 들어 메타 데이터 형식은 `SortedList<K,V>` , `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`등 `SortedList<String, EmployeeRecord>`으로 매핑될 수 있습니다. 따라서 형식 인스턴스화를 처리 하는 방법이 필요 합니다.  
  
 .NET Framework 버전 2.0는 인터페이스를 `ICorDebugType` 소개 합니다. `ICorDebugClass` 제네릭 형식의 경우 `ICorDebugClass2` 또는 개체는 인스턴스화되지 않은 형식 (`SortedList<K,V>`)을 나타내며 개체는 `ICorDebugType` 다양 한 인스턴스화된 형식을 나타냅니다. `ICorDebugClass` 또는 `ICorDebugClass2` 개체가 지정 된 경우 메서드를 `ICorDebugType` `ICorDebugClass2::GetParameterizedType` 호출 하 여 모든 인스턴스화에 대 한 개체를 만들 수 있습니다. 또한 Int32와 같은 단순 `ICorDebugType` 형식 또는 제네릭이 아닌 형식에 대 한 개체를 만들 수 있습니다.  
  
 형식에 대 한 `ICorDebugType` 런타임 개념을 나타내는 개체를 도입 하면 API 전체에 걸쳐 ripple 효과가 적용 됩니다. 이전에 `ICorDebugClass` 또는 `ICorDebugClass2` 개체나 값을 `CorElementType` 사용 하 던 함수는 `ICorDebugType` 개체를 사용 하기 위해 일반화 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
