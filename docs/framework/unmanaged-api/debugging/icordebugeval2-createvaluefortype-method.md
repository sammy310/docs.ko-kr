---
title: ICorDebugEval2::CreateValueForType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 20315dfc426b63f2d526f3481756e165b388b41e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137605"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType 메서드
초기 값이 0 또는 null 인 지정 된 형식의 새 ICorDebugValue에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pType`  
 진행 유형을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.  
  
 `ppValue`  
 제한이 값을 나타내는 `ICorDebugValue` 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 일반화 [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) `CreateValueForType` `List<int>`와 같은 생성 된 형식을 포함 하 여 임의의 개체 형식을 지정할 수 있습니다. 이 메서드의 유일한 용도는 함수 실행으로 전달 될 수 있는 값을 생성 하는 것입니다.  
  
 형식은 클래스 또는 값 형식 이어야 합니다. 이 메서드를 사용 하 여 배열 값 이나 문자열 값을 만들 수는 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
